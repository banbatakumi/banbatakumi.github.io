# banbatakumi.github.io

馬場 拓海 / Takumi Bamba のポートフォリオサイト（GitHub Pages）。

- 単一ファイル `index.html` で完結（バニラ HTML / CSS / JS）
- 公開URL: https://banbatakumi.github.io/

## 公開方法

1. このリポジトリ名を `banbatakumi.github.io` にして GitHub へ push
2. GitHub の **Settings → Pages → Source** を `main` ブランチ / `/ (root)` に設定
3. 数分後 https://banbatakumi.github.io/ で公開される

## ページ構成

Hero（主な実績）→ About → **SURGE Mark.2（最新作・解説サイトへのリンク）** → Projects → Awards → Skills → Contact

- SURGE Mark.2 の技術解説サイト: https://banbatakumi.github.io/surge-mk2/ （リポジトリ `banbatakumi/surge-mk2`）。
  ナビの「SURGE 解説サイト」、Hero、SURGE Mark.2 セクション、フッターからリンクしている。

## 画像

ページが表示するのは `images/web/` の**軽量版**（長辺 960px、Mark.2 のみ 1280px、JPEG 品質 78）。
`images/` 直下の元画像（数 MB）は保管用で、ページからは読み込まない。

| 表示用ファイル | 元画像 | 内容 |
| --- | --- | --- |
| `images/web/surge_mk2.jpg` | `surge-mk2/docs/assets/img/car_blackback.jpg` | SURGE Mark.2 |
| `images/web/robotcar.jpg` | `images/robotcar.jpeg` | SURGE Mark.1 |
| `images/web/rcj_open.jpg` | `images/rcj_open.jpeg` | RoboCup Junior（オープン） |
| `images/web/ssl.jpg` | `images/ssl.jpeg` | Ri-one SSL ロボット |
| `images/web/bldc.jpg` | `images/bldc.jpeg` | BLDCホイールモジュール |
| `images/web/inverted_pendulum.jpg` | `images/inverted_pendulum.JPG` | 倒立振子ロボット |
| `images/web/linetrace.jpg` | `images/linetrace.jpeg` | ライントレースロボット |
| `images/web/robotrace.jpg` | `images/robotrace.jpeg` | ロボトレース |
| `images/web/disinfectant_stand.jpg` | `images/disinfectant_stand.jpeg` | 足踏み式消毒液スタンド |
| `images/og.jpg` | `surge-mk2/docs/assets/img/og.jpg` | URL を貼ったときのプレビュー画像（1200×630） |

> `images/rcj_lightweight.JPG`（RCJ軽量級ロボ）は現状サイト未使用。

写真を足すときは、元画像を `images/` に置き、次のように軽量版を作ってから `index.html` で `images/web/...` を参照する。
縦長の写真はカードの画像枠に `portrait` クラスを付けると、切り取らずに全体を表示する。

```bash
python3 -c "
from PIL import Image, ImageOps
im = ImageOps.exif_transpose(Image.open('images/NEW.jpeg')).convert('RGB')
im.thumbnail((960, 960)); im.save('images/web/NEW.jpg', quality=78, optimize=True, progressive=True)"
```
