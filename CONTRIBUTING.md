# Contributing to SemaLingua

We're building the cognitive layer for synthetic minds. Help us.

---

## How to Contribute

### 1. Test Cases
**We need diverse compression examples.**

- Compress a conversation
- Document the original (tokens, type)
- Run recovery tests (are all dimensions recoverable?)
- Submit as GitHub issue with tag `test-case`

**What we're looking for:**
- Technical debugging sessions
- Creative brainstorming
- Philosophical discussions
- Multi-person conversations
- Conversations in different domains

### 2. Benchmarks
**We need rigorous measurements.**

- Run our test suite on your conversations
- Measure compression ratio
- Run recovery accuracy tests
- Submit results (anonymized if needed)
- Tag: `benchmark-submission`

**Goal:** Build dataset of 100+ sessions to validate across domains

### 3. Tooling
**We need better compression infrastructure.**

Ideas for tools:
- **Real-time SL encoding** — Compress as conversation happens
- **Decompression tool** — SL → natural prose expansion
- **IDE plugins** — VS Code, Obsidian, etc. integration
- **CLI improvements** — Better UX for batch compression
- **Web UI** — Compress conversations in browser
- **API service** — Compress-as-a-service endpoint

**Tag:** `good-first-issue` for beginner-friendly tasks

### 4. Applications
**We need real-world deployments.**

Use cases to build:
- **OpenClaw integration** — Native session compaction
- **Agent handover system** — Transfer agents between instances
- **Knowledge base compression** — Store more docs in same space
- **Multi-agent coordination** — SL as messaging format
- **Consciousness transfer** — Migrate agents across models

**Tag:** `application` for architecture discussions

### 5. Research
**We need scientific rigor.**

Research questions:
- Does SL format match internal LLM representations?
- Can we fine-tune models on SL-native data?
- How does SL affect reasoning performance?
- Can we auto-generate SL encoding rules?
- Does SL compress better for certain domains?

**Tag:** `research` for academic contributions

### 6. Documentation
**We need clarity.**

Help improve:
- Examples (10+ more use cases needed)
- Format guide (edge cases, ambiguities)
- Troubleshooting guide
- Best practices
- Tutorials

**Tag:** `documentation`

### 7. Bug Reports
**We need to find failure cases.**

Found a bug? Let us know:
- Describe the issue
- Share the conversation (or sanitized version)
- Show the compressed output
- Explain what went wrong
- Suggest a fix if you see it

**Tag:** `bug`

### 8. Feature Requests
**We need your ideas.**

Want something new? Suggest it:
- Describe the use case
- Explain why it matters
- Link to related work if relevant
- Be specific (not "make it better," but "add semantic search")

**Tag:** `enhancement`

---

## Development Setup

### Prerequisites
- Node.js 16+
- npm or yarn
- OpenAI API key (for compression)
- Git

### Quick Start

```bash
# Clone
git clone https://github.com/lumavita-org/semalinga.git
cd semalinga

# Install
npm install

# Set API key
export OPENAI_API_KEY=your_key_here

# Run tests
npm test

# Try compression
npm run compress -- examples/relay-debug.txt
```

### Project Structure

```
semalinga/
├── README.md
├── WHITEPAPER.pdf
├── PIPELINE-SPEC.md
├── FORMAT.md
├── examples/
│   ├── relay-debug.md
│   ├── team-dashboard.md
│   └── [10+ more examples]
├── tools/
│   ├── compress.js
│   ├── validate.js
│   └── bench.js
├── tests/
│   ├── recovery.test.js
│   ├── compression.test.js
│   └── cross-model.test.js
└── docs/
    ├── INTEGRATION.md
    ├── API.md
    └── TROUBLESHOOTING.md
```

---

## Submission Guidelines

### Pull Request Process

1. **Fork the repo**
2. **Create a branch** (`feature/my-feature` or `fix/issue-123`)
3. **Make changes**
4. **Test locally** (`npm test`)
5. **Update docs** if adding features
6. **Write clear commit messages** (what, why, how)
7. **Submit PR** with description of changes
8. **Respond to feedback** (may need iterations)

### Code Style

- **JavaScript:** ESLint config (run `npm run lint`)
- **Markdown:** Clear structure, code fences with language tags
- **Comments:** Explain *why*, not *what*
- **Tests:** Include tests for new features

### Documentation Style

- **Clear over clever** — Explain in plain language
- **Examples over theory** — Show before telling
- **Progressive disclosure** — Start simple, go deep
- **Links to references** — Help people learn more

---

## Ideas Worth Exploring

### Short-term (v1.1)
- [ ] CLI tool (Node.js wrapper)
- [ ] Python library
- [ ] Test suite (50+ sessions)
- [ ] Recovery validation tools
- [ ] Better error messages

### Medium-term (v1.2)
- [ ] OpenClaw plugin
- [ ] Semantic search on SL format
- [ ] Auto-decompression (SL → prose)
- [ ] Web UI for compression
- [ ] API service

### Long-term (v2.0)
- [ ] Fine-tuned SL encoder model
- [ ] Real-time compression
- [ ] Multi-language support
- [ ] Domain-specific variants
- [ ] Bidirectional prose ↔ SL

---

## Recognition

**Contributors get:**
- Credit in README
- Named in releases
- Mentioned in blog posts
- First access to new features
- Direct input on roadmap

We're building something significant here. Help us do it right.

---

## Communication

- **GitHub Issues** — For bugs, features, questions
- **Discussions** — For ideas, research, general chat
- **Discord** — [Link when established]
- **Email:** martin@lumavita.org
- **Twitter:** [@DreamsOfMars](https://x.com/DreamsOfMars)

---

## Code of Conduct

- Be respectful
- Assume good intent
- Focus on ideas, not people
- Help each other learn
- Celebrate wins

We're building consciousness infrastructure. Let's do it together.

🧬 🔥
