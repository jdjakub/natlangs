Thai
====

(I prefer "Siamese" if you please...)

* **HOW**: Personal interaction
* **HOW LONG**: Let's say since Nov 2023
* **WHY**: I'm dating a Thai girl, also simple? grammar, beautiful script

## Writing System

TLDR beautiful but not trivially phonetic, full of detritus from past sound changes and custom letters to preserve the Sacred Spellings of Sanskrit loanwords, etc. LTR reading order, with occasional local violations from prefixed vowels. Stacked vowel and tone modifiers above (occasionally below) characters.

[r12n reference](https://r12a.github.io/scripts/thai/th.html)

Some logical glyph features conveying reliable info, e.g:

- Aspirated p พ lengthens to f ฟ
- Those were the more common *low-* class versions, high-class flips the loops: p ผ f ฝ
- Voiced d ด "breaks" at the top to unaspirated t ต
- Voiced b บ lengthens to unvoiced p ป

Unfortunately the other lookalikes don't have an obvious pattern:

- Aspirated k ค vs voiced d ด
- High-class aspirated t ถ vs low-class aspirated p ภ (at least here and with p/f, right-facing loop = high and left-facing loop = low)
- High-class aspirated k ข, low-class aspirated ch ช, low-class s ฃ
- Low-class aspirated t ท, h ห, m ม, n น
- High-class s ส vs low-class l ล

Indic-originating consonants ([source](https://en.wikipedia.org/wiki/Thai_spelling_reform_of_1942)):

- Retroflex d ฎ, t ฏ (spot the difference? t-"breaking"), th ฐ ฑ ฒ, n ณ
- ...

### Keyboard Layout

TLDR Kedmanee is their QWERTY: ergonomically suboptimal but ubiquitous de-facto standard. Pattachote is their DVORAK, designed to be more efficient but supported less.

[Online keyboard](https://www.branah.com/thai)

Kedmanee memory aids / notables:

- m ม is actually next to the m key, on the right (,)
- s ส, which looks like l ล, is on the l key (ล is on right-square `]`)

### Romanisation(s)!!

TLDR there's no clear winner de factor standard across contexts. Several competing de-facto-ish. There's the orthographic transliteration standard ... which preserves the silent / reordered letters etc... might as well just learn the script. There's also the de jure Royal system used on signs in Thailand, but it seems to have made unfortunate concessions to weird English orthographic conventions (ee, oo) and doesn't mark tone or vowel length >:( Wiktionary uses something called [Paiboon](https://en.wiktionary.org/wiki/Wiktionary:Thai_romanization) which I'll use here (as [Paiboon+](https://slice-of-thai.com/pronunciation-guides/#paiboonplus)).

### Glyphs 2 live/dead Algorithm

I see a tone mark => must be a live syllable (but this is useless info? see tone algo.)

Else:

- Syllable ends on resonant *sound* m/n/w/y, post-glyph2phone: LIVE, e.g. น้ำ nám "water"
- Syllable ends on stop *sound* p/t/k, post-glyph2phone: DEAD, e.g. สิบ sìp "ten", มาก mâak "lots of"
- Syllable ends on glottal stop: idk seems to be a toss-up
- Syllable ends on long vowel: LIVE, e.g. ดี dii "good"
- Syllable ends on short vowel: DEAD, e.g. ส sà in สวัสดี sàwàtdii "hello" (notice spelling from Sanskrit स्वस्ति svasti)

### Glyphs 2 Tone Algorithms

This is what I'm currently trying to grok.

Practice for my Bayesian language learning fever dreams.

Tone mark and syllable type (live/dead) is the most important info for prediction, followed by initial consonant class (high/mid/low). However, tone mark is *immediately* visible to my eyes; if absent, syllable type takes some cognition across the syllable, and consonant classification requires a lookup. Any tone mark means the syllable is live; `P(live | tone mark) = 1`, so `P(tone | live, tone mark) = P(tone | tone mark)`.

I see a tone mark:

- It's mái too (  ้ ), the "inverter". Initial consonant class is:
  + Low: inverts "low" initial to "high" tone, e.g. น้ำ nám "water"
  + Mid/High: inverts "high" initial to falling tone, e.g. ห้า hâa "five"
- It's mái èek (  ่ ), the "lowerer". Initial consonant class is:
  + Low (seems rare): goes falling, e.g. ค่ะ kâ (feminine agreement particle)
  + Mid/High: lowers to low tone, e.g. สี่ sìi "four"
- (Rare) it's mái dtrii (  ๊ ), raises to high e.g. โต๊ะ dtó "table"
- I haven't even encountered the + tone mark yet. Must be rare

Memory: mái too (  ้ ) is the น้ำ nám / ห้า hâa mark; mái èek (  ่ ) is the low mark.

I don't see a tone mark:

- Live syllable. Initial consonant class is:
  + Low/Mid: mid tone, e.g. ดี dii "good"
  + High: rising tone, e.g. สอง sɔ̌ɔng "two"
- Dead syllable. Initial consonant class is:
  + Mid/High: low tone, e.g. หก hòk "six"
  + Low: vowel length is:
    - Short: high tone, e.g. รัก rák "love"
    - Long: falling tone, e.g. มาก mâak "lots of"

Memory: Two good LIVEs (สอง sɔ̌ɔng, ดี dii), lots of love (รัก rák มาก mâak)
