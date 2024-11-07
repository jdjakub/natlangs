Thai's writing system was designed for version 1.0 of the language, which was last spoken like 1000 years ago. This is a common tale with languages. Thai has received system updates over the years which have changed the way things sound. To read written Thai and convert into speech phonemes, we'll start at version 1.0, then apply the sound changes.

Warning: this is my *FICTIONAL* history loosely based on the true story, optimised for learning Thai and nothing else.

# Thai 1.0 ("Old Thai")
(conceptually 1000 years ago, don't quote me on this)

## Thai 1.0 Consonants

(Ad-hoc Paiboon++)

|            | Aspirated | Preglottalised | Unvoiced | Voiced | Pali |
|------------|:---------:|:--------------:|:--------:|:------:|:----:|
| Labials    |    ผ ph   |      บ ʔb      |   ป bp   |   พ b  |      |
| Dentals    |    ถ th   |      ด ʔd      |   ต dt   |   ท d  |      |
| Affricates |   ฉ tch   |                |   จ ch   |   ช j  |      |
| Velars     |    ข kh   |                |    ก k   |   ค g  |      |
| Sibilants  |           |                |    ส s   |  ซ zh  |      |
| Fricatives |           |                |    ฝ f   |   ฟ v  |      |

## Thai 1.0 Tones
Thai live syllables have three tones: high, neutral, low. Dead syllables copy the "low" tone. I've no idea what these sounded like but it's OK because we're not learning to pronounce Thai 1.0.

Thai is the first written language to have explicit marks for its tones! The default "neutral" tone wisely goes unmarked. They mark the lòw tone with "mark one" and hígh with "mark two". These are fancy Sanskritty number words, not native Thai; I'll gloss them with fancy English equivalents:

1. ไม้เอก mái èek i.e. Mark One (Mark Primus): ◌่ even looks like a little 1! Low tone e.g. ก่อน gɔ̀ɔn "before"
2. ไม้โท mái-too i.e. Mark Two (Mark Secundus): ◌้ even looks a bit like a little 2! High tone e.g. ไม้ mái "mark"

Simple! Algorithm:

- I see Mark One ◌่ => low tone
- I see Mark Two ◌้ => high tone
- I see no mark =>
  + Live => neutral tone
  + Dead => add Mark One ◌่ and restart

# Thai 2.0
## Consonant Update: De-voice / De-glottalise

## Tone Update: Split Live, Merge, Split Dead, Copy

1. Each tone gets a new variant split off for the formerly-voiced initials, leaving six tones.
2. New-low merges with old-high, leaving five tones.
3. Devoiced-initial dead syllables with a *short* vowel now copy new-high; others continue to follow old-low or new-low as appropriate.
4. Mid-class initials copy "low-class" when unmarked, "high-class" when marked.

All we know are the results of this process:

- Old-neutral is now "rising" ǎ, new-neutral is "middle" a
- Old-low is now "low" à, new-low is "falling" â
- Old-high is now "falling" â, new-high = "high" á

For all I know, the "old" tones (high/mid-class initials) could have sounded similar to these, or could have changed as well.

Dead syllables work almost the same as before - add Mark One and use that tone - except in the single case of "new class, short vowel" in which case Mark Two is added instead (resulting in "high" tone).

It's crazy how the so-called "low" class doesn't contain any low tones!! True, "falling" ends low, but I would never think to name it "low". "Low"-class is the only one that can make the "high" tone!! And the so-called "high" class has a monopoly on the "rising" tone that sounds pretty low to me!

I hereby rename the classes to something more useful:
- Rising initials have rising tone by default ("high-class")
- High-sounding initials don't have low/rising tones ("low-class")
- Copying initials copy High-sounding in unmarked live only, and copy Rising elsewhere ("mid-class")

(Back to normal Paiboon+)

| Rising ("high-class") |    Copying ("mid-class")   |       High-sounding ("low-class" 🙃)      |
|:---------------------:|:--------------------------:|:----------------------------------------:|
|    ผ p ถ t ฉ ch ข k   | บ b ป bp ด d ต dt จ ch ก g | Formerly voiced: พ p ท t ช j ค k ซ s ฟ f |
|        ฝ f ส s        |                            |  Sonorants ม m น n ง ng ว w ร r ล l ย y  |
|          ห* h         |            อ* _            |                   Pali                   |

Algorithm:

- I see Mark One ◌่ => low tone.
  + But if low tone is impossible (i.e. High-sounding initial) => falling tone.
- I see Mark Two ◌้ => falling tone.
  + But if High-sounding initial, this tone is already taken by Mark One ◌่ => High tone.
- I don't see a mark =>
  + Live => Rising initial gets rising tone, else neutral
  + Dead => add Mark One ◌่ and restart
      * Unless it's a High-sounding initial with short vowel => add Mark Two ◌้ and restart (i.e. high tone)

## Tone Update: Add Chinese loanword tone marks
The Thai borrowings from nearby Chinese languages (Teochew apparently) wanted to faithfully maintain the rising/high tones on Copying-class initials, so they added Mark Three and Mark Four. Of course, this was not Sino-Thai *sam* and *si*, but continuing in fancy Sanskrit-esque:

- ไม้ตรี mái dtrii i.e. Mark Three (Mark Tertius) ◌๊ which kinda looks like a numeral 3 on its side: high tone e.g. โต๊ะ dtó "table"
- ไม้จัตวา mái jàt-dtàwaa i.e. Mark Four (Mark Quattuor!) ◌๋ which kinda looks like the 4 without diagonal: rising tone e.g. กว๋ยเตี๋ยว gǔai-dtǐao "noodles" (useful word!)

Because these are only used for the special case of Chinese-originating loanwords, they're pretty rare and beginners should not be misled by seeing them on the chart, as if they're somehow on a par with the other Thai tone marks. They're super easy because they only appear on Copying-class initials.

## Consonant Clusters

epenthetic vowels, second-consonant rule

## Vowels

why so many different ways to write? one answer: aids with word segmentation

## Word Segmentation
