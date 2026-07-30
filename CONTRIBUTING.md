# Contributing to OpenBare

Thank you for your interest in contributing to OpenBare! This document provides guidelines and instructions for contributing.

## 🌟 Ways to Contribute

### 1. Run a Public Node

The easiest way to contribute is by running a public node:

```bash
cd server
npm install
NODE_URL=https://your-domain.com REGISTRY_URL=http://localhost:3000 npm start
```

### 2. Report Bugs

Found a bug? Please [open an issue](https://github.com/nirholas/openbare/issues/new?template=bug_report.md) with:

- Clear description of the problem
- Steps to reproduce
- Expected vs actual behavior
- Environment details (Node.js version, OS, etc.)

### 3. Suggest Features

Have an idea? [Open a feature request](https://github.com/nirholas/openbare/issues/new?template=feature_request.md) with:

- Clear description of the feature
- Use case / problem it solves
- Proposed implementation (optional)

### 4. Submit Code

#### Setup Development Environment

```bash
# Fork and clone the repo
git clone https://github.com/YOUR-USERNAME/openbare.git
cd openbare

# Install dependencies
npm install

# Start in development mode
npm run dev:server
```

#### Coding Standards

- Use ES modules (`import`/`export`)
- Follow existing code style
- Add JSDoc comments for public APIs
- Write meaningful commit messages

#### Pull Request Process

1. Create a feature branch: `git checkout -b feature/my-feature`
2. Make your changes
3. Test thoroughly
4. Commit with clear messages
5. Push and open a PR
6. Wait for review

### 5. Improve Documentation

- Fix typos or unclear explanations
- Add examples
- Translate to other languages
- Improve README or guides

## 📁 Project Structure

```
openbare/
├── server/           # Node.js bare server
│   ├── index.js      # Main entry point
│   ├── config.js     # Configuration
│   ├── metrics.js    # Metrics collection
│   ├── health.js     # Health checks
│   └── register.js   # Registry client
│
├── client/           # JavaScript client library
│   └── src/
│       ├── index.js       # Main client
│       ├── server-pool.js # Server management
│       ├── bare-fetch.js  # Bare protocol fetch
│       └── discovery.js   # Registry discovery
│
├── edge/             # Cloudflare Workers
│   └── src/
│       ├── index.js         # Worker entry
│       ├── bare-protocol.js # Protocol impl
│       └── websocket.js     # WS handling
│
├── registry/         # Node registry service
│   ├── index.js      # Main server
│   ├── db.js         # SQLite database
│   └── health-checker.js # Node health checks
│
└── docs/             # Documentation
```

## 🧪 Testing

```bash
# Run all tests
npm test

# Run specific workspace tests
npm test -w server
npm test -w client
```

## 📝 Commit Messages

Follow [Conventional Commits](https://www.conventionalcommits.org/):

```
feat: add automatic failover to client
fix: resolve memory leak in metrics
docs: update deployment guide
chore: upgrade dependencies
```

## 🔍 Code Review

All PRs require review. Reviewers look for:

- Code quality and style
- Test coverage
- Documentation
- Security implications
- Performance impact

## 📜 Code of Conduct

Be respectful and inclusive. We follow the [Contributor Covenant](https://www.contributor-covenant.org/).

## ❓ Questions?

- Open a [Discussion](https://github.com/nirholas/openbare/discussions)
- Ask in issues

Thank you for contributing! 🎉

## Code of Conduct

Please read and follow our [Code of Conduct](CODE_OF_CONDUCT.md).
