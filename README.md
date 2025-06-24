# follyanna
automatic pinyin and furigana ruby tags in js

## Overview
`follyanna` uses intelligent furigana placement to strip redundant kana from furigana readings.

For instance: 頑張る[がんばる] -> <ruby>頑張<rt>がんば</rt>る</ruby>


## Usage
* Include `furigana.bundle.js` into your webpage.
```
console.log(generateFurigana('頑張る', 'がんばる'));
console.log(generateFurigana('阿吽の呼吸', 'あうんのこきゅう'));
console.log(generateFurigana('冴え冴え', 'さえざえ'));
console.log(generateFurigana('権兵衛が種蒔きゃ烏がほじくる', 'ごんべえがたねまきゃからすがほじくる'));
console.log(generateFurigana('蒔かぬ種は生えぬ', 'まかぬたねははえぬ'));
console.log(generateFurigana('秋の野芥子', 'あきののげし'));
console.log(generateFurigana('巻き脚絆', 'まききゃはん'));
console.log(generateFurigana('瞋恚の炎', 'しんいのほのお'));
console.log(generateFurigana('ザ・ソプラノズ哀愁のマフィア', 'ザソプラノズひげきのマフィア'));
console.log(generateFurigana('ハレー彗星', 'ハレーすいせい'));
console.log(generateFurigana('四方反鉋', 'しほうそりかんな'));
console.log(generateFurigana('鱧も一期、海老も一期', 'はももいちご、えびもいちご'));
console.log(generateFurigana('八ヶ岳美術館', 'やつがたけびじゅつかん'));
console.log(generateFurigana('ナルホド駅', 'なるほどえき'));

// output:
頑張[がんば]る[ ]
阿吽[あうん]の[ ]呼吸[こきゅう]
冴[さ]え[ ]冴[ざ]え[ ]
権兵衛[ごんべえ]が[ ]種蒔[たねま]きゃ[ ]烏[からす]がほじくる[ ]
蒔[ま]かぬ[ ]種[たね]は[ ]生[は]えぬ[ ]
秋[あき]の[ ]野芥子[のげし]
巻[ま]き[ ]脚絆[きゃはん]
瞋恚の炎[しんいのほのお]
ザ[ ]・ソプラノズ[ ]哀愁[ひげき]のマフィア[ ]
ハレー[ ]彗星[すいせい]
四方反鉋[しほうそりかんな]
鱧も一期[はももいちご]、海老[えび]も[ ]一期[いちご]
八ヶ岳美術館[やつがたけびじゅつかん]
ナルホド[ ]駅[えき]
```

## TODO
* Set up CDN