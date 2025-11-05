# React Component Builder Toolkit

A VS Code extension to quickly create React components with TypeScript and custom templates.

## Features

- ✅ Generate React components with a standard folder structure
- ✅ Custom templates for the component and index file
- ✅ Supports tsx, jsx, ts, js
- ✅ Automatically generates a TypeScript interface
- ✅ Validates component names

## How to Use

1. Right-click a folder in Explorer
2. Select "Create React Component"
3. Enter the component name
4. Done!

## Configuration (Settings)

### Via GUI

1. Open Settings (Ctrl+,)
2. Search for "React Component Builder Toolkit"
3. Adjust the following options:
   - reactComponentBuilderToolkit.componentTemplate: Template for the component file (use `{ComponentName}`)
   - reactComponentBuilderToolkit.indexTemplate: Template for `index.ts` (use `{ComponentName}`)
   - reactComponentBuilderToolkit.fileExtension: `tsx` | `ts` | `jsx` | `js`
   - reactComponentBuilderToolkit.createIndexFile: Toggle creating `index.ts`
   - reactComponentBuilderToolkit.componentTemplatePath: File path to the component template
   - reactComponentBuilderToolkit.indexTemplatePath: File path to the index template

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
  "reactComponentBuilderToolkit.indexTemplatePath": "./.templates/index.ts.tpl"
}
```

### Notes

- The `{ComponentName}` placeholder will be replaced with the component name you enter.
- `fileExtension` determines the extension of the generated component file.
- Set `createIndexFile = false` if you do not want to generate `index.ts`.
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
