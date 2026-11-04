# Pageree agent plugin

<img src="assets/logo.svg" alt="Pageree" width="64" height="64">

Pageree lets your AI assistant publish landing pages that collect leads, then read how visitors behave and improve each page with you.

This plugin connects your assistant to Pageree's hosted server and adds the Landing Page Guru skill, which guides the offer, copy, design, forms and measurement of a page.

## Requirements

- A [Pageree account](https://console.pageree.com/signup).
- Internet access to `https://mcp.pageree.com/`.

Pageree hosts the MCP service. There is no API key to copy. You sign in through your browser the first time your assistant connects. Pageree service usage is subject to your account plan.

## Install

### Claude Code

```sh
claude plugin marketplace add Pageree/agent-plugin
claude plugin install pageree@pageree
```

### Kiro

In the Powers panel, choose **Add Custom Power**, then **Import power from GitHub**, and enter `https://github.com/Pageree/agent-plugin`.

### Antigravity

```sh
git clone https://github.com/Pageree/agent-plugin
agy plugin install ./agent-plugin
```

### Gemini CLI

```sh
gemini extensions install https://github.com/Pageree/agent-plugin
gemini extensions list
```

Inside Gemini, run `/mcp auth pageree` and finish the browser sign-in. The manifest uses `httpUrl` to select Streamable HTTP. Details and testing are in [RELEASE.md](RELEASE.md).

## Verify the connection

Ask your assistant:

> Use Pageree to call whoami and list_pages. Do not create, change, or publish anything.

Confirm that the account is correct and both calls succeed. A new account can have an empty page list.

The endpoint ends at `/`. Do not append `/mcp` or `/sse`.

## Example prompts

**Create a draft**

> Use Pageree to create a landing page for my product. Start by asking about the product, audience, and desired action. Show me a draft preview before publishing.

**Publish a reviewed draft**

> Publish the Pageree draft I just approved to the subdomain we chose.

**Improve a page**

> Use Pageree to review my page's analytics and suggest improvements supported by the data. Wait for my approval before editing or publishing.

Publishing makes a page public, so review the preview and confirm the destination before asking the agent to publish.

## Package contents

| Path | For |
| --- | --- |
| `plugin.json`, `mcp.json` | Agent Plugins clients, such as Kiro and GitHub Copilot |
| `.claude-plugin/`, `.mcp.json` | Claude Code and its marketplaces, and Grok Build |
| `.antigravity-plugin/`, `mcp_config.json` | Antigravity |
| `gemini-extension.json` | Gemini CLI |
| `skills/landing-page-guru-skill/` | The Landing Page Guru skill, copied unchanged from [Pageree/landing-page-guru-skill](https://github.com/Pageree/landing-page-guru-skill) at commit `f756e9a` (0.1.0) |
| `assets/logo.svg` | Pageree logo |
| `RELEASE.md` | Gemini CLI testing and gallery checklist |

The skill includes optional local helper scripts for testing form flows and event data. This package contains no hooks, server runtime or credentials. Tool requests go to the hosted Pageree service, and your assistant's client manages the sign-in.

## Links

- [Pageree setup documentation](https://pageree.com/docs)
- [Pageree dashboard](https://console.pageree.com/)
- [Privacy](https://pageree.com/privacy) · [Terms](https://pageree.com/terms)
- Support: [support@pageree.com](mailto:support@pageree.com)

## License

MIT. See [LICENSE](LICENSE).
