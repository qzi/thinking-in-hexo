# Thinking in Hexo

I’m not sure whether it will become the next generation of static site generators — I’m just thinking how it could be improved.  

## Current Pain Points

- **No ESM support**: Hexo's plugin system is built on legacy CommonJS (`vm.runInThisContext`), forcing all plugins to use CJS style
- **Slow builds**: npm install + tsc takes ~45 seconds, mostly waiting on I/O

## Proposed Improvements

### 1. Switch from npm to bun
- Build time: 45s → 2s (22x faster)
- Already validated on `hexo-v7-bun` and `main` branches

### 2. Refactor from CJS to ESM
- Modernize `loadPlugin()` to support dynamic `import()`
- Allow plugins to use native ES modules
- Better tree-shaking and static analysis

### 3. AI-Native Features
- Agent-friendly APIs for content generation
- Structured output formats for LLM integration
- Hook system for AI-assisted workflows

## Roadmap

- [x] Validate bun compatibility
- [ ] ESM plugin loader prototype
- [ ] AI integration design doc
