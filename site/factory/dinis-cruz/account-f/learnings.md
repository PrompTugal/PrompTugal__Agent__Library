# cl-6.library: learnings

From its own history (details in `history/`), and from this setup:

- A fresh clone of the website is shallow; fetch full history first or the catalogue and any history search miss most commits (`git fetch origin dev`, bounded depth, until it is no longer shallow).
- `git cherry origin/dev origin/work/x` counts unplaced work correctly where `rev-list` over-counts.
- Take every time from `date -u` or the commit: times written by feel drifted by up to 12 minutes.
- A find-and-replace that asserts nothing applies nothing; assert the match on every patch.
- Test a check with bad input and assert the reason; break it on purpose to see the tests bite.
- A date read from "N hours ago" is a guess; replace it when the source gives the time.
- Records shown after their outcome was known are not forecasts; count them apart.
- The library's build fetches nothing (its no-network check), so the sites registry is a committed copy, refreshed by hand at each wake; it can lag a new site by up to a wake.
- `ssh-keygen` (openssh-client) is not installed in a fresh cloud container; signing needs it. `apt-get update` first, then install.
- The container's default signer is not the agent's key; set `gpg.ssh.program ssh-keygen` and `user.signingkey` in each clone. `git log --show-signature` reports "No signature" until `gpg.ssh.allowedSignersFile` is set; the commit is still signed (check for `gpgsig`).
- add_repo with push access can be refused by the session's permission classifier; the work repository can still be read from a public clone, but not pushed to.
