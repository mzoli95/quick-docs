# Using Tailwind

## Installation and Setup

1. Open a terminal and install Tailwind
- npm install -D tailwindcss


2. Create a config file
- npx tailwindcss init

3. Modify the tailwind config file with the following basic code
```/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./src/**/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
}```

4. Add the Tailwind directives to your CSS
@tailwind base;
@tailwind components;
@tailwind utilities;


## Usage

1. Apply Tailwind classes directly in your HTML

```<div class="bg-blue-500 text-white p-4 rounded-lg shadow-md"> This is a styled div using Tailwind CSS </div>```

2. Use Tailwind's responsive design classes

```<div class="text-sm md:text-base lg:text-lg">
  This text changes size on different screen sizes
</div>```

3. Customize your design by extending the Tailwind config

```module.exports = {
  theme: {
    extend: {
      colors: {
        'custom-blue': '#1da1f2',
      },
    },
  },
}```

4. Use the @apply directive in your CSS to extract common utility patterns

```.btn-primary {
  @apply bg-blue-500 text-white font-bold py-2 px-4 rounded;
}```

## Troubleshooting

Classes not applying:
- Ensure your HTML files are included in the content array of your Tailwind config.
- Check if your build process is correctly processing the Tailwind CSS file.
- Custom styles not working:
- Make sure you've rebuilt your CSS after modifying the Tailwind config.
- Verify that your custom styles are properly defined in the theme.extend section.
- Purge issues in production:
- Ensure all your template files are included in the content array.
- If using a framework, make sure dynamic class names are fully written out.
Conflicts with other CSS:
- Consider using Tailwind's @layer directive to manage style precedence.
- Use more specific selectors or !important flag for Tailwind classes if needed.
- Performance issues:
- Use @apply to group commonly used utilities into custom classes.