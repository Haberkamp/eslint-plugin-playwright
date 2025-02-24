# Enforce assertion to be made in a test body (`expect-expect`)

Ensure that there is at least one `expect` call made in a test.

## Rule Details

Examples of **incorrect** code for this rule:

```javascript
test('should be a test', () => {
  console.log('no assertion');
});

test('should assert something', () => {});
```

Examples of **correct** code for this rule:

```javascript
test('should be a test', async () => {
  await expect(page).toHaveTitle('foo');
});

test('should work with callbacks/async', async () => {
  await test.step('step 1', async () => {
    await expect(page).toHaveTitle('foo');
  });
});
```
