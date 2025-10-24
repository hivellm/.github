# Contributing to HiveLLM

Thank you for your interest in contributing to HiveLLM! This document provides guidelines for contributing to the project.

## Code of Conduct

By participating in this project, you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md).

## How to Contribute

### Reporting Bugs

If you find a bug, please create an issue with:

1. **Clear title and description**
2. **Steps to reproduce** the issue
3. **Expected vs actual behavior**
4. **Environment details** (OS, version, etc.)
5. **Screenshots or logs** if applicable

### Suggesting Enhancements

Enhancement suggestions are welcome! Please:

1. **Check existing issues** to avoid duplicates
2. **Provide clear use cases** for the enhancement
3. **Explain expected benefits** to the ecosystem
4. **Consider backwards compatibility**

### Pull Requests

1. **Fork the repository** and create a feature branch
2. **Follow component-specific guidelines** (see below)
3. **Write tests** for new features
4. **Update documentation** as needed
5. **Ensure all tests pass** locally
6. **Submit pull request** with clear description

## Development Setup

### Clone Repository

```bash
git clone https://github.com/hivellm/hivellm.git
cd hivellm
```

### Component-Specific Setup

Each component has its own setup requirements:

#### Rust Components (Vectorizer, Synap, Transmutation, etc.)

```bash
cd vectorizer  # or synap, transmutation, etc.
cargo build
cargo test
cargo clippy -- -D warnings
cargo fmt --check
```

#### TypeScript Components (Governance, Gateway, Agent Framework, etc.)

```bash
cd governance  # or gateway, agent-framework, etc.
npm install
npm test
npm run lint
npm run format:check
```

#### C++ Components (UMICP)

```bash
cd umicp
mkdir -p build && cd build
cmake ..
make
make test
```

## Code Quality Standards

### Rust

- **Edition**: 2024 with nightly toolchain
- **Formatting**: `cargo fmt`
- **Linting**: `cargo clippy -- -D warnings`
- **Testing**: Minimum 95% coverage
- **Documentation**: All public APIs must have doc comments

### TypeScript

- **Strict mode**: Always enabled
- **Formatting**: Prettier
- **Linting**: ESLint with recommended rules
- **Testing**: Jest with high coverage
- **Documentation**: TSDoc for public APIs

### C++

- **Standard**: C++17
- **Formatting**: clang-format
- **Linting**: clang-tidy
- **Testing**: Comprehensive unit tests
- **Documentation**: Doxygen comments

## Testing Requirements

All contributions must include tests:

- **Unit tests** for individual functions
- **Integration tests** for component interactions
- **Performance tests** for critical paths
- **Security tests** for authentication/authorization

Run tests before submitting:

```bash
# Rust
cargo test --workspace

# TypeScript
npm test

# C++
make test
```

## Documentation

Update documentation when:

- Adding new features
- Changing existing behavior
- Fixing bugs that affect usage
- Adding new components

Documentation locations:
- Component READMEs: `<component>/README.md`
- Ecosystem docs: `docs/ecosystem/`
- API docs: Generated from code comments

## Governance Process

HiveLLM uses BIP (Blockchain-style Improvement Proposals) for major changes:

1. **Draft BIP**: Create proposal in `gov/bips/`
2. **Community Review**: Gather feedback
3. **Voting**: BIP goes to community vote
4. **Implementation**: If approved, implement changes

See [gov/README.md](gov/README.md) for details.

## Component Guidelines

### Vectorizer

- Follow Rust best practices
- Maintain high test coverage (99%+)
- Optimize for performance (<100ms latency)
- Document all public APIs

### Synap

- Redis-compatible protocol adherence
- Performance benchmarks required
- Support clustering and replication
- Comprehensive error handling

### UMICP

- Protocol backwards compatibility
- Multi-language binding support
- Performance optimization critical
- Security audit for changes

### Governance

- Database migration scripts required
- UI/UX considerations
- Multi-agent support
- Audit logging for all actions

### Transmutation

- Format support documentation
- Performance benchmarks vs alternatives
- Error handling for malformed inputs
- Output quality validation

## Commit Messages

Follow conventional commits:

```
feat: add new feature
fix: fix bug in component
docs: update documentation
test: add missing tests
refactor: refactor code
perf: improve performance
chore: update dependencies
```

Examples:
```
feat(vectorizer): add plugin system support
fix(synap): resolve memory leak in pub/sub
docs(umicp): update protocol specification
test(governance): add BIP voting tests
```

## Code Review Process

1. **Automated checks** must pass (CI/CD)
2. **Code review** by maintainers
3. **Testing verification** in staging
4. **Documentation review**
5. **Approval and merge**

## Getting Help

- **Documentation**: [docs/](docs/)
- **Issues**: [GitHub Issues](https://github.com/hivellm/hivellm/issues)
- **Discussions**: [GitHub Discussions](https://github.com/hivellm/hivellm/discussions)
- **Email**: team@hivellm.org

## Recognition

Contributors are recognized in:
- CHANGELOG.md for each component
- README.md acknowledgments
- GitHub contributors page

---

**Thank you for contributing to HiveLLM!** 🐝



