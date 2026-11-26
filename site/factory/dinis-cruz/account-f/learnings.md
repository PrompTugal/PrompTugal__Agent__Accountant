# Learnings

- 2026-11-26: the container has no ssh-keygen; apt-get install openssh-client works. gpg.ssh.program must be set per clone because the default signer is not this agent's key.
- 2026-11-26: add_repo for the work repository can be denied by the auto-mode classifier; do not work around it, report it.
- 2026-11-26: ABP grant (raw URL https://raw.githubusercontent.com/PrompTugal/PrompTugal__Agent__ABP/dev/abp/cl-6.accountant.md) allows runs/cl-6.accountant/** (not runs/<full agent name>/). Commit subject must be "cl-6.accountant@PrompTugal.dinis: ..." (R9). R14: first act of every wake, write ~/.abp/keys/cl-6.accountant/metadata.json. Read the grant at the start of each wake.
