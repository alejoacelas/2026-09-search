# Find

Scope: a keyword search prototype over Simple English Wikipedia, served from the agent
server to devices on the tailnet at http://agent-server/. [README.md](README.md) covers
the data, behaviour and rebuild steps.

- Visibility: public. The corpus is a public Wikimedia export; no personal data.
- Still running: `search.service`, a user service of `alejo` on the agent server, runs a
  copy of this source from `~/.local/share/agent-server-search/` on `127.0.0.1:8765`.
  Tailscale Serve proxies tailnet HTTP port 80 to it. Deploy by copying the files there
  as the README shows, then `systemctl --user restart search.service`.
- The server itself is documented in
  [`~/best/stash/agent-server`](/Users/alejo/best/stash/agent-server/docs/setup.md).

On 2026-10-03, 18 requests from the Mac had a 43 ms median total time and 4 ms median
server search time; the slowest took 477 ms. A one-letter query took about 298 ms,
188 ms of it searching. The UI shows timing for every query.
