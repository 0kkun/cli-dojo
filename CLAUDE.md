# cli-dojo

Vim操作とShell操作の練習ができるローカルWebアプリ。

## コマンド

```bash
npm run dev      # 開発サーバー起動 (http://localhost:3000)
npm run build    # プロダクションビルド
npm run lint     # ESLint実行
npm run test     # テスト実行
```

## 技術スタック

- Next.js 15 (App Router)
- TypeScript 5
- CodeMirror 6 + @replit/codemirror-vim
- Tailwind CSS 4
- Volta (Node/npm バージョン管理)

## アーキテクチャ

```
src/
├── app/                    # Next.js App Router
│   ├── page.tsx            # トップページ（モード選択）
│   ├── vim/
│   │   ├── page.tsx        # Vimカテゴリ選択
│   │   └── [categoryId]/
│   │       └── page.tsx    # Vim問題画面
│   ├── shell/
│   │   ├── page.tsx        # Shellカテゴリ選択
│   │   └── [categoryId]/
│   │       └── page.tsx    # Shell問題画面
│   └── progress/
│       └── page.tsx        # 進捗確認
├── components/
│   ├── vim-editor.tsx      # CodeMirror + Vimバインド
│   ├── shell-terminal.tsx  # コマンド入力・実行結果表示
│   ├── problem-card.tsx    # 問題文・判定結果の共通UI
│   └── progress-chart.tsx  # 達成率グラフ
├── lib/
│   ├── judge/
│   │   ├── vim-judge.ts    # Vim正誤判定（テキスト一致）
│   │   └── shell-judge.ts  # Shell正誤判定（出力比較）
│   ├── executor/
│   │   └── shell-exec.ts   # child_process.execラッパー
│   └── progress/
│       └── storage.ts      # localStorage操作
├── data/
│   ├── vim/                # Vim問題定義JSON
│   └── shell/              # Shell問題定義JSON
└── types/
    └── index.ts            # 共通型定義
```

## ディレクトリ方針

- `app/` — ルーティングとページコンポーネントのみ。ロジックを持たない
- `components/` — 再利用可能なUIコンポーネント
- `lib/` — ビジネスロジック。UIに依存しない
- `data/` — 問題定義の静的JSON
- `types/` — プロジェクト共通の型定義
# cli-dojo

Vim操作とShell操作の練習ができるローカルWebアプリ。

## コマンド

```bash
npm run dev      # 開発サーバー起動 (http://localhost:3000)
npm run build    # プロダクションビルド
npm run lint     # ESLint実行
npm run test     # テスト実行
```

## 技術スタック

- Next.js 15 (App Router)
- TypeScript 5
- CodeMirror 6 + @replit/codemirror-vim
- Tailwind CSS 4
- Volta (Node/npm バージョン管理)

## アーキテクチャ

```
src/
├── app/                    # Next.js App Router
│   ├── page.tsx            # トップページ（モード選択）
│   ├── vim/
│   │   ├── page.tsx        # Vimカテゴリ選択
│   │   └── [categoryId]/
│   │       └── page.tsx    # Vim問題画面
│   ├── shell/
│   │   ├── page.tsx        # Shellカテゴリ選択
│   │   └── [categoryId]/
│   │       └── page.tsx    # Shell問題画面
│   └── progress/
│       └── page.tsx        # 進捗確認
├── components/
│   ├── vim-editor.tsx      # CodeMirror + Vimバインド
│   ├── shell-terminal.tsx  # コマンド入力・実行結果表示
│   ├── problem-card.tsx    # 問題文・判定結果の共通UI
│   └── progress-chart.tsx  # 達成率グラフ
├── lib/
│   ├── judge/
│   │   ├── vim-judge.ts    # Vim正誤判定（テキスト一致）
│   │   └── shell-judge.ts  # Shell正誤判定（出力比較）
│   ├── executor/
│   │   └── shell-exec.ts   # child_process.execラッパー
│   └── progress/
│       └── storage.ts      # localStorage操作
├── data/
│   ├── vim/                # Vim問題定義JSON
│   └── shell/              # Shell問題定義JSON
└── types/
    └── index.ts            # 共通型定義
```

## ディレクトリ方針

- `app/` — ルーティングとページコンポーネントのみ。ロジックを持たない
- `components/` — 再利用可能なUIコンポーネント
- `lib/` — ビジネスロジック。UIに依存しない
- `data/` — 問題定義の静的JSON
- `types/` — プロジェクト共通の型定義