# Digital Certificates Monorepo

This is a monorepo built with pnpm workspaces for digital certificates.

## 📦 Repository Structure

```
digital-certificates/
├── services/           # Application services (frontend, backend, ...)
│   └── frontend/     
├── packages/           # Shared packages and libraries
├── package.json        # Root package configuration
└── pnpm-workspace.yaml # Workspace configuration
```

## 🛠 Tech Stack & Tools

### Package Management
- **pnpm**: Fast and efficient package manager
- **Workspaces**: Managed via `pnpm-workspace.yaml`

### Code Quality Tools

#### ESLint
We use ESLint for code linting:

Run linting with:
```bash
pnpm lint
```

#### Prettier
Code formatting is handled by Prettier. Configuration in `.prettierrc`:
```json
{
  "semi": false,
  "singleQuote": true,
  "useTabs": true,
  "trailingComma": "none",
  "plugins": ["prettier-plugin-tailwindcss"],
  "tailwindConfig": "./services/frontend/tailwind.config.ts"
}
```

#### Husky
Git hooks management using Husky:
- Pre-commit: Runs linting and type checking
- Commit message: Validates commit messages using commitlint

#### Commitlint
Enforces conventional commit messages with the following format:
```
type(scope): subject

Examples:
feat(auth): add login functionality
fix(api): correct response handling
docs(readme): update installation steps
```

Supported types:
- `feat`: New features
- `fix`: Bug fixes
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Adding or modifying tests
- `chore`: Maintenance tasks

## 🚀 Getting Started

1. **Prerequisites**
   ```bash
   npm install -g pnpm
   ```

2. **Installation**
   ```bash
   pnpm install
   ```

3. **Development**
   ```bash
   pnpm dev        # Start development servers
   pnpm build      # Build all packages
   pnpm lint       # Run linting
   pnpm test       # Run tests
   ```

## 📝 Scripts

Root `package.json` scripts:
```json
{
  "scripts": {
    "build": "pnpm -r build",
    "dev": "pnpm -r dev",
    "lint": "pnpm -r lint",
    "test": "pnpm -r test",
    "clean": "pnpm -r clean",
    "typecheck": "tsc --noEmit"
  }
}
```

## 🔧 Development Workflow

1. Clone the repository
2. Install dependencies with `pnpm install`
3. Create a new branch for your feature/fix
4. Make your changes
5. Commit using conventional commit format
6. Push and create a pull request

### Commit Example
```bash
git commit -m "feat(frontend): add user authentication"
```

## 🤝 Contributing

1. All commits must follow the conventional commit format
2. Code must pass linting and type checking
3. New features should include tests
4. Update documentation as needed

## 📚 Additional Documentation

- [Frontend Service](/services/frontend/README.md)
- [Package Documentation](/packages/README.md)

