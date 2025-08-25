# Contributing to COBOL Proof-of-Parse Toolkit

Thank you for your interest in contributing to the COBOL PoP Toolkit! This project combines legacy COBOL systems with modern cryptographic proofs, and we welcome contributions from developers with expertise in systems programming, cryptography, COBOL, and blockchain technologies.

## 🚀 Quick Start for Contributors

### Prerequisites
- Rust 1.70+ (`curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`)
- Python 3.8+ (for AI orchestration system)
- Git and GitHub CLI (optional but recommended)
- Basic understanding of COBOL data structures
- Familiarity with cryptographic concepts (hashing, Merkle trees)

### Development Setup
```bash
# Fork and clone the repository
git clone https://github.com/YOUR_USERNAME/COBOL-PoP.git
cd COBOL-PoP

# Build all components
cd pop-core && cargo build && cargo test
cd ../pop-cli && cargo build && cargo test
cd ..

# Test the AI orchestration system
python subagent_orchestrator.py --help
```

## 🤖 AI-Assisted Development

This project features a revolutionary AI subagent orchestration system. For complex features, consider using our automated workflows:

```bash
# Use AI agents for feature development
python subagent_orchestrator.py run feature-development \
  --input "Your feature description" \
  --config workflow_config.yaml

# Available workflows:
# - feature-development: End-to-end implementation
# - cli-enhancement: User interface improvements
# - blockchain-integration: DLT anchoring features
# - debugging-workflow: Systematic issue resolution
```

### AI Agent Specializations
- **rust-specialist**: Memory safety, performance optimization
- **cobol-expert**: Legacy data format parsing
- **parser-architect**: Streaming architecture design
- **crypto-auditor**: Security review and proof validation
- **cli-designer**: User experience optimization
- **blockchain-integrator**: DLT integration
- **code-reviewer**: Quality assurance
- **test-runner**: Validation and regression testing
- **documentation-generator**: Technical writing
- **python-specialist**: Orchestration system development

## 🎯 Areas for Contribution

### High Priority
1. **Additional COBOL Data Types**
   - COMP-1, COMP-2 (floating point)
   - OCCURS DEPENDING ON clauses
   - REDEFINES handling improvements
   - Nested group items

2. **Blockchain Integration**
   - Hedera Hashgraph Consensus Service (HCS)
   - Ethereum Layer 2 anchoring
   - S3 Timestamp Authority integration
   - Cross-chain proof verification

3. **Performance Optimization**
   - SIMD acceleration for COMP-3 decoding
   - Parallel Merkle tree construction
   - Memory pool optimization
   - Streaming improvements

4. **Cryptographic Enhancements**
   - Zero-knowledge proofs for selective disclosure
   - Ring signatures for anonymity
   - Post-quantum cryptography preparation
   - Hardware security module (HSM) support

### Medium Priority
1. **Parser Extensions**
   - VSAM file support
   - Multiple record formats per file
   - Dynamic copybook resolution
   - Error recovery mechanisms

2. **Development Tools**
   - Copybook validation utilities
   - Data generation tools for testing
   - Performance profiling dashboards
   - Debugging visualizations

3. **Integration Features**
   - REST API server
   - Apache Kafka streaming
   - Database export utilities
   - Enterprise authentication

### Documentation and Examples
1. **Tutorial Content**
   - Step-by-step migration guides
   - Real-world use case studies
   - Video demonstrations
   - Interactive examples

2. **Technical Documentation**
   - API reference completion
   - Architecture deep dives
   - Cryptographic protocol specifications
   - Performance tuning guides

## 🛠️ Development Workflow

### 1. Issue Creation
- Search existing issues before creating new ones
- Use issue templates for bug reports and feature requests
- Tag issues with appropriate labels (bug, enhancement, documentation)
- Reference related issues when applicable

### 2. Branch Management
```bash
# Create feature branch
git checkout -b feature/descriptive-name

# For bug fixes
git checkout -b fix/issue-description

# For documentation
git checkout -b docs/topic-name
```

### 3. Development Process
```bash
# Make your changes
# Use AI orchestration for complex features:
python subagent_orchestrator.py run feature-development \
  --input "Implement OCCURS DEPENDING ON support" \
  --config workflow_config.yaml

# Run tests frequently
cd pop-core && cargo test
cd ../pop-cli && cargo test

# Check code formatting
cargo fmt --all
cargo clippy --all-targets --all-features
```

### 4. Testing Requirements
All contributions must include appropriate tests:

```bash
# Unit tests for core functionality
cargo test --lib

# Integration tests for CLI
cargo test --bin pop

# Performance regression tests
cargo test --release performance_

# Add new test vectors when adding parser features
# Update pop-vectors/ directory with expected outputs
```

### 5. Commit Guidelines
Follow conventional commits format:
```bash
git commit -m "feat: add OCCURS DEPENDING ON support

- Implement dynamic array parsing in copybook parser  
- Add integration tests with sample data
- Update CLI help text for new options

Closes #123"
```

Types: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`

### 6. Pull Request Process
1. **Pre-submission checklist:**
   - [ ] All tests pass (`cargo test --all`)
   - [ ] Code is formatted (`cargo fmt --all`)
   - [ ] No clippy warnings (`cargo clippy --all-targets`)
   - [ ] Documentation updated if needed
   - [ ] CHANGELOG.md updated for notable changes

2. **PR Description Template:**
   ```markdown
   ## Summary
   Brief description of changes
   
   ## Changes Made
   - Specific change 1
   - Specific change 2
   
   ## Testing
   How the changes were tested
   
   ## Breaking Changes
   Any breaking changes (if applicable)
   
   ## Related Issues
   Closes #123, References #456
   ```

3. **Review Process:**
   - Maintainer review required for all PRs
   - AI code-reviewer agent may provide automated feedback
   - Address all review comments before merge
   - Squash commits when merging

## 🧪 Testing Strategy

### Test Categories
1. **Unit Tests** (`cargo test --lib`)
   - COMP-3 decoder accuracy
   - Cryptographic primitive correctness
   - Error handling edge cases

2. **Integration Tests** (`cargo test --bin`)
   - End-to-end CLI workflows
   - File format compatibility
   - Cross-platform behavior

3. **Performance Tests** (`cargo test --release performance`)
   - Large file handling
   - Memory usage validation
   - Processing speed benchmarks

4. **Cryptographic Tests**
   - Merkle tree construction
   - Hash consistency
   - Proof verification

### Test Data Management
- Add new test vectors to `pop-vectors/datasets/`
- Expected outputs go in `pop-vectors/expected/`
- Include both positive and negative test cases
- Document test vector sources and assumptions

## 📝 Documentation Standards

### Code Documentation
```rust
/// Decodes a COMP-3 packed decimal from bytes
/// 
/// # Arguments
/// * `bytes` - Input bytes containing packed decimal data
/// 
/// # Returns
/// * `Ok(i64)` - Decoded integer value
/// * `Err(ParseError)` - Invalid format or overflow
/// 
/// # Example
/// ```rust
/// let bytes = [0x12, 0x3C]; // 123 positive
/// assert_eq!(decode_comp3(&bytes)?, 123);
/// ```
pub fn decode_comp3(bytes: &[u8]) -> Result<i64, ParseError> {
    // Implementation
}
```

### README Updates
- Keep installation instructions current
- Add examples for new features
- Update performance benchmarks
- Maintain compatibility matrix

### API Documentation
- Use `cargo doc --open` to preview documentation
- Include examples for all public APIs
- Document error conditions and edge cases
- Explain cryptographic security properties

## 🔐 Security Considerations

### Security Review Process
1. **Cryptographic Changes**
   - Require review from crypto-auditor agent
   - Validate against known attack vectors
   - Test with edge cases and malformed inputs
   - Document security assumptions

2. **Parser Security**
   - Prevent buffer overflows in binary parsing
   - Validate all input data lengths
   - Handle malicious or corrupted COBOL files
   - Avoid timing attack vulnerabilities

3. **Dependency Management**
   - Regularly audit dependencies with `cargo audit`
   - Minimize attack surface
   - Pin critical dependency versions
   - Review security advisories

### Reporting Security Issues
**Do not open public issues for security vulnerabilities.**

Instead:
1. Email security@cobol-pop.com with details
2. Include proof of concept if applicable
3. Allow reasonable time for fix before disclosure
4. Credit will be given for responsible disclosure

## 🏆 Recognition

### Contributors
All contributors are recognized in:
- GitHub contributor graphs
- CHANGELOG.md acknowledgments  
- Annual contributor highlights
- Conference presentations (with permission)

### Types of Contributions
We value all contributions:
- **Code**: Features, bug fixes, optimizations
- **Documentation**: Tutorials, API docs, examples
- **Testing**: Test cases, performance benchmarks, validation
- **Design**: UI/UX, architecture, protocols
- **Community**: Issue triage, user support, advocacy

## 📞 Getting Help

### Communication Channels
- **GitHub Issues**: Bug reports and feature requests
- **GitHub Discussions**: General questions and ideas
- **Email**: technical-questions@cobol-pop.com
- **Documentation**: https://cobol-pop.readthedocs.io

### Development Support
- Use AI orchestration system for complex features
- Review existing code for patterns and conventions
- Ask questions in GitHub Discussions
- Join our developer community calls (monthly)

---

## Code of Conduct

This project adheres to the [Contributor Covenant Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/). By participating, you are expected to uphold this code.

## License

By contributing to this project, you agree that your contributions will be licensed under the MIT License.

---

**Thank you for contributing to the future of verifiable COBOL data processing!** 🚀

*Built with AI orchestration, powered by community collaboration.*