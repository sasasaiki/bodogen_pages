# bodogen_pages

ボードゲーム向け手番タイマー & リソース管理アプリ **ボドゲン（Bodogen）** の公開ページ用リポジトリです。
`sasasaiki/mttask_pages` をクローンして作成しました。

## 構成

| ブランチ | 役割 |
| --- | --- |
| `main` | 作業用。README のみ（公開されません） |
| `gh-pages` | **GitHub Pages の公開元**。サイトの実ファイルはこちら |

`gh-pages` ブランチの中身:

```
CNAME          bodogen-prapori.saiki.app
_config.yml    Jekyll 設定（テーマ: cayman）
index.md       トップページ
privacy.md     プライバシーポリシー（日本語）
privacy-en.md  Privacy Policy (English)
```

## 公開URL

| ページ | URL |
| --- | --- |
| トップ | https://bodogen-prapori.saiki.app/ |
| プライバシーポリシー（日本語） | https://bodogen-prapori.saiki.app/privacy |
| Privacy Policy (English) | https://bodogen-prapori.saiki.app/privacy-en |

> Google Play のストア登録にはプライバシーポリシーURLが必須です。日本語版のURLを登録してください。

## 公開手順

1. GitHub で空のリポジトリ `sasasaiki/bodogen_pages` を作成（README・.gitignore・LICENSE は追加しない）
2. push

   ```sh
   git push -u origin main
   git push -u origin gh-pages
   ```

3. リポジトリの **Settings → Pages** で
   - Source: `Deploy from a branch`
   - Branch: `gh-pages` / `/ (root)`
   - Custom domain: `bodogen-prapori.saiki.app`（CNAME ファイルがあるため自動入力されます）
   - `Enforce HTTPS` にチェック（証明書発行後に有効化できます）

4. DNS（`saiki.app` のゾーン）に CNAME レコードを追加

   | Type | Name | Value |
   | --- | --- | --- |
   | CNAME | `bodogen-prapori` | `sasasaiki.github.io` |

5. DNS 反映後、上記URLで表示を確認

## ポリシー本文を更新するとき

`gh-pages` ブランチの `privacy.md` / `privacy-en.md` を編集して push すれば、数分で反映されます。
