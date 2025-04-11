# Nature Remo - Home Assistant カスタム統合

Nature RemoをHome Assistantに連携するためのカスタムインテグレーションです。
エアコンや照明の操作、温度・湿度などの情報をHome Assistant上でまとめて扱えるようになります。

---

## ⚠️ ご注意
このカスタムインテグレーションは、Nature社およびHome Assistantの**非公式**な統合です。
利用にあたっては、**自己責任で**ご使用いただきますようお願いいたします。

---

## 主な機能

- Nature Remoに登録された家電（エアコン・照明）の操作
- 温度・湿度・照度・人感センサーのデータ取得
- Nature Remo E / E Liteによるスマートメーターの電力データ取得
- カスタムサービスによる照明の詳細な制御（モード指定など）

---

## インストール方法

1. 本リポジトリを以下のパスに配置してください：

```
<設定フォルダ>/custom_components/nature_remo/
```

2. Home Assistantを再起動してください。

---

## セットアップ手順

1. Home Assistantの「設定 → デバイスとサービス → 統合を追加」から `Nature Remo` を選択します。
2. アクセストークン（APIキー）と統合の名前を入力します。
   - トークンは [Nature公式サイト](https://home.nature.global) から発行できます。
3. 登録済みのデバイスや家電が自動的に追加されます。

---

## オプション設定

- データの更新間隔（秒単位）を指定できます。
  - デフォルトは `60秒` に設定されています。

---

## 対応しているエンティティ

| 種類      | 説明                    |
| ------- | --------------------- |
| climate | エアコンの制御（冷暖房、除湿など）     |
| light   | 照明の制御（ON/OFF、モード選択）   |
| sensor  | 温度・湿度・照度・人感・電力（買電/売電） |

※ 今後、さらに対応デバイスやエンティティを拡張予定です。

---

## 作者情報

- 作成者：[@nanosns](https://github.com/nanosns)(NaNaRin)
- 所属・運営：[@NaNaLinks](https://github.com/NaNaLinks)
- SNS： [note](https://note.com/nanomana), [Qiita](https://qiita.com/NaNaRin), [X](https://x.com/NaNaRin_ks)

---

## ライセンス

MIT License

