# Cipher Machine

Eight historical ciphers, from a Hebrew scribe's mirror alphabet to the
Wehrmacht Enigma, running entirely in your browser.

**[Try it →](https://YOURNAME.github.io/REPONAME/)**

No server, no build step, no dependencies. One HTML file.

---

## The ciphers

| | Cipher | Era | Key |
|---|---|---|---|
| 🔁 | **Atbash** | Judea, c.600 BC | none |
| | **Caesar** | Rome, c.50 BC | a number, 0–25 |
| | **Rail Fence** | uncertain | number of rails |
| | **Vigenère** | Italy, 1553 | a keyword |
| | **Playfair** | London, 1854 | a keyword |
| 🔁 | **Beaufort** | England, 1857 | a keyword |
| 🔁 | **Enigma** | Germany, 1918 | e.g. `I II III AAA` |
| 🔁 | **ROT13** | Usenet, 1980s | none |

🔁 = reciprocal: the same operation encrypts and decrypts.

### Enigma keys

The simplest form is three rotors and three start positions:

```
I II III AAA
```

Rotors are Roman numerals `I` to `V` and must be given left to right, as
they sit in the machine. Ring settings and plugboard pairs can be added:

```
I II III AAA BBB          with ring settings
I II III AAA BBB AB CD    with ring settings and two plug pairs
```

This is Enigma I with reflector B, including the double-stepping quirk of
the real machine — and, faithfully, its fatal flaw: **no letter ever
encrypts to itself.** Type two hundred A's and count how many come back.

---

## Where this came from

This is the browser version of a physical cipher machine — a Raspberry Pi
Zero 2 W with a small SPI screen, running the same eight ciphers in a
terminal interface, built as a gift for a teenager who likes codes.

The Python and JavaScript implementations are checked against each other
across **2,304 test vectors** covering mixed case, punctuation, doubled
letters, empty input and malformed keys. Both produce identical output, so
a message encrypted on one decrypts on the other.

---

## Privacy

Everything happens in your browser. There is no back end, no analytics, no
cookies, and nothing is stored. Your text is never transmitted anywhere,
because there is nowhere for it to go.

The page makes exactly one network request, for two fonts from Google
Fonts. If you would rather it made none at all, delete the two `<link>`
tags marked in the `<head>` — the page falls back to your system's
monospace font and works identically.

---

## Running it yourself

Download `index.html` and open it. That's the whole process. It works
offline, from a USB stick, or from a folder on your desktop.

To host it, put `index.html` in the root of a public repository and turn on
GitHub Pages under **Settings → Pages → Deploy from a branch → main →
/ (root)**. Netlify, Cloudflare Pages and Vercel all work the same way.

---

## A word of warning

**Do not use any of this to protect anything that matters.**

Every cipher here has been thoroughly broken, most of them a very long
time ago. Caesar falls to twenty-five guesses. Vigenère fell to Kasiski in
1863. Enigma fell to Polish mathematicians and then to Bletchley Park.

That is exactly why they are worth playing with. Each one is small enough
to hold in your head and work with a pencil, and you can see precisely why
it was trusted and precisely why it stopped being trustworthy. Modern
cryptography is unbroken but opaque; these are broken but transparent.

---

## Licence

<!-- Pick one and delete this comment. MIT is the usual choice for
     something like this: short, permissive, lets anyone reuse it as
     long as they keep the copyright notice. Add the full text as a
     LICENSE file in the repo root — GitHub can generate it for you
     via Add file → Create new file → type "LICENSE" → Choose a
     license template. -->

MIT

---

If this was any fun, you can [buy me a coffee](https://ko-fi.com/thedemonverse).
