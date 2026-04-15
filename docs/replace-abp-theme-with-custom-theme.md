# How to replace the ABP default theme with a custom theme

## Overview

The [ABP Framework](https://abp.io) provides a powerful and flexible theming system that allows developers to control the entire look and feel of their application without breaking core framework functionality. By default, ABP applications use the LeptonX theme, which offers a modern UI, built-in layouts, and ready-to-use components. However, in many real-world scenarios, you may want to replace this default theme with a fully customized design tailored to your product or brand.

Replacing the default theme is not just about changing colors or styles—it involves redefining the application layout, component structure, and visual identity while still leveraging ABP’s modular architecture and infrastructure. This ensures that even after customization, essential features such as authentication, localization, navigation, and permission management continue to work seamlessly.

#### Why Replace the Default Theme?

There are several reasons why you might want to replace the default ABP theme:

- **Brand Identity:** Align the application UI with your company’s branding guidelines (colors, typography, layout).
- **Custom UI/UX Requirements:** Implement unique user experiences that go beyond the default theme capabilities.
- **Integration with UI Libraries:** Use third-party UI frameworks like PrimeNG, Tailwind CSS, or Bootstrap-based custom designs.
- **Performance Optimization:** Remove unused styles and components to reduce bundle size and improve performance.
- **Full Design Control:** Gain complete control over layouts, headers, footers, and reusable UI components.

## Understanding ABP Theme Architecture

Learn about ABP's theme structure, including the default theme components, layout system, module organization, and how themes are registered in the application. Understanding this architecture is crucial for successful theme replacement.

```
├── src
│   ├── app
│   │   ├── footer
│   │   │   ├── footer.component.ts
│   │   │   └── footer.config.ts
│   │   ├── home
│   │   │   ├── home.component.html
│   │   │   ├── home.component.scss
│   │   │   └── home.component.ts
│   │   ├── app.component.ts
│   │   ├── app.config.ts
│   │   ├── app.routes.ts
│   │   └── route.provider.ts
│   ├── assets
│   │   └── images
│   │       └── ...
│   ├── environments
│   │   ├── environment.prod.ts
│   │   └── environment.ts
│   ├── favicon.ico
│   ├── index.html
│   ├── main.ts
│   └── styles.scss
├── README.md
├── angular.json
├── package.json
└── yarn.lock
```

## Environment Setup and Tools

Ensure your development environment is properly configured. This includes verifying Node.js and npm versions, installing ABP CLI, setting up your IDE with necessary extensions, and confirming your ABP application is running correctly.

## Backup Current Theme Configuration

Create a complete backup of your current theme files, configurations, and custom modifications. Document all current theme settings in appsettings.json and save copies of modified layout files. This ensures you can rollback if needed.

## Configure Theme Layouts

Define and implement custom layouts for your theme including application layout, account layout, and empty layout. Configure navigation menus, headers, footers, and sidebars. Map routes to appropriate layouts in your routing configuration.

## Implement Theme Styles and Assets

Add custom CSS/SCSS files, import fonts, and include custom assets (images, icons). Configure theme variables for colors, spacing, and typography. Set up SCSS compilation and ensure proper asset paths in angular.json or webpack config.

## Register Custom Theme

Register your custom theme in the application module by replacing the default theme provider. Update appsettings.json to reference the new theme. Configure theme options and ensure proper dependency injection.