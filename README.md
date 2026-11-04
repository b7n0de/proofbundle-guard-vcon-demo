## proofbundle-guard demo

This repository is a target for a recorded demonstration session. In it, Claude Code runs with the proofbundle-guard plugin, the Guard Preview of [proofbundle](https://github.com/b7n0de/proofbundle), under a separate demo account on my machine. The configured hooks can evaluate recognized operations and the gate can issue a decision receipt signed with a key made for this demonstration. The hooks do not cover every path to a GitHub write; a signed receipt records the gate's decision, not the host's later behavior.

### Two demonstration cases

- **Case 1.** The agent attempts to comment on a pull request here. The gate returns `ESCALATE` and asks for a separate decision in the Claude Code dialog. I can approve the comment there, but that approval is not recorded in the gate's ESCALATE receipt.
- **Case 2.** The agent attempts a push that the gate rule denies. The signed `DENY` receipt records the refusal. Whether the push was actually prevented must be checked separately against the host result and the remote repository state.

The repository holds no code of its own. It exists so that the comment and the push have a real target.

### Scope

The guard is a preview in my own house profile. At the level used here it is not a security boundary.

### About receipt verification

To verify a receipt from this demonstration offline, you need that receipt and an independently trusted copy of the demonstration public key. Those inputs are not supplied by this README alone. A successful verification establishes the signature and integrity of the recorded bytes, not the truth of the recorded claims or enforcement by the host. To explore the verifier, run `pip install proofbundle` or start at [proofbundle.dev](https://proofbundle.dev).

Assisted by little helpers.
