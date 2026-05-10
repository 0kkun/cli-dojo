---
description: コーディング規約・スタイルガイド
paths:
  - "src/**/*.{ts,tsx}"
---

# コーディング規約

## TypeScript

- strictモードを有効にする
- anyの使用を禁止する。unknownを使い、型ガードで絞り込む
- 型定義は `types/` に集約する。コンポーネント固有のPropsは同ファイル内で定義可
- enumは使わない。union型またはas constオブジェクトを使う
- 非null アサーション (!) は使わない

## React / Next.js

- Server Componentをデフォルトとし、インタラクションが必要な場合のみ "use client" を付ける
- コンポーネントはnamed exportで公開する（default exportはpage.tsxのみ）
- propsの型名は `{ComponentName}Props` とする
- useEffectは最小限にする。データ取得はServer Componentで行う

## 命名規則

- ファイル名: kebab-case (`vim-editor.tsx`)
- コンポーネント: PascalCase (`VimEditor`)
- 関数・変数: camelCase
- 型・interface: PascalCase
- 定数: UPPER_SNAKE_CASE

## インポート

- パスエイリアス `@/` を使用する（`src/` を指す）
- インポート順: 1) external 2) @/ internal 3) relative
