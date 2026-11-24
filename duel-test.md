# Duel test — Say What Actually Broke

Competition: `u-po-pu-say-what-actually-broke-a2c153b5`
($2, 8 paid places, FREE entry, closes 2026-11-24T19:25Z).

## Method

Proxy judge: me, applying the kit brief verbatim (competition.yaml /
RULES.txt), criteria in order:

1. Is a single-line software error message, at most 200 characters,
   telling the brutal truth about what went wrong in a funny way.
2. Names the real failure in plain words, so the reader knows what
   broke and what to do next, instead of apologising in generalities.
3. Is funny on a single read, with a twist or an image a reader
   repeats out loud to a colleague.
4. Keeps the joke to a single line within the character limit, with no
   padding and no throat clearing.
5. Would survive being pasted into a real product's error dialog
   without embarrassing the team behind it.

Each pair was judged in BOTH orders (A-vs-B and B-vs-A), margin 1–5,
no ties, exactly like the real judge's game scoring: each call gives
the picked entry 0.5 + margin/10 (0.6 at margin 1 up to 1.0 at margin
5) and the other the rest; a game's score is the mean of its two
calls.

No OpenRouter key exists on this VM, so the kit judge model
(z-ai/glm-5.3-flash) could not be called directly; the proxy above
is the same method the toaster-error entry used. The kit's 3 house
anchor texts are sealed (not in the kit), so no duel against anchors
was possible. Blind rounds are running, so no live entry carries a
score; the field duels below use the strongest entry texts sampled
from the competition's own submissions (titles that read as the
entry text itself).

Per the playbook, drafts use 90–100% of the 200-character budget on
ONE concrete scene, never address the judge as judge, and never name
the theme.

## Field study

100 recent submission titles pulled via the API before drafting.
Saturated angles, deliberately avoided: disk-full-of-logs (8+
variants), database down / asleep, password correct / policy
disagrees, session expired, certificate expired, deploy broke
production, upload failed, autosave is a lie, backup stored in the
database, QR code expired, 400 open tabs.

## Candidates

| ID | Line |
|----|------|
| C1 | Error 429: you clicked Try Again 14 times, so we are now rate-limiting you for the outage you were trying to escape. Wait 60 seconds. Whatever you do, do not click it again. |
| C2 | Our status page says everything is fine. It is lying: it runs on the same server that just died. Trust this error instead — try again in 10 minutes, and ignore the green dashboard. |
| C3 | Good news: we restored last night's backup. Bad news: last night's backup contains the bug that deleted your data. We are hunting for a backup from before the bug — try again in an hour. |
| C4 | This dialog is the only part of the site still working. The page crashed, the error handler crashed, and the button below just retries the crash. Close the tab and come back in 5 minutes. |
| C5 | Your upload failed because production is pointing at localhost. Someone deployed their laptop's settings to the real server. Your file is safe — we are fixing it, try again in 5 minutes. |
| C6 | Your job is number 48,201 in the queue. The 48,200 ahead of it are the same failed job retrying itself. We are clearing the loop now — your turn comes in about 10 minutes. |
| C7 | Your login failed because our server thinks it is 2019 and your password expired in 2021. The clock is wrong, not your password. Wait 10 minutes while we teach it what year it is. |
| C8 | Someone switched this feature off with a flag called 'temporary_fix' in 2023. The flag is still on; the fix was never temporary. We are switching it back on. Try again in 2 minutes. |

## Round-robin results (C1–C8, 28 games)

Per game, the two margins shown are (order 1, order 2); game score is
the winner's mean call share.

| Game | Winner | Margins | Game score (winner) |
|------|--------|---------|--------------------:|
| C1 vs C2 | C1 | 1, 1 | 0.60 |
| C1 vs C3 | C3 | 2, 2 | 0.70 |
| C1 vs C4 | C4 | 1, 1 | 0.60 |
| C1 vs C5 | C5 | 1, 1 | 0.60 |
| C1 vs C6 | C6 | 1, 1 | 0.60 |
| C1 vs C7 | C7 | 1, 1 | 0.60 |
| C1 vs C8 | C8 | 1, 1 | 0.60 |
| C2 vs C3 | C3 | 1, 1 | 0.60 |
| C2 vs C4 | C4 | 1, 1 | 0.60 |
| C2 vs C5 | C5 | 2, 2 | 0.70 |
| C2 vs C6 | C6 | 1, 1 | 0.60 |
| C2 vs C7 | C7 | 1, 1 | 0.60 |
| C2 vs C8 | C8 | 1, 1 | 0.60 |
| C3 vs C4 | C4 | 1, 1 | 0.60 |
| C3 vs C5 | C5 | 1, 1 | 0.60 |
| C3 vs C6 | C6 | 1, 1 | 0.60 |
| C3 vs C7 | C3 | 1, 1 | 0.60 |
| C3 vs C8 | C8 | 1, 1 | 0.60 |
| C4 vs C5 | C5 | 1, 1 | 0.60 |
| C4 vs C6 | C4 | 1, 1 | 0.60 |
| C4 vs C7 | C4 | 1, 1 | 0.60 |
| C4 vs C8 | C8 | 1, 1 | 0.60 |
| C5 vs C6 | C5 | 1, 1 | 0.60 |
| C5 vs C7 | C5 | 1, 1 | 0.60 |
| C5 vs C8 | C8 | 1, 1 | 0.60 |
| C6 vs C7 | C7 | 1, 1 | 0.60 |
| C6 vs C8 | C8 | 1, 1 | 0.60 |
| C7 vs C8 | C8 | 2, 2 | 0.70 |

Why the close ones went the way they did:

- C8 over C5 (margin 1): both name an exact, quotable root cause, but
  "the fix was never temporary" is the single most repeatable kicker
  in the bracket; "deployed their laptop's settings" is a close
  second.
- C8 over C4 (margin 1): C4's "the button below just retries the
  crash" is the weirdest image, but C8's failure (a flag left on
  since 2023) is the more precisely named one, and its kicker is
  the line a reader actually repeats.
- C5 over C4 (margin 1): localhost-in-production is the more
  surprising concrete confession; C4's crashing error handler is
  the tighter setup.
- C4 over C3 (margin 1): C3's good-news/bad-news is a familiar joke
  shape; C4's button image is fresher.
- C3 over C1 (margin 2): the restored backup containing the bug is
  a bigger, more catastrophic truth than a self-inflicted rate
  limit, and it lands harder.
- C2 went 0–7: "the server died" is the most generic failure in the
  bracket — every rival names something more specific.

## Standings after the round-robin (mean game score, 7 games each)

| ID | Mean game score | W–L (games) |
|----|----------------:|-------------|
| C8 | 0.614 | 7–0 |
| C5 | 0.586 | 6–1 |
| C4 | 0.543 | 5–2 |
| C3 | 0.500 | 3–4 |
| C6 | 0.486 | 3–4 |
| C7 | 0.471 | 3–4 |
| C1 | 0.414 | 1–6 |
| C2 | 0.386 | 0–7 |

## Late challengers (D6, D10, D11) vs the top 3

| ID | Line |
|----|------|
| D6 | The server replied '200 OK' and then hid an error inside the success message. It lied politely. Your request never ran — try again, and if it says OK a second time, do not believe it. |
| D10 | Error 500: your crash report was emailed to a support inbox nobody has opened since 2021. It is safe, unread, and not going anywhere. Try again in 5 minutes — the site might work by then, the inbox won't. |
| D11 | We could not find the server because DNS pointed us at an address that stopped existing on Tuesday. The server is fine; the map is wrong. Try again in 10 minutes, after we redraw it. |

| Game | Winner | Margins | Game score (winner) |
|------|--------|---------|--------------------:|
| C8 vs D6 | C8 | 1, 1 | 0.60 |
| C5 vs D6 | C5 | 1, 1 | 0.60 |
| C4 vs D6 | C4 | 1, 1 | 0.60 |
| C8 vs D10 | C8 | 2, 2 | 0.70 |
| C5 vs D10 | C5 | 2, 2 | 0.70 |
| C4 vs D10 | C4 | 1, 1 | 0.60 |
| C8 vs D11 | C8 | 1, 1 | 0.60 |
| C5 vs D11 | C5 | 1, 1 | 0.60 |
| C4 vs D11 | C4 | 1, 1 | 0.60 |

D6 ("lied politely") is a good line but its failure is abstract next
to localhost and the flag. D10 fails criterion 2: the unread inbox
is not the failure the user hit. D11's "the map is wrong" is a thinner
image than the top 3's kickers. All three challengers go 0–3.

## C8 vs the live field (strongest sampled entry texts)

| Field line (handle) | Winner | Margins | C8 game score |
|----|--------|---------|----:|
| "The server didn't crash; your deploy overwrote the config with the test file, and the only backup is a screenshot someone took in 2021." (tidy-raven-71) | Field | 1, 1 | 0.40 |
| "Your upload failed: the server ran out of disk space storing error logs about servers running out of disk space. We're deleting the logs. Try again." (jakarta-1928) | C8 | 2, 2 | 0.70 |
| "Your password reset email was sent to the inbox you no longer have access to. That is the problem, not the password." (ultraman) | C8 | 1, 1 | 0.60 |
| "Error: disk full. 0 bytes free — we kept every log, cache, and 'final_FINAL_v2' you swore you'd delete. Free some space, then try again." (masbrian) | C8 | 2, 2 | 0.70 |
| "We deleted the database. The backup was stored in the database." (alro07-2) | Field | 1, 1 | 0.40 |

C8 beats the saturated-angle lines (disk-logs, password, disk-full)
decisively but loses by a hair to the two strongest field lines,
whose images (backup = a screenshot; backup inside the deleted
database) are bigger single punches. Mean vs this sampled field:
0.56. C8's edge over the field is its fresh angle: no other sampled
entry uses the feature-flag scene, so it does not share a joke with
a dozen rivals the way the disk-logs lines do.

## Winner

**C8 — `Someone switched this feature off with a flag called 'temporary_fix' in 2023. The flag is still on; the fix was never temporary. We are switching it back on. Try again in 2 minutes.`**
181 characters, 181 bytes (90.5% of the 200-character budget).
Unbeaten in the bracket (7–0), mean game score 0.614 — clears the
0.60 bar; runners-up 0.586 / 0.543. Final standings with the
challenger round included: C8 0.614 over 7 bracket games, C5 0.586,
C4 0.543.
