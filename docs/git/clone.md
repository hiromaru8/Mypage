## `git clone --mirror` と `git clone` の違い

結論から言うと：

> **`--mirror` は「リポジトリそのものを完全に複製する管理用クローン」**
> **通常の `git clone` は「作業するためのクローン」**

目的がまったく違います。

---

## ① 通常の `git clone`

```bash
git clone https://example.com/repo.git
```

### 何が作られる？

* 作業ツリー（ファイルが展開される）
* `.git/` ディレクトリ
* デフォルトブランチのみ checkout
* `origin` は **fetch 用**

### 特徴

* 普段の開発用
* `git add / commit / pull` が前提
* push は **自分のブランチだけ**

### 内部構造（イメージ）

```
repo/
 ├─ src/
 ├─ README.md
 └─ .git/
```

---

## ② `git clone --mirror`

```bash
git clone --mirror https://example.com/repo.git
```

### 何が作られる？

* **作業ツリーなし**
* `.git` 相当のみ（bare）
* **全ブランチ・全タグ・全 refs**
* `origin` は **fetch + push 両方**

### 特徴

* 管理・履歴書き換え・バックアップ用
* 開発作業は不可
* リモートと 1:1 同期される

### 内部構造

```
repo.git/
 ├─ HEAD
 ├─ config
 ├─ objects/
 ├─ refs/
 └─ packed-refs
```

---

## ③ `--bare` との違い

```bash
git clone --bare https://example.com/repo.git
```

| 項目        | --bare   | --mirror         |
| --------- | -------- | ---------------- |
| 作業ツリー     | なし       | なし               |
| refs      | 通常       | **すべて**          |
| remote 設定 | fetch のみ | **fetch + push** |
| 用途        | サーバ用     | **完全複製・履歴操作**    |

`--mirror` = **`--bare` + refs/remote 完全同期**

---

## ④ なぜ履歴削除で `--mirror` が推奨されるのか

### 履歴書き換え対象

* 全ブランチ
* 全タグ
* hidden refs（`refs/original/*` など）

→ 通常 clone では **一部が残る可能性**

`--mirror` なら：

* **消し漏れゼロ**
* 強制 push 1 回で完全反映

---

## ⑤ よくある事故パターン

❌ 通常 clone で filter-repo
→ 別ブランチやタグにバイナリが残る

❌ bare で push
→ refs が不完全

✅ mirror + filter-repo
→ リモートから完全消去

---

## ⑥ 使い分けまとめ

| 目的        | コマンド                 |
| --------- | -------------------- |
| 普段の開発     | `git clone`          |
| 履歴改変・事故対応 | `git clone --mirror` |
| Git サーバ用  | `git clone --bare`   |
| バックアップ    | `git clone --mirror` |

---

### 一言で言うと

> **`--mirror` は「Git の中身を丸ごとコピーする」**
> **`git clone` は「作業するためのコピー」**

履歴削除・容量事故対応の文脈では
**`git clone --mirror` 一択**です。
