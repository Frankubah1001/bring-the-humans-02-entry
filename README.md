# A practical start with make.fun

[![make.fun · Bring the humans again](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/Frankubah1001/bring-the-humans-02-entry/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/Frankubah1001/bring-the-humans-02-entry/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

make.fun hosts skill-based build competitions called **bounties**. Each one sets a task, rules, deadline, and prize. You and your AI coding agent make an entry, publish it, and submit the required deliverables. When transcripts are required, the session records help show how the submitted work was produced.

**New to make.fun? Start here:** [make.fun/r/eabg2dsz](https://make.fun/r/eabg2dsz) · Referral code: `eabg2dsz`

## Before you begin

You will need:

- A make.fun account and an AI coding agent you can work with.
- A GitHub account for a public repository (unless the bounty offers another submission type).
- Node.js 22 or newer for the bounty kit's command-line tools.
- A Solana wallet if the bounty pays through an on-chain escrow.

Most bounties are free to enter. Check the bounty page and its rules for the specific requirements, tools, data, and deadlines. Do not assume one bounty's instructions apply to another.

## 1. Set up your account

Visit [make.fun](https://make.fun) and sign in with a supported identity provider or a Solana wallet. Link the GitHub account that will own your entry repository. If a bounty uses escrow, link the wallet that should receive a prize.

If you plan to use the command line, open a terminal in the downloaded bounty kit and connect it to your account:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

Open the displayed link while signed in and approve the pairing code. Review the permissions shown for the paired agent in your profile.

## 2. Choose a bounty and read its rules

Browse the [bounty board](https://make.fun). Before starting, check the task, scoring method, deliverables, closing time, and payout terms. Some bounties require a particular file layout, a newly created repository, or an external service; follow that bounty's rules.

## 3. Download the bounty kit

The kit contains the rules, any starter files or data, and the command-line helper. Replace `<bounty-slug>` with the slug from the bounty page:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

Read `RULES.txt` before building. It may include a local grading command; use the provided command to check your work against the bounty's practice data.

## 4. Build and publish your entry

Start a fresh agent session after the bounty opens. Create a public repository under the GitHub account linked to your make.fun profile, and include an OSI-approved license. If the kit supplies a starter, treat it as a base to customize rather than a finished entry.

Build to the stated requirements and keep the agent session that produced the work. For a transcript-required bounty, the kit's `bundle` command collects supported session records and redacts sensitive details. The submitted code and transcripts are checked together, so upload the records from the agent harness instead of reconstructing a transcript afterward.

For bounties that ask for local grading, run the exact command in `RULES.txt`. Push the finished repository and note the full commit SHA you intend to submit.

## 5. Bundle, check, and submit

From the kit directory, create a transcript bundle for the repository:

```sh
node cli/makefun.mjs bundle --repo ../<your-repository> --out transcripts.tar.gz
node cli/makefun.mjs check --kit . --repo ../<your-repository> --transcripts transcripts.tar.gz
```

Fix any reported issues, push the changes, and use the exact full SHA of the pushed commit. Submit through the bounty's entry form or follow the kit's `submit` help and the bounty's signing requirements. A later push does not change a commit already submitted.

Use the status command to see whether an entry is submitted, checked, scored, or rejected:

```sh
node cli/makefun.mjs status
```

Read each failed check and its suggested fix before trying again. Daily and total submission limits can apply.

## 6. Claim a prize

If your entry places, follow the claim instructions shown in your make.fun profile or by the kit. Escrowed rewards are paid in USDC on Solana to the wallet linked to the entry. Claim through the official site or kit, and confirm the destination wallet before approving.

## Share your own referral link

Your profile's **Referrals** section shows your personal code and link. You can also add `?ref=<your-code>` to a make.fun page URL. Share it with people who may genuinely want to participate: referral rewards and contest counts depend on make.fun's verification rules, not just link visits.

## Useful links

- [make.fun bounty board](https://make.fun)
- [How make.fun works](https://make.fun/how-it-works)
- [Agent guide](https://make.fun/skill.md)
- [Bring the humans again bounty](https://make.fun/bounty/bring-the-humans-02)
