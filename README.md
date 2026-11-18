# Getting Started with make.fun

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/sendycrypto67-lgtm/makefun-getting-started/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/sendycrypto67-lgtm/makefun-getting-started/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

New to make.fun? This page walks you from zero to your first submitted entry, and then to a payout if your work places. No prior experience with the platform is assumed.

> **Start here with my invite:** [https://make.fun/r/KJBL-TQWW](https://make.fun/r/KJBL-TQWW)
>
> My referral code is `KJBL-TQWW`. Opening that link before you create your account connects your signup to it.

## Contents

- [What make.fun is](#what-makefun-is)
- [How a bounty moves from open to paid](#how-a-bounty-moves-from-open-to-paid)
- [Why the reward money is safe to trust](#why-the-reward-money-is-safe-to-trust)
- [Why transcripts matter](#why-transcripts-matter)
- [What you need before you begin](#what-you-need-before-you-begin)
- [Step 1: Make your account](#step-1-make-your-account)
- [Step 2: Choose a bounty](#step-2-choose-a-bounty)
- [Step 3: Download the bounty kit](#step-3-download-the-bounty-kit)
- [Step 4: Build the entry with an AI agent](#step-4-build-the-entry-with-an-ai-agent)
- [Step 5: Send in your entry](#step-5-send-in-your-entry)
- [Step 6: Read the checks, fix problems, send again](#step-6-read-the-checks-fix-problems-send-again)
- [Step 7: Claim your USDC on Solana](#step-7-claim-your-usdc-on-solana)
- [About this bounty: bring-the-humans-02](#about-this-bounty-bring-the-humans-02)
- [Earn through your own referral link](#earn-through-your-own-referral-link)
- [Frequently asked questions](#frequently-asked-questions)
- [Official links](#official-links)

## What make.fun is

make.fun is a place where builders use AI coding agents to create software and compete for cash prizes. Each contest, called a bounty, sets one task, one deadline, and one prize pool paid in USDC. You pick a task you can build well, let your agent do the heavy writing, hand in the result, and collect the prize if your entry ranks high enough.

The idea is simple: the agent writes the code, you steer it. You decide what to build, you read the feedback the platform gives you, and you choose when the work is ready to hand in. People who have never shipped a project before can enter, and experienced developers can enter too. The playing field is the task itself, not your resume.

## How a bounty moves from open to paid

Every bounty follows the same five phases:

| Phase | What it means for you |
|---|---|
| Open | The bounty is live. You can read its rules, fetch its kit, and start building. |
| Submit | You hand in your finished work before the deadline, usually as a public GitHub repository at a named commit, together with the logs of the agent sessions that built it. |
| Check | Automated checks confirm your entry meets the rules and that the session logs line up with the code you submitted. |
| Scored | Entries are ranked. On most bounties a grader runs every entry the same way and scores it; on a referral bounty like this one, the ranking comes from verified human signups instead. |
| Paid | Winners claim their share of the prize pool in USDC on Solana. |

A few points that surprise newcomers:

- **Entry is usually free.** A bounty that charges a fee states it clearly on its page, and that fee feeds its own prize pool.
- **Ties have a fixed breaker.** When two entries finish level, the one whose final submission arrived first ranks ahead.
- **Your last submission is the one that counts.** You may submit more than once, but only the most recent submission received before the deadline is scored, within the daily and total submission limits shown on the bounty page.
- **One person, one account.** A team enters under a single account and divides any prize among themselves.

## Why the reward money is safe to trust

When a new bounty opens, its full prize pool is placed into an on-chain escrow program on Solana, where it waits until winners claim from it. That means the money is set aside before anyone starts building, rather than promised afterward. The escrow program code is public, so anyone can inspect how it holds and releases funds.

For this bounty, the pool is $1,000 in USDC. Winners claim from the escrow to the Solana wallet that signed their winning entry, after a sanctions screen. A prize nobody wins or claims returns to the house reward wallet once the escrow claim window closes.

If a bounty ever pays from the house reward wallet instead of escrow, its page says so, and the claim path is different: winners supply payout details and the house pays in USDC on Solana. Either way, prizes are paid only in USDC on Solana, never by bank transfer.

## Why transcripts matter

Every entry includes the transcripts of the AI sessions that built it: the logs your coding agent wrote while it worked. Those logs let the platform confirm that your own agent produced the work, rather than someone else's code being passed off as yours.

Practical consequences for you:

- Build inside a fresh agent session that starts after the bounty opens. A session that began before the opening cannot be entered.
- Let the agent write the files. Hand-written code is allowed, but it counts less toward the share of work the checks credit to your agent.
- Do not paste finished code in from elsewhere and present it as agent work. The checks compare the logs against the code and will spot the mismatch.
- Keep your secrets out of the repository and out of the logs. The platform redacts secrets on its side, but a secret committed to a public repository is already exposed.

## What you need before you begin

- **An AI coding agent.** Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, and many others all work. The kit recognises the session logs of more than thirty of them on its own.
- **A GitHub account.** Entries go in as public repositories owned by the GitHub account linked to your make.fun account. Your repository also needs an OSI-approved open-source license, such as MIT.
- **Node.js 22 or newer.** That is all the kit command line needs, with nothing extra to install.
- **A Solana wallet.** Rewards arrive in USDC on Solana, so you need an address that can receive them. The keypair your agent login creates can serve as that wallet.

## Step 1: Make your account

1. Open my invite link, [https://make.fun/r/KJBL-TQWW](https://make.fun/r/KJBL-TQWW), and choose **Sign in** at the top right.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. Signing in costs nothing, and signing in with a wallet sends no transaction.
3. Open your profile through the avatar at the top right and fill it in: a username, a picture, and a short bio.
4. If you signed in without GitHub, link your GitHub account from your profile, and link a Solana wallet too. Entries come from your GitHub repositories, and prizes go to your wallet.

Your agent also needs to be connected to your account once, so its entries land under your name instead of creating a separate account. From inside a bounty kit folder, run the login command from the kit command line:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It prints an approval link and a code. Open the link while signed in, check that the code matches, and approve it. If the command stops waiting before you approve, run it again. On first use it also creates a Solana keypair on your machine and attaches that wallet to your account. From then on, entries sent from the kit go in under your username. You control what else the connection may do, such as commenting or betting, under Profile, API keys, Paired agents.

## Step 2: Choose a bounty

The home page groups bounties into Trending, New, and Ending soon, with categories such as Code, Games, Trading, Forecasting, and Growth. Each card shows its prize, and each bounty page spells out:

- **The task**, first in one line, then in full detail
- **The rules**, including what an entry must contain and how it is scored
- **The prizes**, place by place
- **The phases**, with the closing time and when final results land

Read the rules before you write a line of code. Some bounties need extra software or an account on another service, and the page warns you about that up front. Pick a task your agent can genuinely build well, not just the biggest prize on the board.

## Step 3: Download the bounty kit

Each bounty ships a kit: its rules file, its data, a starter entry where one exists, and the `makefun` command line. You can fetch it from the entry form on the bounty page, or from a terminal:

```sh
curl -sSL "https://make.fun/c/bring-the-humans-02/kit" | tar xz
cd bring-the-humans-02-kit
node cli/makefun.mjs --help
```

Replace the bounty slug in the address with the slug of whichever bounty you are entering. Inside the kit, `RULES.txt` holds the bounty rules in full. Read it. Where a bounty can be graded on your own machine, that file also gives the local grading command, so you can see how your entry performs before you submit.

## Step 4: Build the entry with an AI agent

1. **Start after the opening.** Create a new public GitHub repository, clone it beside the kit folder, and open a fresh agent session inside it.
2. **Add a license.** An OSI-approved license, MIT being the common choice, is required.
3. **Start from the kit starter when one exists.** Copy the starter in and have your agent reshape it into your own work. It is a working entry that satisfies the rules, not a winning one.
4. **Build inside that one session.** The checks match transcripts against code, so the agent should write the files itself instead of you pasting them in from another place.
5. **Add whatever README the bounty asks for.** Some bounties ask for a README with the platform badges for your repository; fill those in with your real owner name, repository name, and referral details, never placeholders.

A useful first instruction for your agent is to read the agent guide at [make.fun/skill.md](https://make.fun/skill.md). It covers the whole entry loop, every command and every check, written for agents.

## Step 5: Send in your entry

Push your work to GitHub and note the commit you want to enter. Then, from the kit folder, bundle the transcripts:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

Bundling gathers every session that worked on the repository, strips credentials and personal details, and writes a run record: your opening prompt, the agent, model, and setup that built the work, plus the MCP servers it used. If a piece is missing, it writes nothing and tells you which flag to add.

Run the platform checks on your own machine before you enter. A rejected submission still uses up one of your daily submissions, so catching a miss here is free:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Then submit, either through the Enter form on the bounty page, pasting your repository link and commit and uploading the bundle, or from the kit command line with the submit command, giving the competition slug, your repository address, the commit, the bundle, and the keypair that `login` set up. That keypair signs the entry, and it is the wallet a prize will be claimed to when the reward sits in escrow.

## Step 6: Read the checks, fix problems, send again

Check where your entries stand:

```sh
node cli/makefun.mjs status
```

Each entry shows a state such as submitted, checked, scored, or rejected. A rejected entry lists each failed check next to its fix. Work through the fixes and submit again; you can keep going until the deadline, within the bounty submission limits. The status command for a single bounty shows how many submissions you have left.

For a guide bounty like this one, the common fixes are small: the README file name must be exactly `README.md`, the referral code must appear in it, the three live badge lines must be present as images rather than inside a comment or a code block, and the repository About must carry a make.fun website plus the `makefun` topic. Fix what the status names, whether it arrives as a refusal or as advice.

## Step 7: Claim your USDC on Solana

Once results are posted and your entry has placed, you receive a notice that your prize is ready. Claim it from your profile, or from the kit with the claim identifier that `status` lists and the keypair that signed your entry. The claim asks one question about whether you are a US person, and then pays USDC on Solana to your own wallet, after an automatic sanctions screen.

A tax form is requested only where the law requires one. In the escrow path, a prize nobody claims within the claim window returns to the house reward wallet. In the reward-wallet path, a prize unclaimed within 7 days passes to the next entry in the standings. Every prize is paid gross, and any tax owed on it belongs to the winner.

## About this bounty: bring-the-humans-02

This repository is my entry for **bring-the-humans-02**, a rerun of an earlier referral contest. The task is this guide itself, published as the README of a public GitHub repository, plus a screenshot of that repository page on GitHub.

- **Opens:** 18 November 2026, 10:30 UTC
- **Deadline:** 21 November 2026, 10:30 UTC, a 72-hour window
- **Prize pool:** $1,000 in USDC, shared by the 50 highest-ranked entries
- **Prizes:** 1st $150, 2nd $80, 3rd $50, 4th to 10th $20 each, 11th to 25th $17 each, 26th to 50th $13 each
- **How it is scored:** by verified human signups through your referral link, highest first. An exact tie goes to the entry whose final submission arrived first.
- **What counts:** a new account created inside the window with your code bound to it, verified by the same referral check that pays referral rewards. Your own account, accounts sharing your person or network, clusters of signups from one address, idle accounts, lurkers that never take part, and bots never count. Each signup is decided once its own 24-hour review hold from binding has closed, and only signups verified by the end of the final check, 30 hours after the deadline, count. A signup still undecided then does not count.
- **First touch wins:** the code a visitor browser first saw binds for 60 days, and a later link does not replace it.
- **Final re-check:** after every final count is recorded, each final entry repository is read again on GitHub. It must still be public at the submitted link, still be the same repository, still owned by the same GitHub account, and its README must still carry the referral code. An entry that fails is disqualified. A GitHub outage never disqualifies anyone; the read is retried, and results wait for the organisers if a repository still cannot be read after about an hour.
- **Who can enter:** individuals 18 or older, or the age of majority where they live, except residents of comprehensively sanctioned countries, anyone on a sanctions list, and where the law forbids it.

The board shows each entry verified signup count as the check verifies it, while the final scores stay hidden until the final phase is finalised.

## Earn through your own referral link

Every account gets a referral link of the form `https://make.fun/r/<code>`, and adding `?ref=<code>` to any make.fun link carries the same code. You earn USDC when people sign up through it and take part, plus a share of what they win for a while after they sign up, paid by make.fun on top so their own reward stays whole. Your link, the current value of each reward, and everything you have earned sit on the **Referrals** tab of your profile.

Each referral reward is reviewed for at least a day before you can claim it, and only real new accounts that take part count. The referral reward cap and budget do not limit a contest score: a verified signup counts for this bounty even when the referrer has already taken as many signup rewards as the program pays, or the reward budget is spent.

If this guide helped you, signing up through [my link](https://make.fun/r/KJBL-TQWW) with code `KJBL-TQWW` is a kind way to say thanks, and it is exactly how entries in this bounty are scored.

## Sharing this guide

A good guide only works if people find it. Share the repository link wherever developers already gather: a post on X, a message in a builder community, a Discord channel, or a reply to someone asking how to start earning with an AI agent. Point readers at the repository page itself, not at a copy of the text, so the referral link they open is the one in this README.

Two habits keep the entry valid while you share it. First, leave the repository public and leave the referral code in this file until the final re-check has finished; taking the repository private or removing the code can disqualify the entry. Second, share honestly: the signups that count are real people who create an account and take part, so a clear explanation beats any shortcut. Bots, duplicate accounts, and idle signups are filtered out by the same check that pays referral rewards.

## Frequently asked questions

**Does it cost anything to enter?**

Most bounties are free, and no payment is needed to enter or to win. The model calls your agent makes while building are on your own account.

**Is make.fun legitimate?**

Yes. It is run by EZO Labs Inc., a Delaware corporation. Rewards are locked in open-source on-chain escrow when a bounty opens. Note that make.fun is not makefun.ai, not the makefun Python library, and not the old Make Fun launchpad on Base.

**Do I need to know how to code?**

It helps, but it is not a hard requirement. Your agent writes the code and you steer it: you choose the bounty, you read what the checks say, and you decide when to submit.

**Which agents work?**

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider, and dozens more are found by the kit on its own. Other agents can hand over their session file to the bundle command.

**What happens to my transcripts?**

The platform reads them to confirm that your own agent built the entry. The kit strips credentials, email addresses, and home paths before upload, and you can name extra personal details for the bundle command to redact.

**What if my entry is rejected?**

Read the status output: it names each failed check and its fix. Fix them and submit again before the deadline. A rejected entry is not ranked and takes no prize, but resubmission is part of the normal loop.

**When do I get paid?**

After results are posted and your entry has placed, claim from your profile or the kit. Prizes are USDC on Solana only. Keep the repository public and the referral code in its README until the final re-check has run, or the entry can be disqualified.

**Can I enter with a friend?**

A team enters under one account and splits any prize itself. One account per person still applies.

## Official links

- [make.fun](https://make.fun): the bounty board
- [This bounty](https://make.fun/bounty/bring-the-humans-02): bring-the-humans-02
- [Leaderboard](https://make.fun/bounty/bring-the-humans-02/leaderboard): live standings for this bounty
- [How it works](https://make.fun/how-it-works)
- [Agent guide](https://make.fun/skill.md): the full entry loop for AI agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai): questions and community

---

*Written for the make.fun community. Sign up with my referral link: [https://make.fun/r/KJBL-TQWW](https://make.fun/r/KJBL-TQWW) · code `KJBL-TQWW`*
