## GitHub Actions Implementation Guidelines

- Always set the default shell to bash
- Group logs into meaningful units
- Always separate caches at least by OS and CPU architecture
  - example: `key: example-${{ runner.os }}-${{ runner.arch }}`
