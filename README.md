# buyer_intent_finder_new

## Environment merger utility

This repository includes `combine_envs.py`, a helper script that compares multiple `.env` files, highlights where their values match or differ, and writes a single combined `.env` file. The combined file keeps common values once and annotates keys that vary across environments.

### Quick start
1. Place your environment files anywhere in the repository (for example `dev.env`, `staging.env`, and `prod.env`).
2. Run the script, pointing it at each source file and an output path:

   ```bash
   python combine_envs.py dev.env staging.env prod.env -o combined.env
   ```

3. The script prints a short summary and writes `combined.env`. Varying keys include a comment showing the per-environment values while defaulting to the first source file's value.

### Example inputs
Sample environment files live in `env_examples/`:

- `env_examples/dev.env`
- `env_examples/staging.env`
- `env_examples/prod.env`

You can regenerate the provided `env_examples/combined.env` with:

```bash
python combine_envs.py env_examples/dev.env env_examples/staging.env env_examples/prod.env -o env_examples/combined.env
```

The generated `combined.env` captures shared values once and documents differences so you can see at a glance where environments diverge.
