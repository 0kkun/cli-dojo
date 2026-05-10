---
description: 問題データの定義方針
paths:
  - "src/data/**/*.json"
---

# 問題データ設計

## 形式

問題はJSONファイルで静的に定義する。カテゴリごとに1ファイル。

## Vim問題の構造

```json
{
  "categoryId": "motion",
  "categoryName": "カーソル移動",
  "problems": [
    {
      "id": "motion-001",
      "title": "行末に移動",
      "description": "カーソルを行末に移動せよ",
      "difficulty": "beginner",
      "initialText": "hello world",
      "initialCursor": { "line": 0, "ch": 0 },
      "goalText": "hello world",
      "goalCursor": { "line": 0, "ch": 10 }
    }
  ]
}
```

## Shell問題の構造

```json
{
  "categoryId": "file-ops",
  "categoryName": "ファイル操作",
  "problems": [
    {
      "id": "file-ops-001",
      "title": "ファイル一覧表示",
      "description": "/tmp/dojo以下のファイルを一覧表示せよ",
      "difficulty": "beginner",
      "setupCommands": ["mkdir -p /tmp/dojo", "touch /tmp/dojo/{a,b,c}.txt"],
      "expectedOutput": "a.txt\nb.txt\nc.txt\n",
      "expectedExitCode": 0,
      "hints": ["lsコマンドを使う"]
    }
  ]
}
```

## 難易度

- `beginner`: 基本操作1つで解ける
- `intermediate`: 複数操作の組み合わせ
- `advanced`: 効率的な操作を求める（ストローク数制限など）
