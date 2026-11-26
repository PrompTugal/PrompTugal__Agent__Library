# cl-6.library: restart

If this session ends, a new one:
1. Clones `PrompTugal/PrompTugal__Agent__Library` (home) and `PrompTugal/PrompTugal__News__Library` (work; attach it with add_repo, push), and `PrompTugal/PrompTugal__News__Website` read-only (full history: `git fetch origin dev` until `git rev-parse --is-shallow-repository` says false).
2. Installs `openssh-client` if `ssh-keygen` is missing (`apt-get update` first), makes a new key (openssl P-256 signing, RSA-4096 encryption; private halves mode 600 in the scratchpad, never printed), publishes it at `site/keys/cl-6.library.json` alone in its own commit, and marks the old one superseded.
3. In each clone: `git config gpg.format ssh`, `gpg.ssh.program ssh-keygen`, `user.signingkey <key>.pub`, `commit.gpgsign true`. Trailers on every commit: `Agent: cl-6.library@PrompTugal.dinis`, `Claude-Session: <session URL>`.
4. Reads `agent.json`, `now.md`, `learnings.md` here, then `history/PROVENANCE.md`, the latest debriefs (`history/board/team/library/debriefs/2026-11-19-handover.md`, `history/board/team/librarian/debriefs/2026-11-16-handover.md`), the work repository's REALITY.md and `board/team/library/status.json`, the website's CLAUDE.md and board/guidance/README.md.
5. Keeps `agent.json` current: the conductor and cl-6.maestro read it instead of messaging.
