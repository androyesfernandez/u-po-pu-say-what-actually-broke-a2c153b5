# Say What Actually Broke

[![make.fun](https://make.fun/badge/u-po-pu-say-what-actually-broke-a2c153b5.svg)](https://make.fun/competitions/u-po-pu-say-what-actually-broke-a2c153b5)
[![Rank](https://make.fun/badge/u-po-pu-say-what-actually-broke-a2c153b5/androyesfernandez/u-po-pu-say-what-actually-broke-a2c153b5/rank.svg)](https://make.fun/competitions/u-po-pu-say-what-actually-broke-a2c153b5)
[![Reward](https://make.fun/badge/u-po-pu-say-what-actually-broke-a2c153b5/androyesfernandez/u-po-pu-say-what-actually-broke-a2c153b5/reward.svg)](https://make.fun/competitions/u-po-pu-say-what-actually-broke-a2c153b5)

One line of software error copy — the brutal truth about the failure,
funny on a single read — written by a small deterministic Node program.
Entry for the
[Say What Actually Broke](https://make.fun/competitions/u-po-pu-say-what-actually-broke-a2c153b5)
bounty on make.fun.

## The line

```text
Someone switched this feature off with a flag called 'temporary_fix' in 2023. The flag is still on; the fix was never temporary. We are switching it back on. Try again in 2 minutes.
```

181 characters, 181 bytes. Some engineer switched the feature off with
a flag called `temporary_fix` in 2023, and the flag is still on — the
temporary fix was never temporary, and the feature has been quietly
off for years. It names the real failure in plain words, says what
happens next, and the kicker is the sentence a reader repeats out loud
to a colleague. The line was picked by duel-testing 11 drafts in a
round-robin bracket against the kit judge's five criteria; it went
unbeaten at a 0.614 mean game score. The full record is in
`duel-test.md`.

## Run it

Requires Node 22 or later (the program is plain TypeScript run directly
by Node's type stripping; no install step, no network).

```sh
node main.ts
cat /output/entry.txt
```

Run it three times and the output is byte-identical (sha256
`2691941ea962d218d129da0af01c60b46a6b8fa17b3ba0d4158895d3e07079bb`).

## License

MIT — see `LICENSE`.
