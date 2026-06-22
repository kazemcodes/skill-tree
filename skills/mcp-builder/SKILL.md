---
name: mcp-builder
description: Create MCP (Model Context Protocol) servers that let LLMs interact with external services — covers Python FastMCP and TypeScript MCP SDK
---

# MCP Builder

Build high-quality MCP servers for LLM integration.

## When to Use

- Creating MCP server for an external API
- Building tools that LLMs can call
- Integrating services with AI agents

## Design Principles

1. **Build for workflows, not API endpoints** — consolidate related operations
2. **Optimize for limited context** — return high-signal data, not dumps
3. **Design actionable errors** — guide toward correct usage
4. **Use evaluation-driven development** — test with realistic scenarios

## Python (FastMCP)

```python
from fastmcp import FastMCP
from pydantic import BaseModel, Field

mcp = FastMCP("my-server")

class SearchInput(BaseModel):
    query: str = Field(description="Search query")
    limit: int = Field(default=10, ge=1, le=100)

@mcp.tool()
async def search(input: SearchInput) -> str:
    """Search the database for matching records.
    
    Args:
        input: Search parameters
        
    Returns:
        JSON string with search results
    """
    results = await db.search(input.query, limit=input.limit)
    return json.dumps(results)
```

## TypeScript (MCP SDK)

```typescript
import { McpServer } from "@modelcontextprotocol/sdk/server/mcp.js";
import { z } from "zod";

const server = new McpServer({ name: "my-server", version: "1.0.0" });

server.tool(
  "search",
  "Search the database for matching records",
  {
    query: z.string().describe("Search query"),
    limit: z.number().min(1).max(100).default(10),
  },
  async ({ query, limit }) => {
    const results = await db.search(query, limit);
    return { content: [{ type: "text", text: JSON.stringify(results) }] };
  }
);
```

## Tool Annotations

```python
@mcp.tool(
    readOnlyHint=True,      # No side effects
    destructiveHint=False,  # Safe to run
    idempotentHint=True,    # Same result on retry
)
async def get_user(user_id: str) -> dict:
    ...
```

## Error Handling

```python
# Good: actionable error messages
raise ValueError(
    "No results found. Try broader search terms or "
    "use filter='active_only' to reduce scope."
)

# Bad: unhelpful error
raise Exception("Error")
```

## Checklist

- [ ] Tool names use kebab-case or snake_case consistently
- [ ] Input schemas have descriptions and constraints
- [ ] Error messages suggest next steps
- [ ] Read-only tools marked with `readOnlyHint`
- [ ] Character limits enforced (truncate at ~25k tokens)
- [ ] Pagination for large result sets
- [ ] Tests with realistic scenarios
