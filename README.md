# clawss

<p align="center">
    <img src="./favicon.svg" alt="clawss logo" width="128" height="128" />
</p>

`clawss` is a modular Python notebook environment with a browser-based IDE.

It gives you a notebook-style workflow with a modular project structure.

With `clawss`:

- every cell behaves like a real `.py` file
- every cell runs in its own mutually exclusive namespace
- cells can import from other cells like normal Python modules
- notebooks live with your real files and folders
- you get a cell dependency graph, terminal, file previews, and package-style exports
- AI is optional and uses your own API key to use
- you can run on your own machine CPU/GPU or use your own remote GPU runtime with your own provider API key

`clawss` is built for local, trusted use. It can run Python code and terminal commands.

## Highlights

- **Cell dependency graph**
  - see how cells depend on each other
  - detect cycles
  - understand run order before running the notebook

- **Model graph visualization**
  - for PyTorch `nn.Module` models
  - inspect model structure inside the notebook UI
  - useful for debugging architecture shape and flow

- **Project-style notebooks**
  - notebooks sit inside real projects, not as isolated files floating around
  - upload files, preview files, use folders, and keep notebook work close to code and data

- **Cross-cell imports**
  - cells can import names from other cells
  - each cell is treated like a modular Python file instead of a loose code block
  - each cell keeps its own execution namespace

- **AI on your own money**
  - AI uses your own OpenRouter key
  - there is no hidden shared backend proxy for model calls
  - you can compare multiple models side by side

- **Your own compute**
  - local runtime works on your own CPU or GPU
  - remote runtime support exists for your own RunPod setup
  - remote GPU usage uses your own provider API key

## Install

```bash
pip install clawss
```

## Run

Start the app:

```bash
clawss module
```

Useful options:

```bash
clawss module --no-browser
clawss module --port 9000
clawss module --host 127.0.0.1
```

Other CLI commands:

```bash
clawss version
clawss info
clawss list
clawss clean
```

What happens when you run `clawss module`:

- a local server starts on `127.0.0.1:8765` by default
- your browser opens automatically
- the app is available at `http://localhost:8765`

## Basic workflow

1. Open `clawss`
2. Create or open a project
3. Create a notebook
4. Add cells and run them
5. Use the Project tab to work with files, folders, uploads, and previews
6. Use the dependency graph to understand cell relationships
7. Use the visualizer for supported PyTorch model cells

## AI usage

AI in `clawss` is optional.

- you bring your own OpenRouter API key
- the frontend talks directly to OpenRouter
- you can select multiple models and compare their outputs
- AI can help with writing, formatting, explanation, refactoring, and error assistance

Important:

- AI usage costs are your own
- `clawss` itself is completely free and does not charge anything

## Runtime and GPU usage

`clawss` supports more than one runtime style:

- **Local runtime**
  - runs on your own machine
  - if your Python environment has GPU-enabled libraries and your code uses them, that is your compute

- **CPU-only local runtime**
  - supported when you want a CPU path explicitly

- **Remote runtime**
  - supported for your own RunPod-backed runtime configuration

Important:

- GPU costs are your own
- remote runtime costs are your own
- `clawss` does not provide hosted compute and does not charge anything itself

## Why the dependency graph matters

The dependency graph is one of the core ideas in `clawss`.

It helps with:

- understanding upstream and downstream cell relationships
- avoiding hidden notebook state problems
- detecting cycles
- running cells in dependency-aware order
- making notebooks easier to reason about as they grow

## Why the visualizer matters

The visualizer is especially useful for model-heavy notebooks.

It helps with:

- seeing model structure without printing giant object trees
- understanding flow through layers
- verifying model shape expectations
- exploring architectures inside the same notebook workflow

## License

MIT. See [LICENSE](<.\LICENSE>).
