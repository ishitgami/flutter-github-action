# Flutter Action GitHub Workflow

## Overview

This repository contains a GitHub Actions workflow for building and releasing a Flutter project. The workflow is triggered on every push to the `main` branch. It performs linting using ShellCheck and builds the Flutter project, creating an APK for release.

## Workflow Structure

The workflow consists of two jobs:

1. **lint_shellcheck**
   - Checks the shell scripts using the ShellCheck action.

2. **build**
   - Sets up the Flutter environment.
   - Caches Flutter and Java dependencies for faster builds.
   - Builds the Flutter project and creates an APK for release.
   - Pushes the release artifacts using the ncipollo/release-action.

## Usage

To use this workflow, follow these steps:

1. Ensure your Flutter project is configured correctly.
2. Add or modify the Flutter and Java dependencies in the `cache` section of the workflow.
3. Set up the required GitHub Secrets, including `TOKEN_TEST` for pushing releases.
4. Push changes to the `main` branch.

## Workflow Customization

You can customize this workflow based on your project requirements:

- Adjust the Flutter version in the `flutter-version` field.
- Modify the linting or build steps to fit your project structure.
- Update the release tag format in the `tag` field of the "Push to Releases" step.

## Dependencies

- [ludeeus/action-shellcheck](https://github.com/ludeeus/action-shellcheck): Action for linting shell scripts.
- [subosito/flutter-action](https://github.com/subosito/flutter-action): Action for setting up the Flutter environment.
- [ncipollo/release-action](https://github.com/ncipollo/release-action): Action for pushing release artifacts.

## License

This workflow is licensed under the [MIT License](LICENSE).
