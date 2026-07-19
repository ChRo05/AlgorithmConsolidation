# アルゴリズム教材プロジェクト — 引き継ぎ＆TODOメモ

最終更新：2026-07-19 / 状態：トピック1〜3をGitHubに公開済み

---

## いまの状況（DONE）

- 連携チェック完了：Google Drive＝読み書き可／GitHub＝clone・push可（トークン必要）／Colab＝ファイル編集可・実行はユーザー。
- リポジトリを public 化。README だけの空状態から、INDEX.md ＋ トピック1〜3（各 body / exercises / answers）＝計10ファイルを作成しpush済み。
- 最新コミット：8cb7443 Add INDEX and topics 1-3（作者メールは匿名の noreply）。
- トレース解答・デバッグ挙動は実コードで検算済み。

GitHubで確認：https://github.com/ChRo05/AlgorithmConsolidation

---

## 確立した運用フロー（Colabで完結、pushだけ自分）

1. Colabで対象ノートブックを開く。
2. リポジトリを clone（git clone … && cd AlgorithmConsolidation）。
3. Git設定：user.name = ChRo05 ／ user.email = 82155159+ChRo05@users.noreply.github.com（← このnoreplyメール必須。gmailだと push が保護で弾かれる）。
4. 各ファイルを生成するセルを実行（open(path,"w",encoding="utf-8").write(...)）。
5. git add -A → git commit -m "Add topic N"。
6. push セル（getpassでトークン入力）で HEAD:main に push。
7. 使ったトークンは毎回 revoke。

---

## 重要情報・設定値

- リポジトリ：ChRo05/AlgorithmConsolidation（public）。
- noreplyメール：82155159+ChRo05@users.noreply.github.com
- コミット作者名：ChRo05
- トークン作成（fine-grained・推奨）：https://github.com/settings/personal-access-tokens/new
  - Repository access ＝ Only select repositories → AlgorithmConsolidation
  - Permissions → Contents ＝ Read and write
- トークン失効（後始末）：https://github.com/settings/tokens

---

## 明日以降のTODO

- [ ] トピック4「2次元配列」を作成（フォルダ topic04_matrix、body/exercises/answers）。
- [ ] 以降を順に：5 スタックとキュー ／ 6 ポインタとリスト ／ 7 探索 ／ 8 整列 ／ 9 再帰 ／ 10 木構造 ／ 11 グラフ。
- [ ] 各トピック追加のたびに INDEX.md の該当行を「（未作成）」から実リンクへ更新。
- [ ] トピックごとに commit（メッセージは Add topic N）→ push。
- [ ] （任意）Colabノートブックの「生成→commit→push」を定番ノートブックとして保存し使い回す。

---

## 各トピックの作り方（雛形）

構成：① 理論（一言＋なぜ必要＋O記法＋「30秒で説明」）／② 3言語コード比較（全商DNCL・FE科目B・Python）＋説明チェック／③ トレース演習（基本・境界値の2問）／④ デバッグ演習（2問）／⑤ 指導への還元（躓き・キラーフレーズ・図解指示・AP発展）／⑥ 説明ドリル。

ナビ行：> 🧭 [📘本体](./body.md)｜[✏️演習](./exercises.md)｜[✅解答](./answers.md)｜[🏠目次](../INDEX.md)

方針：分量は「離脱しない程度」。たとえ話は1〜2個。過去問のベタ貼りはせず傾向を汲んだ類題。

---

## 今回ハマった点メモ（次回の回避策）

- Colabへの大きなコピペは途中で切れる（SyntaxError: incomplete input）。→ 1ファイル＝1セルで小さく貼る。エラーのセルだけ貼り直す。
- push がメール保護で拒否（GH007）。→ コミットのメールを noreply に（git config user.email → git commit --amend --reset-author → push）。
- 作業途中でランタイムを再起動しない（/content が消える）。push まで再起動・切断を避ける。
- Google Drive内に .git を置くと同期で稀に壊れる。不安定ならDrive外にcloneして作業。
- アカウントが2つ（Cowork/Drive＝snafty、Colab/GitHub＝個人gmail・ChRo05）。混同に注意。

（再開時：このメモの「確立した運用フロー」に沿って、TODOのトピック4から進める）
