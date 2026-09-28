# Special Contributions

This repository rewards contributions that the normal bounty process cannot track: work that involves no code, or code that was merged somewhere the bounty scanner does not watch. Examples are vulnerability reports without a fix, community moderation, documentation, and onboarding.

The full process is on the wiki: https://wiki.tari.com/processes:bounties

## How it works

1. **A maintainer opens an issue here**, on request from a Core Contributor or the council. The issue describes the contribution and what "done" looks like.
2. **The maintainer applies a sizing label** (`bounty-S`, `bounty-M`, `bounty-L` or `bounty-XL`). The bounty scanner only tracks issues that carry one of these labels, and only maintainers can apply them.
3. **The contributor opens a pull request** following the pattern of earlier merged PRs, with `Fixes #XXX` in the description and their XTM payout address on its own line.
4. **A maintainer merges the PR.** The bounty is queued for payout and the administrator runs a payout batch, usually within a week or two.

## Do not file here unless invited

**Do not open issues or pull requests in this repository unless a maintainer has asked you to.** Unlabeled issues and unsolicited pull requests are not tracked by the bounty system and will not be paid. Issues here are created by maintainers only.

If you believe past work deserves a retro bounty, ask a maintainer or Core Contributor in the community channels. They can request an issue here, or, for a pull request already merged in a repository on the bounty board, apply the `retro-bounty` label plus a sizing label directly to that PR.

## Payout address

Put your XTM address in the PR description. If none is found when the PR merges, the bounty bot posts a comment on the PR asking for one. Only an address posted from the PR author's own GitHub account is accepted.
