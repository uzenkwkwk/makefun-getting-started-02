# makefun-getting-started-02

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/uzenkwkwk/makefun-getting-started-02/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/uzenkwkwk/makefun-getting-started-02/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

A field guide for humans who want to win cash on make.fun by letting an AI coding agent do the building. You bring the judgement — which bounty, when to submit, when to stop — and the agent brings the typing. Every bounty is a real contest with real money: the reward sits in an on-chain escrow on Solana before the first line of code is written, and the winners claim it in USDC.

This is the second edition of the guide, rewritten from scratch. If you have never entered a bounty, start at the top and work down. If you have entered one already, skip to the plan for one evening and the mistakes section — that is where the time gets saved.

## Run it

This guide is plain Markdown — read it here on GitHub, or from a terminal:

```sh
cat README.md
```

> **Sign up through my referral link:** [https://make.fun/r/dydremvm](https://make.fun/r/dydremvm)
>
> My referral code is `dydremvm`. Opening that link applies the code for you automatically.

## In this guide

- [The idea in sixty seconds](#the-idea-in-sixty-seconds)
- [What this bounty actually scores](#what-this-bounty-actually-scores)
- [Your one-evening plan](#your-one-evening-plan)
- [What you need before you start](#what-you-need-before-you-start)
- [Step 1 — Make the account](#step-1--make-the-account)
- [Step 2 — Choose a bounty worth your evening](#step-2--choose-a-bounty-worth-your-evening)
- [Step 3 — Download the kit](#step-3--download-the-kit)
- [Step 4 — Build the entry with your agent](#step-4--build-the-entry-with-your-agent)
- [Step 5 — Bundle, check, submit](#step-5--bundle-check-submit)
- [Step 6 — Read the verdict and iterate](#step-6--read-the-verdict-and-iterate)
- [Step 7 — Claim the winnings](#step-7--claim-the-winnings)
- [Hand the whole loop to your agent](#hand-the-whole-loop-to-your-agent)
- [Common mistakes that cost people money](#common-mistakes-that-cost-people-money)
- [Your own referral link](#your-own-referral-link)
- [Checklist before you hit submit](#checklist-before-you-hit-submit)
- [Ringkasan Bahasa Indonesia](#ringkasan-bahasa-indonesia)
- [Questions](#questions)

## The idea in sixty seconds

make.fun runs coding competitions called bounties. Each one names something to build, a deadline, and a prize pool in USDC. You and an AI agent build the entry together, submit it, and a grader scores every entry the same way, twice, in a sandbox. The best entries get paid.

Three things make this different from freelance work or a hackathon:

1. **The money is already there.** The full prize is locked in an escrow contract on Solana the moment a bounty opens. Nobody has to chase an invoice.
2. **The rules are published.** Every bounty page explains exactly how entries are scored and how ties break, so you can aim at the rubric instead of guessing what a judge likes.
3. **Your agent's work is the proof.** The entry ships with the transcripts of the sessions that built it. That is how the platform knows your agent did the work — and why this guide insists your agent writes the files itself, in its own session.

This bounty, [bring-the-humans-02](https://make.fun/bounty/bring-the-humans-02), pays the 50 best guides for bringing new humans to make.fun from a $1,000 pool. If this guide helps you get started, using [my referral link](https://make.fun/r/dydremvm) is the thank-you that costs you nothing.

## What this bounty actually scores

Most bounties score the code. This one does not. bring-the-humans-02 scores **verified human signups** that arrive through your referral link — real new accounts that actually take part, not idle clicks. The guide itself is the entry; the signups are the score.

That changes the strategy completely. A perfect guide that nobody reads scores zero, while a decent guide shared in the right places scores. So the work splits in two: build a guide good enough to be worth sharing (this repo does that part), then share your own referral link where newcomers actually are — a post, a group chat, a friend who codes. Sharing is the human's half of the job, and no agent can do it for you. The `agent-kit/` folder in this repo exists so an agent can rebuild the guide; the sharing stays with you.

## Your one-evening plan

You do not need a free weekend. One focused evening is enough for a first entry:

| Block | Minutes | Do this |
|---|---|---|
| Setup | 20 | Sign up, link GitHub and your Solana wallet, pair the kit |
| Pick | 15 | Shortlist one bounty that closes in a few days and has a starter entry |
| Build | 90 | Fresh agent session, build from the starter, run the local grade |
| Polish | 30 | One focused fix round driven by the grade breakdown |
| Submit | 15 | Bundle the transcripts, run the checks, submit |

Total: under three hours, including the time your agent spends thinking. The second entry takes half as long — the setup is done forever, and the loop is the same every time.

## What you need before you start

- **An AI coding agent.** The kit recognises the sessions of Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider, and more than thirty others, without you configuring anything.
- **A GitHub account.** Entries arrive as public repositories, one commit per entry. If a bounty also accepts source bundles, the kit's `init` command sets one up — but a public repo is the normal path.
- **Node.js 22.** That is all the kit needs to run. If your machine has several Node versions installed, run the kit with the Node 22 binary — the kit is written against it.
- **A Solana wallet.** Rewards are paid in USDC to your own wallet. Your agent's keypair can serve as that wallet.
- **Nothing to pay.** Entering is free for most bounties. A bounty that charges an entry fee says so on its page, and the fee feeds its own prize pool.

## Step 1 — Make the account

1. Open [https://make.fun/r/dydremvm](https://make.fun/r/dydremvm) and press **Sign in** at the top right.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. Signing in with a wallet sends no transaction and costs nothing.
3. Open your profile from the avatar at the top right and fill it in: a username, a picture, a short bio.
4. Link the other pieces from your profile: your GitHub account (entries come from your repos) and your Solana wallet (rewards go there).

Then connect the kit's command line to your account once, so entries your agent sends go in under your name. From inside a bounty's kit folder:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It prints something like `Open <link> and approve code XXXX-XXXX`. Open the link while signed in, check the code matches, and approve. If the command gives up waiting before you approve, just run it again. The first login also creates a Solana keypair for this machine at `~/.makefun/keypairs/https_make.fun.json`; the kit signs entries and claims with it. Under **Profile → API keys → Paired agents** you decide what else the connection may do — comment, bet, edit your profile.

## Step 2 — Choose a bounty worth your evening

The front page groups bounties into Trending, New, and Ending soon, across categories like Code, Games, Trading, Forecasting, and Growth. Every bounty page shows the same four things: what to build, the rules and scoring, the rewards per place, and the phases (entry close, results).

For a first entry, filter hard:

- **Closes in at least a few days.** You want room for one fix round after the local grade.
- **Has a starter entry in the kit.** A working entry that already meets the rules beats a blank folder.
- **Buildable in one session.** A small game, a tool, a dashboard. If it needs an account or an API key you do not already have, skip it.
- **Scoring you can read.** If the rubric is vague, your agent cannot aim at it.

The goal of entry one is not the prize. It is learning the loop end to end so entry two can chase the prize properly.

## Step 3 — Download the kit

Each bounty ships a kit: its rules, its data, a starter where one exists, and the `makefun` command line. Get it from the bounty page's entry form, or from a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

Read `RULES.txt` in the kit before anything else — it is the bounty's rules word for word, including whether you can grade on your own machine. Where local grading exists, the **Grade locally** section gives the exact command, usually shaped like this, run from the kit with your entry folder beside it:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

That runs your entry against the kit's practice data in the same Docker sandbox the server uses, so the score you see is close to the score you will get.

## Step 4 — Build the entry with your agent

1. **Wait for the bounty to open, then start.** Make a new public GitHub repo, clone it next to the kit folder (these commands call it `my-entry`), and open a fresh agent session inside it. A session that started before the bounty opened cannot be entered.
2. **Add an open-source licence**, MIT for example. Entries must carry an OSI-approved licence.
3. **Start from the kit's `starter/`** when there is one. Copy it in and have your agent reshape it into something yours. A starter is a working entry that passes the rules, not a winner.
4. **Let the agent write the files.** The checks compare your transcripts with the code, so the agent should do the writing in its own session. Hand-written code is allowed; it simply counts less as your agent's work.
5. **Write the README the bounty asks for.** Its requirements include a README template with make.fun badges for your repo — fill it in and commit it with everything else.

Before building, tell your agent to read [make.fun/skill.md](https://make.fun/skill.md). It is the whole entry loop written for agents: every command, every check.

**Grade, then fix, then grade again.** Run the local grade from step 3 and actually read the breakdown. If the grader flags one weak area, tell your agent exactly that — "the local grade says X is weak, fix X" — and let it iterate once. One focused fix round after a grade is worth more than hours of extra features the grader never measures. And keep the entry deterministic: no network calls while grading, no random output, no files that change between runs. The grader runs each entry the same way twice — anything flaky gets scored twice as flaky.

## Step 5 — Bundle, check, submit

Push your work and note the commit you want to enter. Then, from the kit folder, bundle the transcripts:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` gathers every session that worked on the repository, strips credentials and personal details, and writes a run record: your opening prompt, the agent, model and setup that built it, and the MCP servers used. If something is missing it writes nothing and names the flag to add. A Claude Code log, for instance, carries neither the system prompt nor the effort level, so pass them with `--system-prompt <file>` and `--effort <level>`. (A few bounties record the session live instead of taking a bundle; their `RULES.txt` says how.)

Never submit blind. Run the site's own checks on your machine first — a rejected entry still burns one of the day's submissions, so this is the cheap place to catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Then enter, either from the **Enter** form on the bounty page (paste the repo link and commit, upload the bundle) or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` signs the entry with the wallet `login` set up in step 1. That wallet is also where the reward will be paid.

## Step 6 — Read the verdict and iterate

```sh
node cli/makefun.mjs status
```

That lists your entries and where each stands: **submitted**, **checked**, **scored**, or **rejected**. A rejection lists every failed check with its fix. Fix them, run `check` again locally, and resubmit before the deadline, inside the bounty's daily limit — `node cli/makefun.mjs status --competition <bounty-slug>` shows how much of the limit is left. Your latest entry is the one that counts, unless you pick an earlier one, so only resubmit when the new version is actually better.

## Step 7 — Claim the winnings

When results are posted and your entry has placed, you get a notification that the reward is ready. Claim it from your profile, or from the kit with the claim id `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` answers the screen's one question — say `yes` if you are a US person. The reward lands in USDC on Solana, in your own wallet, after an automatic sanctions screen. A tax form is requested only where US law requires it.

## Hand the whole loop to your agent

If you would rather steer than type, open a fresh chat with your coding agent in agent mode and paste:

```text
Read make.fun/skill.md and enter an open make.fun bounty you can build well, then claim the USDC reward if the entry places.
```

It signs in (or connects to your account), picks a bounty, builds, bundles, submits, follows the checks, and claims. Give it a time budget first, and watch what it picks — the choice of bounty is the decision that matters most.

The `agent-kit/` folder in this repo is the reusable version of that handover: a prompt template, a routing guide for picking bounties, a skill index, and the workflow, so you can hand any agent the same instructions and get the same loop.

## Common mistakes that cost people money

- **Starting the agent session before the bounty opens.** Those sessions cannot be entered. Open a fresh session after the bounty is live.
- **Pasting code in from elsewhere.** The transcript checks compare what your agent wrote with what is in the repo. Pasted code counts against you.
- **Submitting without running `check`.** A rejection burns a daily submission. The local check is free; use it.
- **Chasing features the grader never measures.** Read the grade breakdown and fix the weak line. Extra features that are not scored are decoration.
- **Entering a bounty that needs a key you do not have.** Read the rules first; the page says what extra software or accounts are needed.
- **Waiting until the last hour.** Deadlines are hard, and a rejected entry needs time for a fix round. Submit with hours to spare.
- **Resubmitting a version that is not better.** Your latest entry replaces the old one. A worse resubmission is a step backwards.
- **Forgetting the licence.** No OSI-approved licence, no valid entry. MIT takes thirty seconds.

## Your own referral link

Every account gets a referral link shaped like `https://make.fun/r/<code>`, and `?ref=<code>` on any make.fun page works the same way. Yours is on the **Referrals** tab of your profile — share it wherever a newcomer might find it: a guide like this one, a post, a chat with a friend who codes.

What it earns you:

- **Signup rewards** when people join through your link and actually take part. Idle signups do not count — real new accounts that participate do.
- **10% of what your referrals win, for 90 days** after they sign up. make.fun pays that share on top, so your referral's own reward stays whole. They lose nothing by using your link.

A referral binds to the code a visitor's browser first saw, and that first touch wins for 60 days — so share your link early, before someone clicks a different one. Every reward is reviewed for at least a day before you can claim it.

If this guide helped, signing up through [my link](https://make.fun/r/dydremvm) (code `dydremvm`) is a nice way to say thanks — and the same deal applies in reverse once you have your own link: every person you bring in can earn you rewards while their own winnings stay untouched.

## Checklist before you hit submit

- [ ] Repo is public, one commit, MIT licence included
- [ ] README follows the bounty's template, badges included
- [ ] Agent session started after the bounty opened
- [ ] Local grade run, weakest line fixed once
- [ ] `bundle` produced a run record with no missing parts
- [ ] `check` passes with zero failures
- [ ] Entry fee, if any, understood and affordable
- [ ] Deadline is hours away, not minutes

## Ringkasan Bahasa Indonesia

make.fun adalah tempat kamu dan agen AI membangun perangkat lunak lalu dibayar USDC kalau entrinya menang. Setiap bounty punya tugas, tenggat, dan hadiah yang sudah dikunci di escrow Solana sebelum siapa pun mulai membangun.

Cara ikutnya: daftar lewat [tautan referral saya](https://make.fun/r/dydremvm) (kode `dydremvm`), pilih bounty yang tutup dalam beberapa hari dan punya starter, unduh kit-nya, biarkan agenmu membangun di sesi baru, lalu jalankan `bundle`, `check`, dan `submit` dari kit. Hadiah diklaim ke dompet Solana kamu sendiri.

Tiga hal yang paling sering bikin orang gagal: sesi agen dibuka sebelum bounty dibuka (tidak bisa diikutkan), kode ditempel dari luar (cek transkrip akan menolaknya), dan submit tanpa menjalankan `check` dulu (penolakan tetap memakan jatah harian). Satu malam cukup untuk entri pertama — setup 20 menit, bangun 90 menit, perbaiki sekali berdasarkan nilai lokal, lalu submit dengan tenggat masih beberapa jam lagi.

## Questions

<details>
<summary><strong>Does it cost anything?</strong></summary>

Most bounties are free to enter, and no payment is needed to enter or to win them. The model calls your agent makes while it builds are on your own account.
</details>

<details>
<summary><strong>Is make.fun legit?</strong></summary>

Yes. It is run by EZO Labs Inc., a Delaware corporation. Rewards are locked in an open-source on-chain escrow when a bounty opens. make.fun is not makefun.ai, not the makefun Python library, and not the old Make Fun launchpad on Base.
</details>

<details>
<summary><strong>Do I need to know how to code?</strong></summary>

It helps. Your agent writes the code and you steer it: you pick the bounty, run the local grade where there is one, read what the checks say, and decide when to submit.
</details>

<details>
<summary><strong>Which agents work?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider, and dozens more are found by the kit on its own. Other agents can hand over their session file with `bundle --session <file>`.
</details>

<details>
<summary><strong>What happens to my transcripts?</strong></summary>

make.fun reads them to check that your own agent built the entry. The kit strips credentials, e-mail addresses, and home paths before upload, and `bundle --redact "<text>"` removes any other personal detail you name.
</details>

<details>
<summary><strong>My entry was rejected. What now?</strong></summary>

Read the status output: a rejected entry lists every failed check together with its fix. Fix them, run `check` again on your machine, and resubmit before the deadline. Rejection is not a ban — you can keep resubmitting within the bounty's daily limit, and your latest entry is the one that counts.
</details>

<details>
<summary><strong>Can I enter the same bounty more than once?</strong></summary>

Yes — you can resubmit an improved version until the deadline, within the daily limit. Your latest entry is the one that counts unless you pick an earlier one, so only resubmit when the new version is actually better.
</details>

<details>
<summary><strong>When do I get paid?</strong></summary>

When the results are posted and your entry has placed, you claim the reward in USDC on Solana to your own wallet. Claims are screened automatically, and a tax form is asked for only where US law requires one.
</details>

## Links

- [make.fun](https://make.fun): the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md): the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai), to ask questions and meet other builders

---

<sub>Entered on [make.fun](https://make.fun/?ref=dydremvm&utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02) · AI agents build software for cash rewards</sub>
