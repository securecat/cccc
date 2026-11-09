# Accessibility

Last updated: 2026-11-09

## Priorities and Goals

CCCC (Casual Color Contrast Checker) is itself an accessibility tool. It checks whether a combination of text and background colors is easy to read, including for people with low vision or color vision deficiencies, using the WCAG 2.2 contrast ratio criteria. It aims to let people check colors with nothing but a browser, even in workplaces where they can't freely install software, including colors outside the browser, such as those in PowerPoint slides.

If the tool for checking contrast is itself hard to use, it gets in the way of people trying to make accessible materials. So we also care about the accessibility of CCCC's own UI.

This statement covers:

- The CCCC web page (https://securecat.github.io/cccc/)

The color dialog that opens when you click a color swatch, including its eyedropper, is not part of CCCC. It is the browser's own color dialog, so its accessibility is outside the scope of this statement. In Chrome and Edge, you can also type a color value in the dialog as RGB, HSL, or HEX with the keyboard, without using the eyedropper.

For the UI, we target WCAG 2.2 Level AA, and we treat it as a minimum, not a ceiling. Some of our own rules are stricter than AA (see [Contributor Expectations](#contributor-expectations)). We have not had a third-party evaluation, so this is a target, not a claim of conformance.

## How CCCC Judges Contrast

- The contrast ratio is calculated with the relative luminance formula in WCAG 2.2
- The ratio is shown with two decimal places, and further digits are truncated, not rounded. This prevents a color pair that falls just short of a criterion from looking as if it meets it
- CCCC checks three criteria: AA for text (4.5:1), AAA for text (7:1), and AA for non-text elements (3:1)
- Each result is shown not only by color but also by text: "✓ OK" or "✗ NG"
- The criteria for large text (3:1 for AA, 4.5:1 for AAA) are not shown as separate items

## Supported Environments

- Browser: tested on Google Chrome and Microsoft Edge on Windows. We have not yet tested other browsers, such as Firefox and Safari
- Operating systems: tested on Windows. We have not yet tested macOS, iOS, or Android
- Eyedropper: tested on Chrome and Edge on Windows, where it can pick colors outside the browser, such as in PowerPoint
- Screen readers: tested with NVDA on Windows. We have not yet tested other screen readers, including PC-Talker and VoiceOver
- All of CCCC's own controls are native buttons and color inputs, so they can be operated with a keyboard alone
- When you choose a color or swap the two colors, the colors, the contrast ratio, and the results are announced through a live region
- The page opens in the light or dark theme according to your browser's color scheme setting. You can also switch the theme with the button at the top right, but your choice is not saved

## Known Limitations

- **The text in the preview may not meet the contrast criteria.** The preview shows text in the colors you chose, so its contrast depends on those colors. This is by design.
- **The UI is available in Japanese only.**

## Reporting Accessibility Barriers

Please report barriers through [GitHub Issues](https://github.com/securecat/cccc/issues). You can write in English or Japanese.

The following details help us, but all of them are optional:

- What you were trying to do (for example, "I can't pick a color with the eyedropper")
- The screen or feature you were using
- What happened, and what you expected
- Your OS, browser version, and CCCC version
- Any assistive technology you use, such as a screen reader

You don't need to tell us about any disability. Screenshots and recordings are not required.

## Response Process

CCCC is developed by an individual, so we can't promise a deadline for replies or fixes. We will respond as quickly as we can.

- We will reply on the issue once we've seen your report
- If there is a workaround, we will share it
- Before releasing a fix, we may ask you to confirm that it works for you
- Fixes are recorded in [CHANGELOG.md](../CHANGELOG.md)

## Contributor Expectations

These expectations apply equally to human contributors and coding agents.

When you change the UI:

- Use native form controls (`<input>`, `<select>`, `<textarea>`). Don't use `<div>` or `<span>` as buttons; use `<button>` for actions on the page and `<a>` for navigation
- Don't use the `disabled` attribute
- Don't remove focus indicators (no `outline: none`)
- Don't remove link underlines
- Keep text contrast at 7:1 or higher for body text and 4.5:1 or higher for secondary text, in both light and dark themes
- Keep non-text elements, such as borders and icons, at 3:1 or higher against adjacent colors
- Don't apply `opacity` to elements that need contrast
- Use a minimum font size of 16px for Japanese and 14px for English
- Use `font-family: sans-serif` (don't use `system-ui`)
- Don't dismiss status messages automatically
- Don't add anything that moves on its own, such as auto-scrolling

After the change, check that everything can be operated with a keyboard alone, and that a screen reader such as NVDA reads the content correctly.

When you change how the contrast ratio is calculated or judged, follow the formula in WCAG 2.2, and don't round the displayed ratio up or to the nearest value, so that a color pair falling just short of a criterion is never shown as "OK". Don't show the results by color alone; keep text such as "✓ OK" and "✗ NG". The results are announced through a live region (`#announce`), so when you change what the results show, update the announced text as well. The comment at the top of the CSS in `index.html` lists the contrast ratios we checked for the color palette, so update it when you change the colors.

## Ownership and Maintenance

This statement is maintained by the maintainer, securecat. We update it when we add features or when the tested environments change.

## Feedback on This Statement

Suggestions about this statement or our approach to accessibility are also welcome through [GitHub Issues](https://github.com/securecat/cccc/issues).

---

# アクセシビリティ

最終更新：2026-11-09

## 優先事項と目標

CCCC（カジュアルカラーコントラストチェッカー）は、それ自体がアクセシビリティのための道具です。文字と背景の色の組み合わせが、弱視の人や色覚に特性のある人も含めて読みやすいかどうかを、WCAG 2.2 のコントラスト比の基準で確かめられます。ソフトウェアを自由にインストールできない職場などでも、ブラウザだけで、PowerPoint の資料のようなブラウザの外の色も含めて確かめられることを目指しています。

コントラストを確かめる道具そのものが使いにくければ、アクセシブルな資料をつくろうとする人の妨げになります。そのため、CCCC 自身のUIのアクセシビリティも大事にしています。

この文書が対象とするのは、次のとおりです。

- CCCC のウェブページ（https://securecat.github.io/cccc/）

色見本をクリックすると開く色選択ダイアログ（スポイトを含む）は、CCCC の一部ではなく、ブラウザ標準の機能です。そのため、ダイアログの中のアクセシビリティは、この文書の対象外です。なお、Chrome、Edge の色選択ダイアログでは、スポイトを使わずに、色の値を RGB、HSL、HEX でキーボードから入力することもできます。

UIは WCAG 2.2 のレベル AA を目標とし、これを上限ではなく下限と考えています。AAより厳しい独自の基準もあります（[貢献者への期待](#貢献者への期待)を参照）。第三者による試験は受けていないため、これは目標であり、適合を表明するものではありません。

## コントラスト比の判定のしかた

- コントラスト比は、WCAG 2.2 の相対輝度の計算式で求めています
- コントラスト比は小数第2位まで表示し、それより下の桁は四捨五入せずに切り捨てています。基準にわずかに届かない色の組み合わせが、基準を満たしているように見えないようにするためです
- 判定する基準は、AA テキスト（4.5:1）、AAA テキスト（7:1）、AA 非テキスト（3:1）の3つです
- 判定結果は、色だけでなく「✓ OK」「✗ NG」の文字でも示しています
- 大きいテキスト向けの基準（AA 3:1、AAA 4.5:1）は、個別の項目としては表示していません

## 対応している環境

- ブラウザ：Windows の Google Chrome、Microsoft Edge で動作を確認済み。Firefox、Safari など、ほかのブラウザではまだ試していません
- OS：Windows で動作を確認済み。macOS、iOS、Android ではまだ試していません
- スポイト：Windows の Chrome、Edge で、ブラウザの外（PowerPoint など）の色を拾えることを確認済み
- スクリーンリーダー：Windows の NVDA で読み上げを確認済み。PC-Talker、VoiceOver など、ほかのスクリーンリーダーではまだ試していません
- CCCC 自身の操作部品は、すべてネイティブのボタンと色の選択欄なので、キーボードだけで操作できます
- 色を選んだときと、2色を入れ替えたときは、2つの色・コントラスト比・判定結果をライブリージョンで読み上げます
- ページは、ブラウザのカラースキームの設定に合わせて、ライトテーマかダークテーマで開きます。右上のボタンで切り替えることもできますが、切り替えたテーマは保存されません

## 既知の制限

- **プレビューの文字は、コントラストの基準を満たさないことがあります。** プレビューは選んだ色そのもので表示するため、コントラストは選んだ色によって決まります。これは意図したものです。
- **UIは日本語のみです。**

## アクセシビリティの問題を報告する

問題は [GitHub Issues](https://github.com/securecat/cccc/issues) で報告してください。日本語でも英語でも構いません。

次のことを書いてもらえると助かりますが、どれも任意です。

- 何をしようとしていたか（例：「スポイトで色を拾えない」）
- 使っていた画面や機能
- 何が起きたか、どうなると思っていたか
- OS、ブラウザのバージョン、CCCC のバージョン
- 使っている支援技術（スクリーンリーダーなど）

障害の有無や内容を書く必要はありません。スクリーンショットや録画も必須ではありません。

## 対応の流れ

CCCC は個人で開発しているため、返信や修正の期限はお約束できません。それでも、できるかぎり早く対応します。

- 報告を確認したら、Issue で返信します
- 回避策があれば、お知らせします
- 修正をリリースする前に、問題が解消したかどうかの確認をお願いすることがあります
- 修正の内容は [CHANGELOG.md](../CHANGELOG.md) に記載します

## 貢献者への期待

ここに挙げることは、人間の貢献者にもコーディングエージェントにも、同じように求めます。

UIを変更するときは、次を守ってください。

- フォームにはネイティブの要素（`<input>`・`<select>`・`<textarea>`）を使う。`<div>` や `<span>` をボタンの代わりにしない。画面内の操作には `<button>`、ページの移動には `<a>` を使う
- `disabled` 属性を使わない
- フォーカスインジケーターを消さない（`outline: none` を使わない）
- リンクの下線を消さない
- テキストのコントラスト比は、本文で 7:1 以上、補足的なテキストで 4.5:1 以上にする。ライトテーマとダークテーマのそれぞれで満たす
- 境界線やアイコンなど、テキスト以外の要素も、隣り合う色に対して 3:1 以上にする
- コントラストが必要な要素に `opacity` を使わない
- 文字サイズは、日本語で 16px 以上、英語で 14px 以上にする
- `font-family` は `sans-serif` にする（`system-ui` は使わない）
- ステータスメッセージを自動で消さない
- 自動スクロールなど、ひとりでに動くものを作らない

変更したあとは、キーボードだけですべて操作できること、NVDA などのスクリーンリーダーで内容が正しく読み上げられることを確認してください。

コントラスト比の計算や判定を変更するときは、WCAG 2.2 の計算式に従い、表示するコントラスト比を切り上げたり四捨五入したりしないでください。基準にわずかに届かない色の組み合わせを「OK」と表示しないためです。また、判定結果を色だけで示さず、「✓ OK」「✗ NG」のような文字を残してください。判定結果はライブリージョン（`#announce`）でも読み上げているので、表示する判定の内容を変えるときは、読み上げる文も合わせて更新してください。`index.html` の CSS の冒頭のコメントに、カラーパレットで確認したコントラスト比を書いているので、色を変えたら更新してください。

## 責任者と保守

この文書は、メンテナーの securecat が管理しています。機能を追加したときや、動作を確認した環境が変わったときに更新します。

## この文書へのフィードバック

この文書やアクセシビリティへの取り組み方についての提案も、[GitHub Issues](https://github.com/securecat/cccc/issues) で受け付けています。
