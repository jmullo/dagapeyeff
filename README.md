# The d'Agapeyeff cipher (1939): what the digits show

In 1939 Alexander d'Agapeyeff, a Russian-born British cartographer, published *Codes and
Ciphers* (Oxford University Press), a popular introduction to the subject. Its last page
(p.158 in the Gale 1974 facsimile; p.144 in the 1949 "revised and reset" edition) closes the
chapter on deciphering with a challenge: "Here is a cryptogram upon which the reader is invited
to test his skill." It gives 395 digits in five-figure groups, and no method or hint. Nobody has
solved it. The challenge was dropped from later printings, and d'Agapeyeff is said to have
forgotten how he made it.

```
75628 28591 62916 48164 91748 58464 74748 28483 81638 18174
74826 26475 83828 49175 74658 37575 75936 36565 81638 17585
75756 46282 92857 46382 75748 38165 81848 56485 64858 56382
72628 36281 81728 16463 75828 16483 63828 58163 63630 47481
91918 46385 84656 48565 62946 26285 91859 17491 72756 46575
71658 36264 74818 28462 82649 18193 65626 48484 91838 57491
81657 27483 83858 28364 62726 26562 83759 27263 82827 27283
82858 47582 81837 28462 82837 58164 75748 58162 92000
```

This does not solve it. It records what the digits themselves establish, what that rules
out, and why. Every search below was first shown to find what it looks for in simulated
texts (a "power check"), then run on the real cipher and on shuffled copies of it.

## Notation

- **Solid**: follows from counting or direct checking, or from a test fixed in advance.
- **Likely**: significant, but the feature was noticed before it was tested.
- **Possible**: fits the data; nothing independent supports it yet.
- **Open**: not settled.

## What the digits show

### 1. Pairs of digits, from a 5 × 5 square, in a 14 × 14 grid (solid)

Read in pairs, every one of the 196 pairs has a first digit from 6, 7, 8, 9, 0 and a second
digit from 1-5: cells of a 5 × 5 square with labelled rows. 196 = 14 × 14, and the trailing
`000` fills the last group of five. No digit was dropped or added anywhere: either slip would
flip the alternation for the rest of the text, and the pattern is unbroken in all 196 pairs.

The format matches the **Mirabeau cipher** in L. C. S. Mansfield's *The Solution of Codes and
Ciphers* (1936, pp.29-33). There each letter is a group label plus a position 1-5. Mansfield's
example denominator line, `71 64 92 74 94 85 65 91 75 83`, has the challenge's exact layout and
uses the same pairs. d'Agapeyeff mentions Mansfield in his text but leaves him out of his
bibliography. His own book shows the same surface form too: its "German Army Cipher" (p.103)
turns letters, letter groups and words into two-digit numbers from a 10 × 10 table with
mixed-order row and column labels, and prints them run together in five-figure groups
(`42967 93823 75232 …`).

### 2. The last column is different, and the rest uses only 13 symbols (solid)

Written as 14 rows of 14 pairs, every rare pair (92, 93, 94, 04, 71) falls in column 14. The
other 182 pairs (the "body") use exactly **13** different cells, evenly (chi-square 8.7 on 12
degrees of freedom), and never any of the rare ones.

### 3. So it is not one letter per pair, in any language, under any transposition (solid)

A transposition moves symbols but never changes how often each one occurs. 182 letters of
English always use 18 or more different letters (0 of 20,000 samples used 13 or fewer), and
none come close to using 13 letters evenly. So no "square substitution, then any
transposition" can have produced the body, whatever the square, key or language. This
excludes the model behind most published attacks.

### 4. The body looks like random symbols (solid)

On every statistic tried, the 182 body symbols cannot be told apart from a random sequence
over 13 equally likely symbols: counts, adjacent pairs, repeats, doubles, triples, periodic
coincidences at periods 2-26, and dependence between neighbours (all p between 0.15 and 0.76).
An English text through any fixed two-letters-per-symbol code is far less even (E alone is
12.7% of English; the body's most common symbol is 11%). Something removed all letter
structure: a key that never repeats, a code, or text with no meaning.

### 5. The text was laid out as three messages, with formatting added on top (likely)

The only two triples, `75 75 75` and `63 63 63`, both end exactly at the end of a row, just
before column 14 (p ≈ 0.001 against shuffles). The two messages they close also open with the
symbol their triple repeats: row 1 starts with 75, row 4 with 63 (p ≈ 0.004, noticed by eye). The
book itself says triple letters mark the end of a message (p.113). Read this way there are
three messages (rows 1-3, 4-7 and 8-14), and the 14 × 14 layout is how the text was written.
That argues against any transposition that moves columns. Since the triples survive intact
while everything else is flat, they were added after whatever made the body.

Most of the challenge's ingredients sit within ten pages of the book's Chapter V, "Military
Codes and Ciphers": two-digit numbers printed in five-figure groups (the German Army Cipher,
p.103), number keys that use only a corner of the 10 × 10 grid (a German spy cipher, numbers
11-38, p.104), Lord Wolseley's square, whose 25 cells fall into 13 numbered classes, with
dummy letters (pp.109-111), and the triple end-of-message marker (p.113). If he assembled the
challenge from his own material, this chapter, together with Mansfield's Mirabeau for the pair
format, is the likeliest source.

### 6. The 13 cells are where A-M fall in a keyword square (possible)

Numbered in reading order, the 13 body cells sit in a tight window of the 25-cell square
(1 in 5,000 for random cell sets), with two gaps. That is exactly where the letters A-M land in
a keyword-mixed square with Q left out (as in d'Agapeyeff's own square on p.16), for many
ordinary keywords; the column-14 cells then fall on N-Z letters. It would mean the body is
written in the first half of the alphabet. But the window measure was chosen after looking,
and a 13-symbol alphabet simply written into the first cells of a square explains it as well.
Every key method tested under this model came out negative (below).

### 7. The author's own mistakes don't explain it (solid)

Seventeen worked examples in the book, letter and number ciphers, can be recomputed from the
page; all were checked against the page images. He applies the methods correctly. His hand
encipherment leaves isolated wrong letters or numbers (about 1 in 14-30: Beaufort wheel,
Playfair, transposition readout, the French Auvray number cipher), and his one
systematic error is the direction of the Russian Nihilists' double transposition, copied from
Kerckhoffs. Neither kind of error can turn English into 13 even symbols: wrong cells add
symbols rather than remove them, and transpositions keep counts. "He botched a method from his
own book" would need an error he makes nowhere else.

## What is ruled out

Searches were power-checked on simulated texts; the rest follow from counts.

- One letter per pair, with or without any transposition, in any language (§3).
- Periodic keys over the grid (Nihilist, Vigenère, Gronsfeld), periods 2-26; nulls at regular
  spacing; a separate alphabet per message or row; column 14 as a checksum.
- Only the 1-5 digits carrying the message; Mansfield's fraction layout; a straddling
  checkerboard; fixed groups of 2-3 symbols per letter; digit-level fractionation.
- A dictionary or number code as written, under single columnar transposition (widths up to
  about 10), double columnar (widths 5-7) or a Nihilist square; a number code written as letters.
- Two letters per symbol (Wolseley's square, Porta pairs, any fixed pairing) without a key;
  also Wolseley's square with the cell number written instead of the partner letter (exactly
  13 symbols) and a new keyword for each message, with or without dummies: the third message
  is far too even for it.
- Any passage of d'Agapeyeff's or Mansfield's book as the plaintext, under his own letter
  pairings (Porta, Wolseley) and any transposition: no passage of English has letter counts
  that fit.
- Under the A-M model (§6): the book's three ways to hide a key's period (p.122: autokey; one
  key letter per word, for any keyword; an interrupted key, for any keyword of 4-7 letters); a
  repeating keyword up to 20 letters; a running key from any page of d'Agapeyeff's or
  Mansfield's book, under 16 table-reading rules; every key and every example message printed
  in the book, as a key.
- Only the denominator line of a Mansfield Mirabeau being printed, when the key alphabet comes
  from an ordinary word or phrase.

## What is open

- **What makes the body.** It has to lose information (13 symbols for 26 letters) and leave
  no structure: a non-repeating key over a 13-symbol system, a code under a transposition too
  wide to search, or text built to look like a cipher. With 182 symbols and letter-level
  statistics, a key longer than about 40 letters can't be found: wrong keys outscore the true
  one. The symbols do carry enough information to fix both a message and an unknown English
  running key (about 670 bits, against roughly 400-500 needed), so only a far stronger language
  model than letter statistics could test that case.
- **What d'Agapeyeff said.** The earliest discussions are not available online: David
  Shulman's articles in *The Cryptogram* (1952, 1959), Jim Gillogly's (1994) and Wayne
  Barker's in *Cryptologia* (1978). They are the most likely place to find what he told people.

## How this was done

The analysis on this page was carried out with Claude Opus 5.5. It was used to write and run the
statistical tests and searches, check them on simulated texts and shuffled copies of the
cipher, recompute the worked examples in d'Agapeyeff's book against the page scans, and
research the cipher's history and earlier attempts.

## Sources

- A. d'Agapeyeff, *Codes and Ciphers*, Oxford University Press 1939; Gale Research facsimile
  1974, [Internet Archive `codesciphers0000daga`](https://archive.org/details/codesciphers0000daga).
  Challenge p.158; examples pp.33-35, 50-51, 109-126, 141-158.
- L. C. S. Mansfield, *The Solution of Codes and Ciphers*, Alexander Maclehose 1936,
  [Internet Archive `solutionofcodesc0000unse`](https://archive.org/details/solutionofcodesc0000unse).
  Mirabeau cipher pp.29-33 and 151-153.
- Craig P. Bauer, *Unsolved! The History and Mystery of the World's Greatest Ciphers*,
  Princeton University Press 2017, ch. 9 (the "forgot the method" statement).
- Wayne G. Barker, "The Unsolved D'Agapeyeff Cipher", *Cryptologia* 2(2), 1978, 144-147
  (not seen).
- David Shulman ("Ab Struse"), "The d'Agapeyeff Cryptogram: A Challenge", *The Cryptogram*
  Apr-May 1952; "d'Agapeyeff Cipher Postscript", Mar-Apr 1959; Jim Gillogly ("Scryer"),
  "d'Agapeyeff, Mansfield, and Mirabeau", *The Cryptogram* Nov-Dec 1994 (not seen; ACA archive).
- [Wikipedia: D'Agapeyeff cipher](https://en.wikipedia.org/wiki/D%27Agapeyeff_cipher);
  [Cipher Mysteries](https://ciphermysteries.com/category/historical-ciphers/dagapeyeff-cipher)
  (Nick Pelling, 2008-2021, with comments).
- Recent work, all negative, all treating each pair as a cipher letter:
  [Ruben Gariazzo (Zenodo, 2026)](https://zenodo.org/records/22057249),
  [Tim Marland (2026)](https://dagapeyeffresearch.com/),
  [Erik van Eykelen (MsgTrail, 2026)](https://msgtrail.com/posts/unmasking-the-dagapeyeff-cipher-a-multi-faceted-architecture).
- English letter statistics: Project Gutenberg texts (*Pride and Prejudice*,
  *The Adventures of Sherlock Holmes*; *The Hound of the Baskervilles* held back for tests).

## Credits

- **Jim Gillogly** (1994) identified Mansfield's book and the Mirabeau cipher as
  d'Agapeyeff's unacknowledged source.
- **Nick Pelling and his correspondent Marie** (Cipher Mysteries, 2017) traced the Nihilist
  example to Kerckhoffs and found its reversed direction; **Cyril Pineau** (2026 comments) showed
  the key is an involution, which hides the reversal.
- **Menno Knul and Nick Pelling** reported that the 1949 edition keeps the challenge with the
  same digits, including the lone 04.
