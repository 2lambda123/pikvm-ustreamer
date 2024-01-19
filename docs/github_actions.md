name: CI

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Build and test
        run: |
          npm install
          npm test
```

3. Customize the workflow to fit your specific needs. You can add additional steps, specify different events that trigger the workflow, and configure environment variables.

## 2. Specifying Environment Variables
Environment variables are useful for storing sensitive information or configuration values that are required by your workflow. To specify environment variables, follow these steps:

1. Open your workflow file (`main.yml`).
2. Add an `env` section under the `jobs` section. Here's an example:

```yaml
jobs:
  build:
    runs-on: ubuntu-latest

    env:
      API_KEY: ${{ secrets.API_KEY }}
