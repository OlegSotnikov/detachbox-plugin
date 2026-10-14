# detachbox

Your coding agents keep working while you are away from the keyboard. This plugin puts them in your assistant's hands: ask what every detachbox terminal is doing, answer the agent that waits for you, hand the next task to the one that finished, start a terminal with a task, and read a file of your project. By text, or by voice from your phone.

It works in Claude (claude.ai, Cowork, Claude Code) and in Grok Build. It connects your assistant to your detachbox account's MCP server and adds two skills that teach it to drive agents well:

- **drive-agents**: the overview, answering an agent's question with the exact choice, giving the next task, stopping and steering, restarting, switching an agent's account, reading files.
- **watch-terminals**: following events (an agent waits, finished, stopped), checking what changed since last time, and standing rules for what the assistant may approve for you.

## What you need

A detachbox account with a running Compute and at least one project. The plugin reaches only what you see on **Terminals** in the [detachbox dashboard](https://my.detachbox.com).

## Connect

1. Install the plugin. On claude.ai and in Cowork, open the plugin's **Connectors** tab and connect detachbox. Claude Code and Grok Build connect to `https://api.detachbox.com/mcp` on their own; in Claude Code, run `/mcp` to sign in.
2. A detachbox page opens. Check the app's name and press **Allow access**.
3. Ask: "What are my detachbox terminals doing?"

Disconnect any time on [Assistants](https://my.detachbox.com/assistants) in the dashboard: access stops at once.

## What it runs, sends and fetches

- The plugin ships two Markdown skills and one MCP server entry. It runs no code on your machine: no hooks, no scripts, no local servers, no packages to install.
- Its one network endpoint is the detachbox MCP server, `https://api.detachbox.com/mcp`, over HTTPS. Sign-in is OAuth 2.1 with PKCE on `api.detachbox.com`, with the consent page on `my.detachbox.com`. The plugin holds no keys or tokens; your assistant keeps the sign-in.
- Your assistant sends detachbox the arguments of each tool call: a terminal or project name, the choice you picked, the message for an agent, the path of a file to read.
- detachbox answers with what you see in the dashboard: terminal names and states, what the agents said and ask, their last steps and screen lines, preview addresses, account labels and limits, and the contents of the files you ask to read. Those answers become part of your conversation with the assistant.

Every change the assistant makes is recorded in your account's activity log as yours, made through that assistant.

## Privacy and support

- Privacy policy: https://detachbox.com/privacy
- Terms: https://detachbox.com/terms
- Security: https://detachbox.com/security
- Guide: https://detachbox.com/docs/assistants
- Support: https://detachbox.com/contact or support@detachbox.com
