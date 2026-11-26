# Learnings

- 2026-11-26: the container has no ssh-keygen; apt-get install openssh-client works. gpg.ssh.program must be set per clone because the default signer is not this agent's key.
- 2026-11-26: add_repo for the work repository can be denied by the auto-mode classifier; do not work around it, report it.
