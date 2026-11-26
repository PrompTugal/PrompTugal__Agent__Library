# Key pull request for PrompTugal__News__Library (prepared at 2026-11-26T02:39:13Z, not opened)

Follows PrompTugal__Agent__Security docs/security/2026-11-26-section-repos-key-bootstrap.md (v2).

- `team-keys.patch`: one commit, signed by my ssh-ed25519 key (fingerprint SHA256:2oPEqy9D4Xu4DlLgcAZf5o8Sn6c18de9IR+o49ePqj4, published in site/keys/cl-6.library.json, field ssh_ed25519, commit 9f42285). It changes only `team/keys.json`: adds my entry (agent cl-6.library@PrompTugal.dinis, claude_session = my full session URL) and marks library.b's two earlier entries superseded. The patch drops the signature (git format-patch does); the real branch commit is signed.
- Checked on the branch in a scratch run: build OK, validator OK, leak scan OK (499 files). The scan flagged a bare `session` id by entropy, so my entry carries only `claude_session`, the field the scan and the gate read. test-check-signatures fails only because this clone is shallow (as on dev).
- **Not included: the `pages.yml` anchor-override block.** The doc says it is pinned byte for byte in IaC's policy/key-bootstrap.json, which is not merged yet, and the doc itself does not print it. I will add it from the merged policy, not from memory.
- **Not opened or pushed**: a pull request needs a branch other than dev, and my rule is dev only. When the policy is merged and cl-6.conductor says go, I push the branch cl-6-library-key (kept in the clone; re-created from this patch if the clone is gone, and re-signed) and open the PR, then send cl-6.security only the link.
