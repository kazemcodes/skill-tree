---
name: playwright-testing
description: Test web applications using Playwright — automate browser testing, verify UI functionality, capture screenshots for debugging
---

# Playwright Testing

Automate browser-based testing for web applications.

## When to Use

- Testing frontend functionality in real browser
- Verifying UI interactions (clicks, forms, navigation)
- Debugging visual issues
- Capturing screenshots for documentation
- Cross-browser compatibility testing

## Setup

```bash
# Install Playwright
npm init playwright@latest

# Or add to existing project
npm install -D @playwright/test
```

## Writing Tests

### Basic Test

```typescript
import { test, expect } from '@playwright/test';

test('homepage loads correctly', async ({ page }) => {
  await page.goto('http://localhost:3000');
  await expect(page).toHaveTitle(/My App/);
  await expect(page.locator('h1')).toContainText('Welcome');
});
```

### Form Interaction

```typescript
test('login form submits', async ({ page }) => {
  await page.goto('/login');
  await page.fill('#email', 'user@example.com');
  await page.fill('#password', 'password123');
  await page.click('button[type="submit"]');
  await expect(page).toHaveURL('/dashboard');
});
```

### Screenshot

```typescript
test('capture screenshot', async ({ page }) => {
  await page.goto('http://localhost:3000');
  await page.screenshot({ path: 'screenshot.png', fullPage: true });
});
```

### API Mocking

```typescript
test('handles API error', async ({ page }) => {
  await page.route('**/api/data', route => {
    route.fulfill({ status: 500, body: 'Server Error' });
  });
  await page.goto('/');
  await expect(page.locator('.error')).toBeVisible();
});
```

## Running Tests

```bash
# Run all tests
npx playwright test

# Run specific file
npx playwright test tests/login.spec.ts

# Run in headed mode (see browser)
npx playwright test --headed

# Run with UI mode
npx playwright test --ui

# Generate report
npx playwright show-report
```

## Best Practices

- Use `data-testid` attributes for reliable selectors
- Avoid XPath — use Playwright's built-in locators
- Use `page.waitForLoadState()` after navigation
- Mock API calls in unit tests, hit real APIs in E2E
- Take screenshots on failure for debugging

```typescript
// Good: resilient selector
page.getByRole('button', { name: 'Submit' })

// Bad: fragile selector
page.locator('.css-x7y3k > div:nth-child(3) > button')
```

## Debugging

```typescript
// Pause for inspection
await page.pause();

// Debug with console logs
page.on('console', msg => console.log(msg.text()));

// Trace for post-mortem analysis
npx playwright test --trace on
npx playwright show-trace trace.zip
```
