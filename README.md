# Mini Tool Factory

**Mini Tool Factory** turns a supported calculator request into a transparent **declarative JSON tool definition** and runs that definition through a controlled local interpreter. It is a portable local application with no required AI service, no account, and no hosted website URL.

> **Safety boundary:** Generated content is never evaluated as JavaScript, shell code, or a free-form formula language. The runtime only accepts validated calculator specifications built from an allow-listed expression tree: constants, declared inputs, arithmetic, powers, and square roots.

## What the MVP generates

The prompt matcher is intentionally deterministic. It supports the following calculator families, while a template picker makes each result reviewable before use.

| Request family | Definition output | Example |
|---|---|---|
| Balanced three-phase real power | Inputs, units, formula, validation, output, worked example, and test case | `Create a three-phase power calculator` |
| Ohm’s-law voltage | Current/resistance calculator definition | `Create an Ohm's law voltage calculator` |
| Celsius to Fahrenheit | Temperature conversion definition | `Convert Celsius to Fahrenheit` |
| Rectangle area | Same-unit length/width calculator definition | `Create a rectangle area calculator` |

Every generated definition contains a specification version, slug ID, description, exact input units, input bounds, a controlled expression tree, output metadata, and deterministic test cases. Unsupported requests are rejected with a clear message rather than guessed, executed, or sent to an external service.

## Local Linux and Windows use

Install **Node.js 22+** and pnpm. The browser report is generated locally and its configurable preview server binds to `127.0.0.1` only.

| Task | Linux / macOS shell | Windows PowerShell or Command Prompt |
|---|---|---|
| List safe templates | `./run-local.sh templates` | `run-local.cmd templates` |
| Generate definition JSON | `./run-local.sh generate --prompt "Create a three-phase power calculator"` | `run-local.cmd generate --prompt "Create a three-phase power calculator"` |
| Run controlled preview | `./run-local.sh run --prompt "Create a three-phase power calculator" --input lineVoltage=400 --input lineCurrent=10 --input powerFactor=.8` | `run-local.cmd run --prompt "Create a three-phase power calculator" --input lineVoltage=400 --input lineCurrent=10 --input powerFactor=.8` |
| Generate local browser workbench | `./run-local.sh demo --out reports/demo` | `run-local.cmd demo --out reports\demo` |
| Serve local report | `./run-local.sh serve reports/demo --port=4080` | `run-local.cmd serve reports\demo --port=4080` |

Choose any unused port by changing `--port`. The browser workbench exports only the selected declarative JSON definition; it does not export executable code.

## Controlled specification model

The schema rejects unknown expression operations, inputs not declared by the specification, duplicate input keys, missing metadata, invalid numeric bounds, non-finite examples, and oversized or deeply nested structures. The runtime validates all submitted preview inputs before interpreting the expression tree and rejects division by zero, square roots of negative values, and non-finite results.

The displayed formula is explanatory text, not executable syntax. Review it, its units, input ranges, and stated use case before relying on a generated definition. This project does not provide engineering certification, safety analysis, standards compliance, measurements, persistence, user accounts, network access, or arbitrary utility generation.

## Validation

```bash
pnpm install
pnpm test
pnpm check
pnpm demo
```

The automated suite covers deterministic generation, schema validation, invalid-specification rejection, controlled calculator execution, deterministic test cases, and the browser report’s form/export safety contract.

## License

MIT.

## Live Render Demo

A responsive, synthetic/demo report is available at [https://mini-tool-factory.onrender.com](https://mini-tool-factory.onrender.com). The hosted view is read-only and preserves the repository's documented local-first boundaries.

<!-- render-live-url:https://mini-tool-factory.onrender.com -->
