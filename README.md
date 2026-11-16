# RecallsNearMe plugins

Version 1.4.0. Live QA release; marketplace approval is separate.

This repository contains only the MIT-licensed client packages. The hosted application and backend are private.

## Cursor

Open Customize > Plugins > Add > From GitHub Repository and enter dbaMedia/recallsnearme-plugins. Install recallsnearme, then authenticate its MCP connection. If you previously configured the same server manually, remove that duplicate RecallsNearMe entry to let Cursor use the package connection. Do not remove other servers.

## Claude Code

Run `claude plugin marketplace add dbaMedia/recallsnearme-plugins`, then `claude plugin install recallsnearme@recallsnearme-plugins`. In Claude Code, use `/mcp` to authenticate the server. The native package is in plugins/claude.

## ChatGPT and Codex

The OpenAI package is in plugins/openai. Public directory availability requires OpenAI review. For developer-mode QA, add https://recallsnearme.com/mcp with OAuth and Dynamic Client Registration (DCR). You do not need a client ID or secret.

## New-user QA

1. Install and connect from a clean host session.
2. Create a new RecallsNearMe account on the website, then approve the connection. Eligible accounts receive five VIN trial credits once.
3. Ask "Check this VIN: 1HGCM82633A004352". It should start directly with no second conversational confirmation. Also attach examples/review-preview.csv and ask "Check this CSV", or paste its VIN column and ask to check it; both should validate one unique valid VIN, one duplicate and one invalid row, costing at most one credit. Read the saved result for free. Chat batches accept up to 1,000 rows and 256 KB CSV. The host must expose the attachment text; unreadable or oversized files must never be silently truncated.
4. After all five trial credits are used, a new run must be blocked. Reconnecting must not grant another trial.
5. Open the RecallsNearMe workspace, choose an API plan under Plans & billing, and review Stripe checkout. Complete payment only with account-owner approval. A checkout return alone never grants credits.
6. After the signed paid invoice is processed, read the funded balance from the same connected assistant and ask to check the next batch.

Audits and recurring monitoring require separate explicit approval. No purchase or subscription is initiated by connecting. Do not use a shared owner login for QA.

Website: https://www.recallsnearme.com
Privacy: https://www.recallsnearme.com/privacy-policy
Support: https://www.recallsnearme.com/contact
