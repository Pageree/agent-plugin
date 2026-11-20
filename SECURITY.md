# Security policy

This repository holds configuration only: a plugin manifest, the MCP server
address (`https://mcp.pageree.com/`) and the Landing Page Guru skill. It runs no
code of its own on install and has no dependencies. The skill's two optional
Node.js helpers run only when an agent calls them; the form helper uses an
existing Playwright installation and blocks live form submissions.

## Report a vulnerability

Email **privacy@pageree.com** with the affected component (this plugin, the
skill, or the hosted Pageree service), a safe description of the issue, when
you saw it, and how to reach you. Please don't open a public issue for a
vulnerability.

Don't access other people's data, disrupt the service, publish credentials or
send live personal data as proof. Stop testing when you reach someone else's
information, and contact us to agree a safe way to share sensitive evidence.
This policy doesn't authorize intrusive testing or offer a bug bounty. The full
policy is at https://pageree.com/abuse/#security.

## Supported versions

Only the latest commit on `main` is supported. Pageree hosts the MCP server, so
a fix there reaches every installation without an update.
