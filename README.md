# Pre-Commit Templates

Collezione di configurazioni pre-commit riutilizzabili per diversi stack tecnologici.

## 📋 Prerequisiti

```bash
pip install pre-commit
```

## 🚀 Setup

1. **Copia la configurazione** dello stack che ti interessa:
   ```bash
   # Esempio per Laravel + Vue
   curl -O https://raw.githubusercontent.com/YOUR_USERNAME/precommit-templates/main/stacks/laravel-vue/.pre-commit-config.yaml
   ```

2. **Installa gli hooks**:
   ```bash
   pre-commit install
   ```

3. **Verifica che tutto funzioni**:
   ```bash
   pre-commit run --all-files
   ```

## 📦 Stack Disponibili

### `laravel-vue`
Laravel + Vue.js + Inertia.js con:
- Rector (refactoring)
- Laravel Pint (formatting)
- Larastan (static analysis)
- Pest (tests)
- ESLint + TypeScript

### `laravel-api`
Laravel REST API con:
- Rector
- Laravel Pint
- Larastan
- Pest
- API Tests

## 💡 Workflow

### Commit veloci (WIP)
```bash
git commit -m "wip: work in progress" --no-verify
```

### Commit finali (con tutti i check)
```bash
git commit -m "feat: nuova feature [issue: #123]"
```

## 🔄 Aggiornamento

Riscarica semplicemente il file di configurazione e rilancia:
```bash
pre-commit clean
pre-commit install
```

## 🤝 Contributi

PR benvenute! Testa le modifiche con:
```bash
pre-commit try-repo . <hook-id> --verbose --all-files
```

## 📝 License

MIT
