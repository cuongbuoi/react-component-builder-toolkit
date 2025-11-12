# React Component Builder Toolkit

<div align="center">

**Generate React Components, Hooks & Contexts in 3 Seconds**

Create production-ready React code with one right-click. Fully customizable templates for components, hooks, and contexts.

[![Visual Studio Marketplace Version](https://img.shields.io/visual-studio-marketplace/v/cuongbuoi.react-component-builder-toolkit?style=for-the-badge&logo=visual-studio-code&label=VS%20Marketplace)](https://marketplace.visualstudio.com/items?itemName=cuongbuoi.react-component-builder-toolkit)
[![Visual Studio Marketplace Downloads](https://img.shields.io/visual-studio-marketplace/d/cuongbuoi.react-component-builder-toolkit?style=for-the-badge&label=Downloads)](https://marketplace.visualstudio.com/items?itemName=cuongbuoi.react-component-builder-toolkit)
[![Visual Studio Marketplace Rating](https://img.shields.io/visual-studio-marketplace/r/cuongbuoi.react-component-builder-toolkit?style=for-the-badge&label=Rating)](https://marketplace.visualstudio.com/items?itemName=cuongbuoi.react-component-builder-toolkit)
[![Open VSX Version](https://img.shields.io/open-vsx/v/cuongbuoi/react-component-builder-toolkit?style=for-the-badge&logo=eclipse-ide&label=Open%20VSX)](https://open-vsx.org/extension/cuongbuoi/react-component-builder-toolkit)

[🚀 Install for VSCode](https://marketplace.visualstudio.com/items?itemName=cuongbuoi.react-component-builder-toolkit) • [💻 Install for Cursor](https://open-vsx.org/extension/cuongbuoi/react-component-builder-toolkit) • [🐛 Report Bug](https://github.com/cuongbuoi/react-component-builder-toolkit/issues) • [✨ Request Feature](https://github.com/cuongbuoi/react-component-builder-toolkit/issues)

</div>

---

## 🎯 Why Developers Choose This Extension

| Before                           | After                            |
| -------------------------------- | -------------------------------- |
| ❌ Manually create 3+ files      | ✅ One right-click               |
| ❌ Copy-paste boilerplate code   | ✅ Auto-generated with templates |
| ❌ Fix TypeScript types manually | ✅ Perfect types included        |
| ❌ 1-3 minutes per component     | ✅ 3 seconds per component       |
| ❌ Inconsistent code structure   | ✅ Standardized across team      |

## ⚡ Quick Start (30 Seconds Setup)

### 1️⃣ Install Extension

```bash
# VSCode
ext install cuongbuoi.react-component-builder-toolkit

# Cursor
cursor --install-extension cuongbuoi.react-component-builder-toolkit
```

### 2️⃣ Create Your First Component

1. Right-click any folder → "Create React Component"
2. Type: `UserProfile`
3. Press Enter

**Result:**

```
UserProfile/
├── UserProfile.tsx    # Component with TypeScript
└── index.ts          # Clean export
```

### 3️⃣ Create a Custom Hook

1. Right-click folder → "Create React Hook"
2. Type: `useAuth`
3. Done!

**Result:**

```tsx
// useAuth.ts
export const useAuth = () => {
  // Your hook logic
  return { user, login, logout }
}
```

### 4️⃣ Create a Context

1. Right-click folder → "Create React Context"
2. Type: `ThemeContext`
3. Complete!

**Result:**

```tsx
// ThemeContext.tsx with Provider & useThemeContext hook
```

## ✨ Features That Developers Love

### 🎨 Fully Customizable Templates

- **Components**: FC, memo, forwardRef, class components
- **Hooks**: useState, useEffect, custom logic
- **Contexts**: Provider pattern with TypeScript
- **Via Settings GUI** or **Template Files** (.templates/component.tsx)

### 🔧 Works With Your Stack

✅ React 18+  
✅ Next.js 13+ (App Router & Pages)  
✅ Remix  
✅ Vite  
✅ Create React App  
✅ TypeScript & JavaScript

### 🚀 Productivity Boosters

- One-click generation from context menu
- Auto-creates folder structure
- TypeScript interfaces included
- Validates naming (PascalCase, useHook pattern)
- Instantly opens created files

### 📁 Smart File Organization

```
src/
├── components/
│   └── Button/
│       ├── Button.tsx
│       └── index.ts
├── hooks/
│   └── useLocalStorage.ts
└── contexts/
    └── AuthContext.tsx
```

## 📖 Complete Usage Guide

### Via GUI

1. Open Settings (Ctrl+,)
2. Search for "React Component Builder Toolkit"
3. Adjust the following options:

   **Component Settings:**
   - reactComponentBuilderToolkit.componentTemplate: Template for the component file (use `{ComponentName}`)
   - reactComponentBuilderToolkit.indexTemplate: Template for `index.ts` (use `{ComponentName}`)
   - reactComponentBuilderToolkit.fileExtension: `tsx` | `ts` | `jsx` | `js`
   - reactComponentBuilderToolkit.createIndexFile: Toggle creating `index.ts`
   - reactComponentBuilderToolkit.componentTemplatePath: File path to the component template
   - reactComponentBuilderToolkit.indexTemplatePath: File path to the index template

   **Hook Settings:**
   - reactComponentBuilderToolkit.hookTemplate: Template for the hook file (use `{HookName}`)
   - reactComponentBuilderToolkit.hookFileExtension: `tsx` | `ts` | `jsx` | `js` (default: `ts`)
   - reactComponentBuilderToolkit.hookTemplatePath: File path to the hook template

   **Context Settings:**
   - reactComponentBuilderToolkit.contextTemplate: Template for the context file (use `{ContextName}`)
   - reactComponentBuilderToolkit.contextFileExtension: `tsx` | `ts` | `jsx` | `js` (default: `tsx`)
   - reactComponentBuilderToolkit.contextTemplatePath: File path to the context template

### Via settings.json

```json
{
  "reactComponentBuilderToolkit.componentTemplate": "import { FC } from 'react';\n\nexport const {ComponentName}: FC<{ComponentName}Props> = () => {\n  return (\n    <div>{ComponentName}</div>\n  );\n};\n",
  "reactComponentBuilderToolkit.indexTemplate": "export { {ComponentName} } from './{ComponentName}';",
  "reactComponentBuilderToolkit.fileExtension": "tsx",
  "reactComponentBuilderToolkit.createIndexFile": true
}
```

Or specify templates via files (easier to edit, highlight, and format):

```json
{
  "reactComponentBuilderToolkit.componentTemplatePath": "./.templates/component.tsx",
  "reactComponentBuilderToolkit.indexTemplatePath": "./.templates/index.ts.tpl",
  "reactComponentBuilderToolkit.hookTemplatePath": "./.templates/hook.ts",
  "reactComponentBuilderToolkit.contextTemplatePath": "./.templates/context.tsx"
}
```

### Notes

- The `{ComponentName}` placeholder will be replaced with the component name you enter.
- The `{HookName}` placeholder will be replaced with the hook name you enter.
- The `{ContextName}` placeholder will be replaced with the context name you enter.
- `fileExtension` determines the extension of the generated component file.
- `hookFileExtension` determines the extension of the generated hook file (default: `ts`).
- `contextFileExtension` determines the extension of the generated context file (default: `tsx`).
- Set `createIndexFile = false` if you do not want to generate `index.ts`.
- Hook names must start with "use" followed by a capital letter (e.g., `useCustomHook`).
- Context names must start with a capital letter (e.g., `AuthContext`).
- If `*TemplatePath` is provided, the extension will prefer reading content from the file; otherwise, it falls back to the string in settings.

### Template Examples

**Functional Component + props + memo:**

```tsx
"reactComponentBuilderToolkit.componentTemplate": "import React, { memo } from 'react';\n\ninterface {ComponentName}Props {\n  className?: string;\n}\n\nexport const {ComponentName}: React.FC<{ComponentName}Props> = memo(({ className }) => {\n  return (\n    <div className={className}>{ComponentName}</div>\n  );\n});\n\n{ComponentName}.displayName = '{ComponentName}';\n"
```

**Index file re-export:**

```ts
"reactComponentBuilderToolkit.indexTemplate": "export { {ComponentName} } from './{ComponentName}';\n"
```

**JS (no TypeScript):**

```json
{
  "reactComponentBuilderToolkit.fileExtension": "jsx",
  "reactComponentBuilderToolkit.componentTemplate": "import React from 'react';\n\nexport const {ComponentName} = () => {\n  return (\n    <div>{ComponentName}</div>\n  );\n};\n"
}
```

**Custom Hook Template:**

```ts
"reactComponentBuilderToolkit.hookTemplate": "import { useState, useEffect } from 'react';\n\nexport const {HookName} = () => {\n  const [state, setState] = useState(null);\n\n  useEffect(() => {\n    // Your effect logic here\n  }, []);\n\n  return {\n    state,\n    setState\n  };\n};\n"
```

**Hook with TypeScript:**

```ts
"reactComponentBuilderToolkit.hookTemplate": "interface {HookName}Return {\n  value: string;\n  setValue: (value: string) => void;\n}\n\nexport const {HookName} = (): {HookName}Return => {\n  const [value, setValue] = useState<string>('');\n\n  return {\n    value,\n    setValue\n  };\n};\n"
```

**React Context Template (Default):**

The default context template includes:

- Context type interface
- Context creation with TypeScript
- Provider component with children prop
- Custom hook `use{ContextName}` with error handling

**Custom Context Template:**

```tsx
"reactComponentBuilderToolkit.contextTemplate": "import { createContext, useContext, ReactNode, useState } from 'react';\n\ninterface {ContextName}ContextType {\n  value: string;\n  setValue: (value: string) => void;\n}\n\nconst {ContextName}Context = createContext<{ContextName}ContextType | undefined>(undefined);\n\ninterface {ContextName}ProviderProps {\n  children: ReactNode;\n}\n\nexport const {ContextName}Provider = ({ children }: {ContextName}ProviderProps) => {\n  const [value, setValue] = useState<string>('');\n\n  const contextValue: {ContextName}ContextType = {\n    value,\n    setValue\n  };\n\n  return (\n    <{ContextName}Context.Provider value={contextValue}>\n      {children}\n    </{ContextName}Context.Provider>\n  );\n};\n\nexport const use{ContextName} = () => {\n  const context = useContext({ContextName}Context);\n  if (context === undefined) {\n    throw new Error('use{ContextName} must be used within a {ContextName}Provider');\n  }\n  return context;\n};\n"
```

## 🐛 Known Issues

None at the moment! 🎉

Found a bug? [Report it here](https://github.com/cuongbuoi/react-component-builder-toolkit/issues)

## ☕ Support This Project

Love this extension? Support its development!

<div align="center">

<a href="https://www.buymeacoffee.com/cuongbuoi">
  <img src="https://img.buymeacoffee.com/button-api/?text=Buy me a beer&emoji=🍺&slug=cuongbuoi&button_colour=FFDD00&font_colour=000000&font_family=Cookie&outline_colour=000000&coffee_colour=ffffff" />
</a>

**Your support helps:**

- ⚡ Keep extension updated
- ✨ Add requested features
- 🐛 Fix bugs faster
- 📚 Create more templates

</div>

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

MIT License - see the [LICENSE](LICENSE) file for details

## Author

**Cường Buôi**

- GitHub: [@cuongbuoi](https://github.com/cuongbuoi)

## Acknowledgments

Thanks to all contributors and users who provided feedback!

---

<div align="center">

Made with ❤️ by [Cường Buôi](https://github.com/cuongbuoi)

If you like this extension, please ⭐ star the repo and leave a review!

</div>
