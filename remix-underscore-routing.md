# Remix ルーティングにおけるアンダースコアの使い分け

Remix(v2)のファイルベースルーティングでは、アンダースコア（_）の位置によって異なる意味を持ちます。

## 1. 先頭アンダースコア（_leading）

**用途**: パスレスルート（Pathless Routes）を作成する

- URLパスには影響を与えずに、レイアウトをグループ化したい場合に使用
- 認証ルートなど、共通のレイアウトを持つが独自のURLセグメントを持たないルートグループに最適

### 例

```
app/routes/
├── _auth.tsx           # レイアウトルート（URLには現れない）
├── _auth.login.tsx     # /login
└── _auth.register.tsx  # /register
```

- `/login` → `_auth.tsx`のレイアウト内に`_auth.login.tsx`をレンダリング
- `/register` → `_auth.tsx`のレイアウト内に`_auth.register.tsx`をレンダリング

## 2. 末尾アンダースコア（trailing_）

**用途**: レイアウトのネストを回避する

- URLは階層的にしたいが、親のレイアウトは継承したくない場合に使用
- 親ルートのOutletコンポーネントにはレンダリングされない

### 例

```
app/routes/
├── concerts.tsx          # /concerts のレイアウト
├── concerts.trending.tsx # /concerts/trending（concerts.tsxのレイアウトを使用）
└── concerts_.mine.tsx    # /concerts/mine（concerts.tsxのレイアウトを使用しない）
```

- `/concerts/trending` → `concerts.tsx`のレイアウト内にレンダリング
- `/concerts/mine` → `root.tsx`に直接レンダリング（concerts.tsxをスキップ）

## 3. インデックスルート（_index）

**用途**: 親ルートのインデックスページを定義する

- 親ルートのURLに直接アクセスした時に表示されるコンテンツ
- 親ルートのOutlet内にレンダリングされる

### 例

```
app/routes/
├── _index.tsx           # / （ルートインデックス）
├── concerts.tsx         # /concerts のレイアウト
└── concerts._index.tsx  # /concerts のインデックスページ
```

## 使い分けのまとめ

| 記法 | 目的 | URL への影響 | レイアウトへの影響 |
|------|------|-------------|------------------|
| `_auth.login.tsx` | レイアウトをグループ化 | パスセグメントを作らない | 親レイアウトを作成/使用 |
| `concerts_.mine.tsx` | レイアウトネストを回避 | パスセグメントを作る | 親レイアウトをスキップ |
| `concerts._index.tsx` | インデックスページ | 親と同じURL | 親レイアウト内にレンダリング |

## 実際のプロジェクトでの使用例

あるプロジェクトでは以下のような使い分けをしています：

- `_app.*.tsx`: 認証後のアプリケーションルート（共通レイアウト）
- `_auth.*.tsx`: 認証関連のルート（別レイアウト）
- `_app.products._index`: 商品一覧のインデックスページ
- `_app.products.import_.confirm`: importのレイアウトをスキップしてconfirmページを表示

この命名規則により、URLの構造とレイアウトの階層を柔軟に制御できます。
