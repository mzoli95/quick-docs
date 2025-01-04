# Using Prettier in Visual Studio Code

## Installation and Setup

1. Open Extensions in VSCode
   - Use the shortcut: `Ctrl + Shift + X` (Windows/Linux) or `Cmd + Shift + X` (macOS)
   - Search for "Prettier - Code formatter"
   - Click "Install"

2. Set Prettier as the default formatter
   - Open Settings: `Ctrl + ,` (Windows/Linux) or `Cmd + ,` (macOS)
   - Search for "Default Formatter"
   - Select "Prettier - Code formatter" from the dropdown

3. Enable format on save
   - In Settings, search for "Format on save"
   - Check the box next to "Editor: Format On Save"

## Usage

After setup, you can format your documents automatically by saving:
- Use `Ctrl + S` (Windows/Linux) or `Cmd + S` (macOS) to save and format

Your code will now be formatted according to Prettier's rules every time you save a file.

## Troubleshooting

If formatting doesn't work:
- Ensure Prettier is properly configured in your project
- Check for a `.prettierrc` file in your project root
- Verify that the file type is supported by Prettier
