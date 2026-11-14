# Ostrich

**A private daily look at your money. Every number is welcome.**

Many people avoid looking at their money when the news might be bad (the "ostrich effect"). Ostrich makes the look small, calm and private: type three rough numbers, see your net worth, and read two words: *You looked.* No red or green, no streaks, no judgment, and your numbers never leave your device.

Built for the NEAR Private AI Hackathon, New York, November 2026.

**Try it:** [overachievercat.github.io/ostrich](https://overachievercat.github.io/ostrich/), on any phone or computer. The Ostrich website, with the whole story from the pitch deck, is at [overachievercat.github.io/ostrich/site/](https://overachievercat.github.io/ostrich/site/) (`site/` in this repo). Tap "Try the demo with made-up numbers" if you'd rather not type your own.

## Try it in two minutes

1. Open the live link above. You see **What is Ostrich?**, with three promises.
2. Tap **Try the demo with made-up numbers**. You see one question, how it feels to look; pick any answer and tap **Next**. You see three totals already filled in, and a banner saying they are made up.
3. Tap **See my number**. You see the net worth, **"You looked."**, how you felt before, five emoji to say how you feel now, and a line of six months of made-up looks.
4. Tap the **Today's snack** card. You see "Your net worth is not your self-worth", a line you can keep, and "Why?" with its source.
5. Back on your number, tap **What was sent?**. You see that nothing left your device, and the only totals a private AI reading would ever get.
6. Tap **Hide all** at the top. The screen is covered; press and hold **Hold to show** to bring it back.
7. Tap **Your accounts (concept)** or **How the private AI works (concept)**. Each screen is labelled "Concept · not connected".
8. On the numbers screen, type a NEAR account (for example `near`) in **Have a NEAR account?** and tap **Read**. You see its NEAR balance and its dollar value, added to "Anything invested". Tap **See my number**, then **What was sent?**: it names the account that was sent, and nothing else.
9. To use your own numbers: tap **Change today's numbers**, then **Next**, then **Use my own numbers instead**; type three totals and tap **See my number**. The made-up looks are cleared. Reload the page: your look is still there, saved only in this browser.

## Run it yourself

No install and no build step. Either open `index.html` in a browser, or serve the folder:

```
git clone https://github.com/overachievercat/ostrich.git
cd ostrich
python3 -m http.server 8000
# then open http://localhost:8000
```

There are no API keys and no server. The only network calls are the optional NEAR read: `POST` `view_account` to `https://free.rpc.fastnear.com` (falling back to `rpc.mainnet.fastnear.com`, then `near.drpc.org`) and `GET https://1click.chaindefuser.com/v0/tokens` for the NEAR price.

## In prototype (works today, in this repo)

- **What is Ostrich?** A short opening page: what it is, why it's called Ostrich, and three promises (one look a day, your feelings count, only on your device), with the ostrich lifting its head.
- **The daily look.** Enter cash, what you've put away and what you owe; see your net worth today. One look per day; changing today's numbers replaces today's look.
- **"You looked."** Every look ends the same calm way, whatever the number, negative ones included.
- **Compared with your last look.** "Up $140 since your last look (Thu, Nov 12)", in neutral colours.
- **Your looks.** A list of every daily look, newest first.
- **Hide amounts.** One switch hides every number on screen.
- **Stays on your device.** Looks are saved in your browser's local storage. There is no account and no server. The only network request is the optional NEAR read below, and only when you tap Read.
- **Copy my looks (CSV).** Your data, yours to take.
- **Delete everything.** One button, with a confirm step.
- **How does it feel to look?** One question before the numbers: calm to too much. It only sets your pace: "very tense" or "too much" starts with amounts hidden and offers someone to talk to. Not a score; it stays on your device.
- **Hide all.** One tap at the top covers the whole screen, for a shared phone or someone looking over your shoulder. Press and hold to bring it back.
- **What was sent?** Shows that nothing left your device, and exactly which totals the private AI reading would see once it exists.
- **Want to talk to someone?** Free help first: nonprofit credit counselling, free tax help, someone you trust, the National Domestic Violence Hotline and 988. Links and numbers only; Ostrich sends nothing about you.
- **Your feelings, beside your number.** The daily look shows how you felt before you looked, and asks how you feel now, with five emoji. Your feeling is kept beside that day's number in Your looks.
- **Today's snack.** After the daily look, one short snack: "Your net worth is not your self-worth." You can keep a line in your own words ("My number is not my worth."), see why Ostrich says this and how strong the evidence is, and finish with "That's this snack. What you do next is yours."
- **Your number over time.** After a few looks, one line shows your number since you started, with a tap-to-read value for any day. No red or green.
- **Read a real NEAR account (new, works today).** On the numbers screen, type a NEAR mainnet account (for example `yourname.near`) and tap **Read**. Ostrich reads its NEAR balance from a public NEAR RPC (FastNEAR, with fallbacks), gets the NEAR price in US dollars from the NEAR Intents 1Click token list, and adds the dollar value to "Anything invested". Read only: no wallet connection, no signing, no API key. Staked NEAR isn't counted yet. "What was sent?" then says exactly what left the device: the account name, and nothing else.
- **Made-up numbers.** Try it without typing your own; the demo adds six months of a made-up member's looks so you can see the line, all labelled "made up". Saving your own numbers clears the made-up ones.

## Concept screens (clickable, not connected)

Two sets of screens show where Ostrich is going. Each is labelled "Concept · not connected", and none of them connects to anything or sends anything.

- **Your accounts, kept up to date.** Banks and credit cards through Plaid (read only), brokerage and retirement, angel investments by hand, mortgage, student loans, car payment, a NEAR wallet and DeFi, other chains reached through NEAR or by wallet address, and anything else by statement or by hand. The totals would refresh each morning on your phone; your job stays the same: look once a day, and update your setup when your money life changes.
- **How the private AI reading would work.** Totals go from your phone to an AI inside a trusted execution environment on NEAR AI Cloud (Intel TDX with NVIDIA confidential GPUs). The hardware signs an attestation that anyone can check, like a transaction on a block explorer. A sample attestation card is shown. A diagram splits all your money into real-world finance and crypto (w = t + k), and crypto into what NEAR reaches, through Chain Signatures and NEAR Intents, plus the rest (k = x + n). As assets are tokenized and NEAR reaches more chains, more of your number can be read automatically.

## Roadmap (designed, not built)

- **Private AI reading** on NEAR AI Cloud: a short reading of your totals only (never your transactions), run in a private environment so no one, including Ostrich, can see them.
- Linking bank accounts and crypto wallets, read only.
- "Snacks": short lessons, one per visit, built on research about money and behaviour.
- Voice and offline versions for low-cost phones.
- Membership (Ostrich Plus, Feathers) and member ownership. Ostrich never sells data, never lends to members, never shows offers and never takes a cut of members' money.

## How it's made

One HTML file with plain CSS and JavaScript, plus the Newsreader and Inter fonts in `fonts/` (SIL Open Font License), shipped with the app so opening it sends no request anywhere. The NEAR read uses the browser's built-in `fetch`, with no SDK. No build step, no dependencies, no tracking. The look follows the Ostrich screen designs.

## NEAR in this submission (honest scope)

This submission is for Track 03, Privacy & Private AI.

- **Built and working:** the read-only NEAR account read (NEAR RPC `view_account` plus the NEAR Intents 1Click price list), written on November 14 during the hackathon. It sends only the account name you type, and "What was sent?" says so. The rest of the prototype keeps everything on your device.
- **Designed, not built:** the private AI reading on NEAR AI Cloud (a TEE with attestation), NEAR Intents balances, staked NEAR and other chains. These are clickable screens labelled "Concept · not connected" and make no calls. A real NEAR AI Cloud call needs an API key, and keys are never put in this public repo.

## Built during the hackathon

- Every commit in this repo is from November 13 and 14, 2026, during the hackathon. There is no earlier code. The repo was created for this event.
- The submitted version is tagged `hackathon-submission`.
- Built solo by Nadia Choi. Most of the code was written by AI (Claude Code, by Anthropic) from her designs, decisions and testing with five people; she reviewed and tested each change.
- No libraries, templates or boilerplate. The only third-party files are the Newsreader and Inter fonts (SIL Open Font License 1.1; licences in `fonts/`).
- Nadia is not submitting any other project.

## Licence

MIT. See [LICENSE](LICENSE). The fonts in `fonts/` keep their own SIL Open Font License.
