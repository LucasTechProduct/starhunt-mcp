# StarHunt MCP server

Source software engineers from GitHub, from inside Claude, ChatGPT, Cursor, Claude Code or any other MCP client.

StarHunt is a **hosted remote MCP server**. Nothing to install, no API key to paste into a config file: your client connects over OAuth and you approve it once.

```
https://app.getstarhunt.com/mcp
```

## What it does

Most people search is keyword search over what someone wrote about themselves. StarHunt starts somewhere else: from the repositories that define a technology ecosystem, and from the people who actually merged code into them.

A developer is ranked on evidence of real work, never on follower count:

- contributions merged over the last twelve months
- the languages in their own repositories, not the ones they starred
- how widely their projects are used
- how recently they shipped

Locations are normalised to metro areas, so a search for Paris returns the Paris metro rather than only profiles whose bio says the word Paris.

## Tools

### `search_developers`

Find engineers by technology, role and location, or from a pasted job description. Returns public profile data, including the public email or LinkedIn each person chose to publish on their own profile.

Results are already filtered on the location asked for. A short list means the index holds no more people there, not that the search failed.

### `save_candidate`

Save a developer to your StarHunt pipeline, with a stage (`to_contact` or `contacted`), so you can follow up later.

### `list_pipeline`

List the developers already saved, optionally filtered by stage. Answers "who have I contacted" and "who is still waiting" without leaving the conversation.

## Setup

### Claude (web, desktop, mobile)

Settings, Connectors, Add custom connector, then paste:

```
https://app.getstarhunt.com/mcp
```

A StarHunt window opens to sign in and approve the connection. That is the whole setup.

### Claude Code

```
claude mcp add --transport http starhunt https://app.getstarhunt.com/mcp
```

### Cursor, ChatGPT and other clients

Add a remote MCP server with the same URL. Any client that supports Streamable HTTP and OAuth 2.1 works.

Full walkthrough with screenshots: https://www.getstarhunt.com/mcp.html

## Authentication

OAuth 2.1 with PKCE and dynamic client registration (RFC 7591), so a client that discovers the server can register itself without anyone issuing credentials by hand. Access can be revoked at any time from StarHunt settings.

Clients that cannot do OAuth can use a personal key in the URL instead. It is the degraded route and it is documented as such.

## Data

Public GitHub information only: profile, public repositories, languages, and the email or blog a developer chose to publish. Nothing is bought from a data broker and no private address is inferred.

Any developer can have their profile removed from the index from a public page, without an account: https://app.getstarhunt.com/remove

## Registry

Published to the official MCP registry as [`com.getstarhunt/github-developer-sourcing`](https://registry.modelcontextprotocol.io/v0/servers?search=starhunt). `server.json` in this repository is the manifest that describes the remote endpoint.

## Links

- Setup guide: https://www.getstarhunt.com/mcp.html
- How the index is built: https://www.getstarhunt.com/how-it-works.html
- State of Developer Reachability: https://www.getstarhunt.com/developer-reachability-report.html
- App: https://app.getstarhunt.com
