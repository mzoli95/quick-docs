# Using ESLint

## Installation and Setup

1. Install ESLint extension

2. Install ESLint dependencies
- ng add @angular-eslint/schematics

3. Modify your settings.json
```
{
  "typescript.tsdk": "node_modules/typescript/lib",
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": ["source.fixAll.eslint"],
  "eslint.validate": ["javascript", "typescript", "html"],
  "eslint.options": {
    "overrideConfigFile": "eslint.config.js"
  },
  "eslint.useFlatConfig": true
}

```


## Usage

- ESLint will automatically check your code as you type, highlighting issues with colorful underlining2.
- To manually run ESLint on your project, use the following command:
``` ng lint ```
- ESLint can automatically fix many issues. To enable auto-fix on save, ensure the "editor.codeActionsOnSave" setting is configured as shown above2.
- To disable ESLint for a specific line, use the following comment:
``` // eslint-disable-next-line ```

## Troubleshooting

1. If ESLint is not working in VS Code:
- Ensure the ESLint extension is installed and enabled5.
- Check if ESLint is properly configured in your project5.
- Verify that the correct file extensions are being linted6.
2. If you're not seeing any ESLint errors or warnings:
- Check your ESLint configuration file (.eslintrc.json or eslint.config.js)5.
- Ensure you haven't accidentally disabled the rules you're testing6.
3. For TypeScript-specific issues:
- Make sure you've installed and configured the TypeScript ESLint plugin correctly6.
4. Restarting the ESLint server:
- Open the command palette (Ctrl+Shift+P or Cmd+Shift+P on macOS)7.
- Type "ESLint: Restart ESLint Server" and press Enter7.
- This can help if ESLint is not picking up recent changes or behaving unexpectedly7.
5. If all else fails:
- Try updating all ESLint-related dependencies6.
- Check the ESLint output channel in VS Code for any error messages6.
- Consider setting up your ESLint config from scratch using eslint --init6.
