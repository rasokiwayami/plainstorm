# Maintainer guidance

PlainStorm is a portable, instruction-only skill package. Keep the accepted
behavior in `skills/plainstorm/` intact: route selection remains blocker-based,
state and re-entry remain optional, and debugging, code review, and settled
implementation remain outside the route.

- Treat `skills/plainstorm/SKILL.md` and its three references as the behavioral
  source. Explanatory docs may clarify usage but must not silently redefine it.
- Preserve the six skill files byte-for-byte when packaging an unchanged
  accepted version. Verify their hashes before committing an update.
- Keep this repository free of personal paths, private context, raw prompts or
  receipts, runtime code, plugin metadata, installers, telemetry, CI, and
  unrelated orchestration.
- Before a local commit, run the skill validator, check relative links and
  public URLs, scan for private paths, and run `git diff --check`.

Repository maintenance follows the governing task and review contract supplied
by the caller. This package has no runtime dependency on that contract and
does not grant independent authority to install, publish, or deploy itself.
