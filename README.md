# Pre-Commit Templates

A collection of reusable pre-commit configurations for different technology stacks.

## Requirements

Install pre-commit:

```bash
pip install pre-commit
```

On macOS:

```bash
brew install pre-commit
```

## Setup

### 1. Download Configuration

**Option A: Download specific stack config**

```bash
# Example for Laravel + Vue stack
curl -O https://raw.githubusercontent.com/paolobellini/precommit-templates/main/stacks/laravel-vue/.pre-commit-config.yaml
```

**Option B: Clone specific stack directory**

```bash
# Using degit
degit github:paolobellini/precommit-templates/stacks/laravel-vue .

# Or using tiged
npx tiged paolobellini/precommit-templates/stacks/laravel-vue .
```

### 2. Install Stack Dependencies

Each stack requires specific dependencies. See the stack section below for requirements.

**Example for Laravel + Vue:**

```bash
./vendor/bin/sail composer require --dev \
  larastan/larastan \
  rector/rector \
  driftingly/rector-laravel \
  laravel/pint \
  pestphp/pest \
  icanhazstring/composer-unused
```

### 3. Install Pre-Commit Hooks

```bash
pre-commit install
```

### 4. Verify Setup

```bash
pre-commit run --all-files
```

## Available Stacks

### laravel-vue

Laravel + Vue.js + Inertia.js with:

- Rector (refactoring) - [rector-laravel](https://github.com/driftingly/rector-laravel)
- Laravel Pint (formatting)
- Larastan (static analysis)
- Pest (unit tests)
- ESLint + TypeScript check
- Composer unused dependencies

**Dependencies:**

```bash
./vendor/bin/sail composer require --dev \
  larastan/larastan \
  rector/rector \
  driftingly/rector-laravel \
  laravel/pint \
  pestphp/pest \
  icanhazstring/composer-unused
```

### laravel-api

Laravel REST API with:

- Rector (refactoring)
- Laravel Pint (formatting)
- Larastan (static analysis)
- Pest (tests)
- Scribe (API documentation) - [knuckleswtf/scribe](https://scribe.knuckles.wtf/)
- Composer unused dependencies

**Dependencies:**

```bash
./vendor/bin/sail composer require --dev \
  larastan/larastan \
  rector/rector \
  driftingly/rector-laravel \
  laravel/pint \
  pestphp/pest \
  knuckleswtf/scribe \
  icanhazstring/composer-unused
```

## Workflow

### Fast commits (WIP - skip checks)

```bash
git commit -m "wip: work in progress" --no-verify
```

### Full validation commits

```bash
git commit -m "feat: new feature [issue: #123]"
```

This will run all configured checks automatically.

## Updating Configuration

To update to the latest configuration:

```bash
# Re-download the configuration file
curl -O https://raw.githubusercontent.com/paolobellini/precommit-templates/main/stacks/laravel-vue/.pre-commit-config.yaml

# Clean and reinstall hooks
pre-commit clean
pre-commit install
```

## Configuration Files

Some stacks require additional configuration files:

- **Larastan**: `phpstan.neon`
- **Rector**: `rector.php`
- **ESLint**: `.eslintrc.js` or `eslint.config.js`
- **Scribe**: `config/scribe.php`

These files should be customized based on your project needs. Example configurations are available in each stack directory.

## Contributing

Contributions welcome! To add a new stack or improve existing ones:

1. Fork the repository
2. Create your stack in `stacks/your-stack-name/`
3. Add `.pre-commit-config.yaml` and a `README.md`
4. Test with `pre-commit try-repo . <hook-id> --verbose --all-files`
5. Submit a Pull Request

## License

MIT

---

**Repository**: [github.com/paolobellini/precommit-templates](https://github.com/paolobellini/precommit-templates)

For issues or questions, please [open an issue](https://github.com/paolobellini/precommit-templates/issues).
