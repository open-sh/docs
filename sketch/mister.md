# Gorilla Hands Version
Well, this shit got out of hand mostly. Blink's idea was born out of pure hatred for tools such as Swagger, and we wanted a way to document, test and verify endpoints easily.
The idea then expanded into deterministic simulation + enviroments, where one could declare it's entire "business logic" into a blink project, and we could have clear, standardized communication between all areas of a company - Well, the problem with this is that creating a language for such thing would be equivalent to actually programming the thing.

### Why?
Swagger + five wikis + tribal memory = we fucked at 3 AM.
Blink was born from rage against:
- Fragmented source truth – spec in Swagger, logic in code, diagrams in Draw.io, tests in Postman, SLOs in someone’s head.
- Spec ↔ Code drift – we ship, forget docs, and production reminds us the hard way.

We need one artifact that the entire fucking party can rely upon, grep, lint, diff and above all else, **trust**.

### What Blink is not
- Not another code-gen framework that shoves annotations into our source.
- Not a Turing-complete DSL that becomes a second backend to maintain.
- Not tied to any runtime, language, or infra stack.

### What Blink Is
- Graph file (blink.graph): A single TOML (or other file) doc listing services, routes, events, stores, invariants, scenarios. No code, nor YAML.
- Markdown embedding: We could drop that graph in a fenced block inside any .md or .org doc. Writers keep prose; machines parse the block.
- CLI: blink lint / gen / test / watch – lints the graph, spits OpenAPI + diagrams, spins stub servers, queries live metrics.

### To be decided
- Schema language – Could be TOML, HSL, or our own. I can't really consider options beyond this.
- Expression engine for invariants?
- Multi-file or monolith? How would the former work?

### Criterias of success 
1. Some junior runs `blink view` and quickly groks the entire system.
2. Someone is screaming less because invariants can be caught in CI, not prod.
3. Docs are up-to-date because they're an actual spec, not chore.
4. No one forgets about diagrams, for they become natural.
