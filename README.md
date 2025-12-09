[![Run Tests](https://github.com/lee-optiseis/version_test/actions/workflows/test.yml/badge.svg)](https://github.com/lee-optiseis/version_test/actions/workflows/test.yml)

# Version Test

A repository demonstrating automated semantic versioning based on pull request conventions.

## Overview
This project uses automated version bumping to manage releases. The version is stored in `version.yml` and automatically updated based on PR titles and labels following semantic versioning principles.

## How Version Bumping Works

Version changes are automatically determined based on your PR title and labels:

- **major** label → Major version bump (e.g., 1.0.0 → 2.0.0)
- **feat:** prefix → Minor version bump (e.g., 1.0.0 → 1.1.0)
- **fix:** prefix → Patch version bump (e.g., 1.0.0 → 1.0.1)
- Other titles → Patch version bump (default)

### Semantic Versioning

This project follows [Semantic Versioning 2.0.0](https://semver.org/):

- **MAJOR** version: Incompatible API changes or breaking changes
- **MINOR** version: New functionality in a backwards-compatible manner
- **PATCH** version: Backwards-compatible bug fixes

## Usage

### PR Title Conventions

Format your PR titles using conventional commits:

```
feat: add new user authentication
fix: resolve memory leak in data processing
docs: update installation instructions
refactor: simplify configuration logic
```

### Labels

Apply the `major` label to PRs that introduce breaking changes:

- Removing or renaming public APIs
- Changing function signatures
- Modifying configuration formats in incompatible ways
- Any change that requires users to update their code

## Examples

| PR Title | Label | Current Version | New Version |
|----------|-------|----------------|-------------|
| `feat: add dark mode support` | none | 1.2.3 | 1.3.0 |
| `fix: correct timezone handling` | none | 1.2.3 | 1.2.4 |
| `refactor: update API endpoints` | major | 1.2.3 | 2.0.0 |
| `chore: update dependencies` | none | 1.2.3 | 1.2.4 |
| `Breaking change: remove legacy API` | major | 1.2.3 | 2.0.0 |

## Repository Structure

```
├── README.md       # This file
├── version.yml     # Current version configuration
└── test.cpp        # Sample code file
```

## Version Configuration

The current version is stored in `version.yml`:

```yaml
{
  major: 0,
  minor: 0,
  patch: 0
}
```

## Best Practices

1. **Be Consistent**: Always use conventional commit prefixes in PR titles
2. **Document Breaking Changes**: Clearly describe breaking changes in PR descriptions
3. **Use Major Label Carefully**: Only apply the `major` label for true breaking changes
4. **Review Before Merge**: Ensure the version bump matches the scope of changes

## Contributing

When submitting a pull request:

1. Choose an appropriate PR title following conventional commits
2. Add the `major` label if your changes are breaking
3. Ensure all tests pass
4. Document significant changes in the PR description

## License

This is a test repository for demonstrating version management workflows.
