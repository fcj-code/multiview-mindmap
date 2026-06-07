# Multiview Mindmap

[中文文档](./Readme-zh.md)

An interactive mindmap plugin with bidirectional Markdown synchronization, multiple structural views, AI-assisted editing, and slideshow export.


## Features

- **Bidirectional Markdown sync** — edits in the mindmap reflect in Markdown and vice versa.
- **Multiple views** — Basic mindmap, FolderView (from directory structure), TagView (from tags), and CoTView (chain-of-thought outline).
- **Focus view** — deterministic partitioned layout centered on a selected node, showing parents, children, links, tags, and siblings in fixed regions.
- **AI integration** — expand or decompose nodes with AI; chat-based brainstorming panel. (Requires an API key and contacts an OpenAI-compatible endpoint.)
- **Slide presentation** — generate presentation decks from mindmap structure, with AI-assisted slide generation and style presets.
- **Export** — export to PNG, JPEG, HTML, Canvas, Excalidraw, or Markdown.
- **Import** — import OPML and XMind files.
- **Rich node editing** — inline editing, drag-and-drop reordering, copy/paste, find-and-replace, tags, outlinks between nodes.
- **Undo/redo** — full command history for mindmap operations.
- **Laser pen** — freehand laser drawing for presentations and focus sessions.
- **Multi-language** — supports English, 中文, 日本語, 한국어, Deutsch, Español, Français, Italiano, Português, Русский, العربية, and more.
- **Keyboard-driven** — full keyboard shortcut coverage for node creation, editing, navigation, and view toggling.

## Usage

Create a new mindmap via the command palette (`Ctrl/Cmd+P` → "Create new mindmap"), or add a `mm-view` frontmatter key to an existing Markdown file:

```markdown
---
mm-view: basic
---

# My Mindmap
## Branch 1
## Branch 2
```

Switch between mindmap and Markdown views with `Ctrl/Cmd+P` → "Toggle markdown/mindmap".

### Views

| View | Description |
|------|-------------|
| `basic` | Standard mindmap rendered from Markdown headings and lists. |
| `folderview` | Generates a mindmap from a vault folder structure. |
| `tagview` | Generates a mindmap from tags across your vault. |
| `cotview` | Chain-of-thought outline view. |

Set the view via frontmatter (`mm-view: folderview`) or the command palette.

### Keyboard Shortcuts

| Action | Shortcut |
|--------|----------|
| New child node | `Tab` |
| New sibling node | `Enter` |
| Delete node | `Delete` |
| Edit node | `Space` / double-click |
| Undo | `Ctrl/Cmd+Z` |
| Redo | `Ctrl/Cmd+Y` |
| Exit edit | `Tab` |
| Expand/collapse node | `Ctrl/Cmd+/` |
| Navigate nodes | Arrow keys |
| Move node | Drag and drop |
| Zoom in/out | `Ctrl/Cmd` + mouse wheel |
| Center mindmap | `Ctrl/Cmd+E` |

## AI Features

This plugin can send node content to an OpenAI-compatible API for AI-powered node expansion, task decomposition, and chat-based brainstorming.

- **Network usage**: AI features contact the configured API endpoint (`https://api.openai.com/v1` by default, configurable in settings). The plugin sends the selected node text and surrounding file context as prompts. No vault data is sent beyond the current file's content.
- **Requirements**: You must provide your own API key and configure the endpoint in plugin settings. No account with the plugin author is required for AI features.
- **API key storage**: The API key is stored locally in Obsidian's plugin data and is never sent to any server other than the configured API endpoint.

## Licensing

Some features require a paid license. The license is verified via a remote license server.

- **License server**: When you activate or refresh a license, the plugin contacts the configured license server. The following data is sent: license key, device identifier, device name, and app version. No vault content is transmitted during license operations.
- **Offline grace period**: Licensed features remain available for a limited grace period without network access before requiring an online refresh.
- **Free features**: Basic mindmap editing, Markdown sync, keyboard shortcuts, undo/redo, and view toggling are available without a license.

## Installation

### From Obsidian Community Plugins

1. Open Settings → Community Plugins.
2. Search for "Multiview Mindmap".
3. Install and enable.

### Manual Installation

1. Download the latest release from [GitHub Releases](https://github.com/fcj-code/multiview-mindmap/releases).
2. Extract the folder into `<vault>/.obsidian/plugins/`.
3. Reload Obsidian.
4. Enable the plugin under Settings → Community Plugins → Installed plugins.

## Third-Party Libraries

This plugin bundles the following open-source libraries:

- [markmap-lib](https://github.com/markmap/markmap) (MIT) — Markdown-to-mindmap rendering
- [KaTeX](https://katex.org/) (MIT) — Math formula rendering
- [svg.js](https://svgjs.dev/) (MIT) — SVG manipulation
- [JSZip](https://stuk.github.io/jszip/) (MIT) — XMind import support
- [TweetNaCl](https://tweetnacl.js.org/) (Public Domain) — License signature verification
- [randomcolor](https://randomcolor.lllllllllllllllll.com/) (MIT) — Node color generation

## Support

- [GitHub Issues](https://github.com/fcj-code/multiview-mindmap/issues)


## License

GPL © fcj01
