
# ESLint Rules Reference

This document lists important ESLint rules for writing clean, consistent, and professional JavaScript/React code.

---

## ✅ Recommended React Rule

### 1. Disable PropTypes Validation (if using TypeScript)

```js
'react/prop-types': 'off'
```

Turns off warnings related to missing PropTypes in React components, since TypeScript already handles type checking.

---

## ✅ General JavaScript/Code Quality Rules

### 2. Disallow Unused Variables

```js
'no-unused-vars': ['warn', { argsIgnorePattern: '^_' }]
```

Warns about declared variables that are never used. Prefix function args with `_` to intentionally ignore them without error.

### 3. Disallow Console Logs in Production

```js
'no-console': ['warn', { allow: ['warn', 'error'] }]
```

Warns when `console.log` is used. Allows `console.warn` and `console.error` which are more appropriate for warnings/errors.

### 4. Enforce Double Quotes for Strings

```js
'quotes': ['error', 'double']
```

Requires use of double quotes (`"`) instead of single quotes (`'`), for consistent string formatting.

### 5. Require Semicolons

```js
'semi': ['error', 'always']
```

Ensures all statements are terminated with a semicolon for clarity and consistency.

### 6. Disallow Debugger Statements

```js
'no-debugger': 'error'
```

Prevents accidental `debugger` statements in production code.

### 7. Prefer `const` Over `let` When Variables Are Not Reassigned

```js
'prefer-const': 'error'
```

Promotes the use of `const` for variables that are never reassigned after declaration.

---

## 📦 How to Use in `eslint.config.js` (Flat Config) `Rea`

```js
import js from '@eslint/js';
import react from 'eslint-plugin-react';

export default [
  js.configs.recommended,
  {
    plugins: {
      react,
    },
    rules: {
      'react/prop-types': 'off',
      'no-unused-vars': ['warn', { argsIgnorePattern: '^_' }],
      'no-console': ['warn', { allow: ['warn', 'error'] }],
      'quotes': ['error', 'single'],
      'semi': ['error', 'always'],
      'no-debugger': 'error',
      'prefer-const': 'error',
    },
  },
];
```

## 📥 Installation

```bash
npm install eslint eslint-plugin-react --save-dev
```

---

Following these rules helps maintain cleaner, more consistent, and professional codebases.
