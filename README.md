# renovate-31876

Reproduction for [Renovate issue 31876](https://github.com/renovatebot/renovate/issues/31876).

This can't be reproduced directly because according to https://docs.renovatebot.com/configuration-options/#postupgradetasks, only self hosted renovatebot servers can use `postUpgradeTasks`. The server must be configured with https://docs.renovatebot.com/self-hosted-configuration/#allowedpostupgradecommands. However, this renovate.json should work, if the server running against the repo has `allowedPostUpgradeCommands: [".*echo.*$"],` configured.

## Current behavior

Renovate does not run the `postUpgradeTasks` after `requirements.in` changes.

## Expected behavior

Renovate should run the `postUpgradeTasks` after `requirements.in` changes. The task should generate/update the lock file.
