# GitHub Pages 移行メモ

## 公開
Repository Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: main / (root) → Save。
初回公開後 https://itomoki430.github.io/ を確認する。

## 編集
- index.html: 英語トップ
- publications.html: 業績・助成・受賞
- japanese.html: 日本語紹介
- news-*.html: 過去ニュース
- assets/style.css: デザイン
- _layouts/default.html: 共通レイアウト
各ページ先頭の `---` で囲まれた設定を残して、本文のHTMLを編集する。GitHub上で編集・コミットすると再公開される。

## 移行内容
2026-11-03時点の公開サイトの本文・業績・日本語ページ・ニュース4件を移行。画像2件は assets/ 内にコピー。外部メディアと動画はリンクとして保持。元サイトの本文にある連絡先や年月の表記は維持している。
固定ページ2件とニュース4件は既存URLのパスを維持（GitHub Pagesにより末尾 / へ転送）。旧サービス固有のフォロー・検索・シェア機能は移行対象外。

## 独自ドメイン（動作確認後）
1. ドメインの管理会社と現在のDNSを確認する。
2. GitHubアカウント設定でドメインを検証する。
3. Repository Settings → Pages → Custom domain に www.tomokiito.net を登録。
4. DNSの www CNAMEを itomoki430.github.io に変更する。メール用MX・TXT等は保持。
5. ルート tomokiito.net の設定は現在のDNSとGitHub公式の最新値を確認して行う。
6. GitHub側の証明書発行後、Enforce HTTPSを有効にする。
7. _config.yml の url を https://www.tomokiito.net に更新する。
8. トップ、日本語、業績、過去記事、画像を確認する。

この移行ではまだCNAMEファイルも独自ドメイン設定も追加していない。
