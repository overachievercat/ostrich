# Ostrich

**A private daily look at your money. Every number is welcome.**

Many people avoid looking at their money when the news might be bad (the "ostrich effect"). Ostrich makes the look small, calm and private: type three rough numbers, see your net worth, and read two words: *You looked.* No red or green, no streaks, no judgment, and your numbers never leave your device.

Built for the NEAR Private AI Hackathon, New York, November 2026.

**Try it:** [overachievercat.github.io/ostrich](https://overachievercat.github.io/ostrich/), on any phone or computer. Tap "Try it with made-up numbers" if you'd rather not type your own.

## In prototype (works today, in this repo)

- **What is Ostrich?** A short opening page: what it is, why it's called Ostrich, and three promises (one look a day, your feelings count, only on your device), with the ostrich lifting its head.
- **The daily look.** Enter cash, what you've put away and what you owe; see your net worth today. One look per day; changing today's numbers replaces today's look.
- **"You looked."** Every look ends the same calm way, whatever the number, negative ones included.
- **Compared with your last look.** "Up $140 since your last look (Thu, Nov 12)", in neutral colours.
- **Your looks.** A list of every daily look, newest first.
- **Hide amounts.** One switch hides every number on screen.
- **Stays on your device.** Looks are saved in your browser's local storage. There is no account, no server and no network request in the code.
- **Copy my looks (CSV).** Your data, yours to take.
- **Delete everything.** One button, with a confirm step.
- **How does it feel to look?** One question before the numbers: calm to too much. It only sets your pace: "very tense" or "too much" starts with amounts hidden and offers someone to talk to. Not a score; it stays on your device.
- **Hide all.** One tap at the top covers the whole screen, for a shared phone or someone looking over your shoulder. Press and hold to bring it back.
- **What was sent?** Shows that nothing left your device, and exactly which totals the private AI reading would see once it exists.
- **Want to talk to someone?** Free help first: nonprofit credit counselling, free tax help, someone you trust, the National Domestic Violence Hotline and 988. Links and numbers only; Ostrich sends nothing about you.
- **Your feelings, beside your number.** The daily look shows how you felt before you looked, and asks how you feel now, with five emoji. Your feeling is kept beside that day's number in Your looks.
- **Your number over time.** After a few looks, one line shows your number since you started, with a tap-to-read value for any day. No red or green.
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

One HTML file with plain CSS and JavaScript, plus the Newsreader and Inter fonts in `fonts/` (SIL Open Font License), shipped with the app so opening it sends no request anywhere. No build step, no dependencies, no tracking. The look follows the Ostrich screen designs.

## Licence

Open source. Licence to be added.
