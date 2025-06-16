# Contributing to ReactNeuralEngine

Thank you for your interest in contributing to ReactNeuralEngine! We welcome contributions from everyone.

## Table of Contents

- [Getting Started](#getting-started)
- [How to Contribute](#how-to-contribute)
- [Development Setup](#development-setup)
- [Pull Request Process](#pull-request-process)
- [Code Style Guidelines](#code-style-guidelines)
- [Reporting Bugs](#reporting-bugs)
- [Suggesting Features](#suggesting-features)

## Getting Started

1. Fork the repository on GitHub
2. Clone your fork locally
3. Create a new branch for your feature or bugfix
4. Make your changes
5. Test your changes
6. Submit a pull request

## How to Contribute

### Types of Contributions

- **Bug Reports**: Help us identify and fix issues
- **Feature Requests**: Suggest new functionality
- **Code Contributions**: Fix bugs or implement new features
- **Documentation**: Improve our documentation
- **Testing**: Help improve test coverage

## Development Setup

1. **Prerequisites**:
   - Node.js (>= 14.0.0)
   - npm (>= 6.0.0)
   - Git

2. **Clone and Setup**:
   ```bash
   git clone https://github.com/skynetbee/ReactNeuralEngine.git
   cd ReactNeuralEngine
   npm install
   ```

3. **Development Commands**:
   ```bash
   npm start          # Start development server
   npm run build      # Build for production
   npm test           # Run tests
   npm run lint       # Check code style
   npm run lint:fix   # Fix code style issues
   npm run format     # Format code with Prettier
   ```

## Pull Request Process

1. **Before Starting**:
   - Check if there's already an issue for your contribution
   - If not, consider creating one to discuss the change

2. **Making Changes**:
   - Create a new branch: `git checkout -b feature/your-feature-name`
   - Make your changes in logical, atomic commits
   - Follow our code style guidelines
   - Add tests for new functionality
   - Update documentation as needed

3. **Before Submitting**:
   - Run tests: `npm test`
   - Check linting: `npm run lint`
   - Format code: `npm run format`
   - Update CHANGELOG.md if applicable

4. **Submitting**:
   - Push your branch to your fork
   - Create a pull request with a clear title and description
   - Reference any related issues
   - Be prepared to make changes based on feedback

## Code Style Guidelines

- **JavaScript/React**:
  - Use functional components with hooks
  - Use ESLint configuration provided
  - Follow React best practices
  - Use meaningful variable and function names

- **Formatting**:
  - Use Prettier for code formatting
  - 2 spaces for indentation
  - Semicolons required
  - Single quotes for strings

- **Commits**:
  - Use conventional commit format: `type(scope): description`
  - Types: feat, fix, docs, style, refactor, test, chore
  - Keep commit messages clear and concise

## Reporting Bugs

When reporting bugs, please include:

1. **Bug Description**: Clear description of the issue
2. **Steps to Reproduce**: Detailed steps to reproduce the bug
3. **Expected Behavior**: What you expected to happen
4. **Actual Behavior**: What actually happened
5. **Environment**:
   - OS and version
   - Node.js version
   - Browser (if applicable)
6. **Screenshots**: If applicable
7. **Additional Context**: Any other relevant information

## Suggesting Features

When suggesting features, please include:

1. **Feature Description**: Clear description of the proposed feature
2. **Use Case**: Why this feature would be useful
3. **Implementation Ideas**: Any thoughts on how it could be implemented
4. **Alternatives**: Any alternative solutions you've considered
5. **Additional Context**: Any other relevant information

## Code of Conduct

Please note that this project is released with a [Code of Conduct](CODE_OF_CONDUCT.md). By participating in this project you agree to abide by its terms.

## Questions?

If you have questions about contributing, feel free to:

- Open an issue for discussion
- Contact the maintainers
- Check existing issues and pull requests

Thank you for contributing to ReactNeuralEngine! 🚀

