# Shared Configurations

This package contains shared configurations for TypeScript, ESLint, and Prettier that can be used across all projects in the monorepo.

## Usage

Extend the configurations in your project:

- **TypeScript**: Extend your `tsconfig.json`.
- **ESLint**: Extend your `.eslintrc.js`.
- **Prettier**: Extend your `.prettierrc.js`.

### Installation

To use the shared configurations in your project, install the package:

```bash
pnpm add @openanaffa/config
```

### TypeScript Configuration

Extend the base TypeScript configuration in your project's `tsconfig.json`:

```json
{
  "extends": "@shared/config/tsconfig-base.json",
  "compilerOptions": {
    "outDir": "dist",
    "rootDir": "src"
  },
  "include": ["src"]
}
```

### ESLint Configuration

Extend the ESLint configuration in your project's `.eslintrc.js`:

```javascript
module.exports = {
  extends: ["@shared/config/eslint-preset.js"],
  // Add project-specific rules here
};
```

### Prettier Configuration

Extend the Prettier configuration in your project's `.prettierrc.js`:

```javascript
module.exports = {
  ...require("@shared/config/prettier-preset.js"),
  // Add project-specific options here
};
```

## Dependencies

Make sure to add the following dependencies to your project:

```json
{
  "devDependencies": {
    "@shared/config": "workspace:*",
    "@typescript-eslint/eslint-plugin": "^6.21.0",
    "@typescript-eslint/parser": "^6.21.0",
    "eslint": "^8.56.0",
    "eslint-config-prettier": "^9.1.0",
    "eslint-plugin-import": "^2.29.1",
    "eslint-plugin-prettier": "^5.1.3",
    "prettier": "^3.2.5",
    "typescript": "^5.3.3"
  }
}
```

## License

This project is licensed under the MIT License.
