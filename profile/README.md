# ShiftAntigravity ドキュメント

{: align="center"}
![icon](./img/icon.png)

このディレクトリには、シフト管理システム「ShiftAntigravity」の各種マニュアルが格納されています。

## マニュアル一覧

利用者の役割に応じて、以下のマニュアルを参照してください。

| 対象者 | ドキュメント | 内容 |
| :--- | :--- | :--- |
| **室長・管理者** | [室長用マニュアル](https://github.com/Shift-Antigravity/.github/blob/main/Admin_Manual/Admin_Manual.md) | シフトの発行、集計、塾マネへの反映方法など |
| **講師** | [講師用マニュアル](https://github.com/Shift-Antigravity/.github/blob/main/Tutor_Manual/Tutor_Manual.md) | アカウント作成、シフトの提出方法など |

## システム概要

ShiftAntigravityは、塾のシフト集計を効率化し、既存の管理システム（塾マネ）への入力を自動化するためのツールです。

## 設計・開発経緯

シフトの提出では毎回EXCELを作り共有、集めたデータを元に塾マネへ１つ１つ手作業で反映していました。しかし時間が取られる上で、人為的ミスも発生しやすい現状です。一回全ての作業をSeleniumで自動化も行いましたが非常に不安定な動作で継続的な運用は難しい状態でした。そのため今回のアプリケーションを作成しました。

### 設計

主な着眼点は2つです。

- シフトの集計を自動化
- 入力も自動化

特に今回はSeleniumではなくGoogle Chrome 拡張機能を用いることで効率的にかつ安定、継続的な運用が可能になっています。また提出状況を確認しながら入力が行えることが利点です。
そしてシステム移行に伴う作業も最小限になるようになっています。講師各々にアカウント登録及びレギュラー登録を行えるようにすることで管理職の負担を軽減しています。また新規講師が増えても各々に登録させることで負担の軽減を狙います。

## 開発状態

安定した動作が期待されるまで可能な限り開発は続ける予定です。また機能のリクエスト等が合ったら開発します。

## ディレクトリ構造

```
.
└── Shift-Antigravity/
    ├── develop-library/ ... 開発用ライブラリ/
    │   ├── start_terminals.bat ... バックエンドのターミナル起動用batファイル
    │   └── README.md
    ├── juku-fake-system/ ... 偽の塾マネ/
    │   ├── static/
    │   │   ├── .css
    │   │   └── .js
    │   ├── templates/
    │   │   └── .html
    │   ├── requirements.txt
    │   └── test.py ... FastAPI起動用
    ├── shift-management-extension/ ... 拡張機能/
    │   ├── background.js
    │   ├── content.js
    │   ├── manifest.json
    │   ├── README.md
    │   ├── sidepanel.css
    │   ├── sidepanel.html
    │   └── sidepanel.js
    └── shift-management-web/ ... webアプリケーション/
        ├── backend/
        │   ├── api/
        │   │   └── Django App file
        │   ├── config/
        │   │   └── Django setting file
        │   ├── .env
        │   ├── db.sqlite3
        │   └── manage.py
        ├── frontend/
        │   ├── src/
        │   │   ├── api/
        │   │   │   └── client.js
        │   │   ├── pages/
        │   │   │   └── react.jsx
        │   │   ├── App.jsx
        │   │   ├── index.css
        │   │   └── main.jsx
        │   ├── index.html
        │   ├── package-lock.json
        │   ├── package.json
        │   ├── tailwind.config.js
        │   └── vite.config.js
        ├── package-lock.json
        ├── package.json
        ├── README.md
        └── requirements.txt
```

## 開発リポジトリ

- [chrome用拡張機能](https://github.com/Shift-Antigravity/shift-management-extension)
- [ウェブアプリケーション](https://github.com/Shift-Antigravity/Shift-management-web)
- [開発用ライブラリ](https://github.com/Shift-Antigravity/develop-library)

## CONTACT

- [My Discord Server](https://discord.gg/v9ybtUdQhA)
