Thai
====

(I prefer "Siamese" if you please...)

* **HOW**: Personal interaction
* **HOW LONG**: Let's say since Nov 2023
* **WHY**: Dating a Thai girl, also simple? grammar, beautiful script

## Writing System

TLDR beautiful but not trivially phonetic, full of detritus from past sound changes and custom letters to preserve the Sacred Spellings of Sanskrit loanwords, etc. LTR reading order, with occasional local violations from prefixed vowels. Stacked vowel and tone modifiers above (occasionally below) characters.

[r12n reference](https://r12a.github.io/scripts/thai/th.html)

### Romanisation(s)!!

TLDR there's no clear winner de factor standard across contexts. Several competing de-facto-ish. There's the orthographic transliteration standard ... which preserves the silent / reordered letters etc... might as well just learn the script. There's also the de jure Royal system used on signs in Thailand, but it seems to have made unfortunate concessions to weird English orthographic conventions (ee, oo) and doesn't mark tone or vowel length >:( Wiktionary uses something called [Paiboon](https://en.wiktionary.org/wiki/Wiktionary:Thai_romanization) which I'll use here (as [Paiboon+](https://slice-of-thai.com/pronunciation-guides/#paiboonplus)).

### Consonants

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

Basic Consonants are the core set used to express all the sounds in Thai, i.e. what you'd use to write your own name:

- f ฟ p พ bp ป b บ, t ท dt ต d ด, k ค g ก, ch ช j จ
- n น m ม y ย w ว r ร s ส l ล ng ง h ห

My name: โจ ไจาคุโบวิค joo jaakuboowik

### Glyph 2 Class Algorithm

The 40 *initial* consonants are divided between the Hi/Mid/Lo classes. I regret to inform you that these names are calqued from ancient sources and exactly why they were named this way is considered an open mystery. They're just opaque class names like A/B/C with no simple relationship to the tones. Sad!

10 are High, 8 are Middle, and 22 are Low. So a consonant is most likely to be Low, at just over 50%, followed by High, at 25%, followed by Middle, at 20%.

However, some features immediately predict class:

- Resonants (n m ng w y r l) are all Low (graphically; phonetically, they have High variants, written by prefixing h ห)
- Sibilants (s, and I'll include h) have High and Low versions but the Lows seem rare.
- f has a High and a Low version, but I'll class it as an ultra-aspirated p (see next).

All the complexity is concentrated in the remaining 22, stops and affricates (p/t/k/ch and variations - call this Class X):

```
P(hi  | X) = 5/22 ~< 25%
P(mid | X) = 8/22 ~> 33%
P(low | X) = 9/22 ~> 33%
```

Unaspirated (bp, b, dt, d, g, j) are Mid. If aspirated (p, t, k, ch), it's probably Low (67%), else High (33%).

#### Sanskrit/Sukothai Import Rules
According to [this](https://omniglot.com/writing/thaisanskrit.htm), the following rules seem to take us from Sanskrit/Sukothai sounds to Thai consonants:

- Everything gets devoiced. Thai adds novel voiced glyphs (to Mid, of course) for b บ d ด rd ฎ (??)
- All Sanskrit rhotacism disappears, because Thai doesn't have that. rt ฏ rth ฐ rd ฑ rdh ฒ rn ณ rs ษ
- Any voice from Sanskrit or Sukothai *turns into* aspiration in Thai and goes Low. Hence so many in that category. g ค gh ฆ d ท j ช jh ฌ b พ bh ภ
- Unvoiced aspirateds just move High. kh ข th ถ rth ฐ ph ผ chh ฉ
- As usual, all n's move Low. rn ณ ny ญ
- All s's move High. rs ษ sh ศ (low s ซ comes from Sukothai z)

### Keyboard Layout

TLDR Kedmanee is their QWERTY: ergonomically suboptimal but ubiquitous de-facto standard. Pattachote is their DVORAK, designed to be more efficient but supported less. Basic letters are default, weird/rare/Indic letters via Shift.

[Online keyboard](https://www.branah.com/thai)

Kedmanee memory aids / notables:

- m ม is actually next to the m key, on the right (,)
- s ส, which looks like l ล, is on the l key (ล is on right-square `]`)

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

Then I discovered this diagram on the [Wikipedia page](https://en.wikipedia.org/wiki/Thai_script#Tone):

![](https://upload.wikimedia.org/wikipedia/commons/f/f9/Thai_tone_rules.png)

and it's all a visual-memory shape rotator like me needs, so forget the procedure above. See `glyph2tone.md` for full details.

R-exception: I was very confused by the word อร่อย àrɔ̀i "tasty", which under the above rules with ร allegedly low-class, ought to have falling tone. Instead, it has low tone. My conclusion is that ร is normally low-class, but just as ห makes it high-class (หร), อ makes it mid-class (อร) while still remaining as an initial vowel sound. I could only find one other word in the language, อรุณ àrun, that begins with อร, but in the absence of a tone mark its mid tone is consistent with both mid and low class. So perhaps the word อร่อย should just be treated as an exception to what seem like otherwise perfectly regular tone rules. Other words, such as ร่าง râang, ร้าน ráan, and ราม raam are all consistent with ร as low-class.
