# follyanna
automatic pinyin and furigana ruby tags in js

## Overview
`follyanna` uses intelligent furigana placement to strip redundant kana from furigana readings. It also supports pinyin rendering.

For instance:
* 頑張る[がんばる] -> <ruby>頑張<rt>がんば</rt>る</ruby>
* 加油[jia1 you2] -> <ruby>加<rt>jiā</rt>油<rt>yóu</rt></ruby>

This is helpful because a lot of dictionary data, such as Jmdict, contains readings in fully-rendered but not per-character form. These are often a bit clunky to read on their own:

* <ruby>頑張る<rt>がんばる</rt></ruby>
* <ruby>阿吽の呼吸<rt>あうんのこきゅう</rt></ruby>


This is similar to [react-furi](https://github.com/DJTB/react-furi), but I wanted a version that could work in an Anki deck or in other plain JS environments without including React.

## Usage
* Include `furigana.bundle.js` into your webpage.


## Demo
頑張る[がんばる]<br>
<ruby>頑張<rt>がんば</rt>る<rt> </rt></ruby>

阿吽の呼吸[あうんのこきゅう]<br>
<ruby>阿吽<rt>あうん</rt>の<rt> </rt>呼吸<rt>こきゅう</rt></ruby>

冴え冴え[さえざえ]<br>
<ruby>冴<rt>さ</rt>え<rt> </rt>冴<rt>ざ</rt>え<rt> </rt></ruby>

権兵衛が種蒔きゃ烏がほじくる[ごんべえがたねまきゃからすがほじくる]<br>
<ruby>権兵衛<rt>ごんべえ</rt>が<rt> </rt>種蒔<rt>たねま</rt>きゃ<rt> </rt>烏<rt>からす</rt>がほじくる<rt> </rt></ruby>

蒔かぬ種は生えぬ[まかぬたねははえぬ]<br>
<ruby>蒔<rt>ま</rt>かぬ<rt> </rt>種<rt>たね</rt>は<rt> </rt>生<rt>は</rt>えぬ<rt> </rt></ruby>

秋の野芥子[あきののげし]<br>
<ruby>秋<rt>あき</rt>の<rt> </rt>野芥子<rt>のげし</rt></ruby>

巻き脚絆[まききゃはん]<br>
<ruby>巻<rt>ま</rt>き<rt> </rt>脚絆<rt>きゃはん</rt></ruby>

## How it works
We use a greedy algorithm to match each kana sequence to a set of candidate positions. If the candidate positions are at the start or tail of the string (as in 頑張る), we know for certainty that we can match them. If, after matching start and tail sequences, there is only one candidate in the middle of the string, we can definitely match it.

The only ambiguous cases are when there are at least two candidates in the middle of the string. Right now we are not able to solve these, and the tokenizer will just use the whole string in this case. This is solvable using levenshtein distance or public datasets and may be added in a future revision.

It's not particularly hard to do pinyin rendering; it's just bundled into the same library as a utility for multi-language environments.

## TODO
* Set up CDN
* Deal with ambiguities when there are two or more mid-string candidates