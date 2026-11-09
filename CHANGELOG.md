# Changelog

All notable changes to this project will be documented in this file.
The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [1.1.0] - 2026-11-09

### Added

- Open in the light or dark theme according to the browser's color scheme setting, and follow changes to the setting (the theme you choose with the button is not saved)
- Announce the two colors, the contrast ratio, and the results to screen readers when you choose a color or swap the colors
- Add a main landmark and headings for each part of the page
- Show a prominent focus indicator, offset from each control
- Invert the colors of the copy and swap buttons while they are pressed

### Changed

- Remove the backgrounds of the WCAG result items and the message, and raise the contrast of their text and borders to 7:1 or higher
- Remove the border around the result message
- Thicken the borders of the color swatches and buttons on hover, instead of scaling them up or changing their colors
- Remove all animations and transitions, including the pop-in on load, the rotation of the swap button, and the fade when switching themes
- Use the `sans-serif` font instead of the Zen Maru Gothic web font
- Change the theme button label to "ダークに変更" (switch to dark) or "ライトに変更" (switch to light)
- Show the whole title in the text color
- Make the color swatches shorter
- Remove the lead text under the title

### Removed

- Remove the "copied" message shown after copying a HEX value

### Fixed

- Fix the focus indicator not being visible on the color inputs
- Fix the accessible names of the theme and swap buttons not matching their visible labels

## [1.0.2] - 2026-10-05

### Changed

- Write the `meta charset` value in lowercase (`utf-8`) as recommended by the HTML Standard

## [1.0.1] - 2026-03-05

### Added

- Version comment in HTML

## [1.0.0] - 2026-03-04

### Added

- Initial release

---

# 更新履歴

## [1.1.0] - 2026-11-09

### 追加

- ブラウザのカラースキームの設定に合わせて、ライトテーマかダークテーマで開くようにし、設定の変更にも追従するようにした（ボタンで切り替えたテーマは保存しない）
- 色を選んだときと、2色を入れ替えたときに、2つの色・コントラスト比・判定結果をスクリーンリーダーで読み上げるようにした
- ページに main ランドマークと、各部分の見出しを追加
- 操作部品から少し離れた位置に、目立つフォーカスインジケーターを表示するようにした
- コピーボタンと入れ替えボタンを押している間、色を反転させるようにした

### 変更

- WCAG の判定項目とメッセージの背景色をなくし、文字と枠のコントラスト比を 7:1 以上に引き上げ
- 判定結果のメッセージの枠を削除
- 色見本とボタンの hover の表現を、拡大や色の変化から、枠を太くする表現に変更
- 読み込み時のポップイン、入れ替えボタンの回転、テーマ切り替え時のフェードなど、アニメーションとトランジションをすべて削除
- フォントを Webフォントの Zen Maru Gothic から `sans-serif` に変更
- テーマボタンのラベルを「ダークに変更」「ライトに変更」に変更
- タイトル全体を文字色で表示するように変更
- 色見本の高さを縮小
- タイトルの下のリード文を削除

### 削除

- HEX値をコピーしたときの「コピーしました」というメッセージを削除

### 修正

- 色の選択欄でフォーカスインジケーターが見えなかった問題を修正
- テーマボタンと入れ替えボタンの、スクリーンリーダーが読み上げる名前が、見た目のラベルと一致していなかった問題を修正

## [1.0.2] - 2026-10-05

### 変更

- HTML Standard の推奨に合わせ、`meta charset` の値を小文字（`utf-8`）に変更

## [1.0.1] - 2026-03-05

### 追加

- HTMLにバージョンコメントを追加

## [1.0.0] - 2026-03-04

### 追加

- 初回リリース
