# Nature Remo - Home Assistant カスタム統合

Nature RemoをHome Assistantに連携するためのカスタムインテグレーションです。
エアコンや照明の操作、温度・湿度などの情報をHome Assistant上でまとめて扱えるようになります。

---

## ⚠️ ご注意
このカスタムインテグレーションは、Nature社およびHome Assistantの**非公式**な統合です。
利用にあたっては、**自己責任で**ご使用いただきますようお願いいたします。

---

## 本プロジェクトはNaNaLinks様からのフォークです。

- Nature_remo関連のインテグレーションの中で更新が一番最近(2025/5/9)なこちらをフォークさせていただきました。

---

## 背景

- 内部クリーン機能は、冷房で発生したエアコン内の結露によるカビ発生を防ぐために、運転停止後しばらく送風モードで結露を飛ばす便利機能である。
- 2025年、スマートホーム機器はSwitchbotがトップシェアだが、未だにアプリが、霧ヶ峰エアコンの風向・内部クリーン・Ecoに対応しない。
- さらにSwitchbotの公式インテグレーション自体も、エアコンは温度ぐらいしか操作できないようだ。
- Nature remoは知名度が低いものの、以前からAPIを公開しており玄人に好まれてきた。2024年8月23日、アプリが内部クリーン・Ecoに対応した。

## 変更点

- インテグレーションの仕組みはよくわからないので、最終的にNature remo APIに送信するPayloadのうち、power-offのコマンドに、autoclean on, echo onも追記する。
- これでいいのかわからないけどとりあえずHAOSから電源オフを送った後に送風し始めたのでおけ！
- 今は夏なのでこれでいい。
- 冬になったらこの記述を消せばいい。

---

## インストール方法

1. 本リポジトリのcustom_components以下を、HAOSのconfig/custom_components以下に配置してください：

```
config/custom_components/nature_remo/
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

## 対応エンティティ一覧

| 種類    | 説明                                                              |
|---------|-------------------------------------------------------------------|
| climate | エアコンの操作（冷房・暖房・除湿など）                           |
| light   | 照明の操作（オン／オフ、モード切替）                              |
| sensor  | 温度、湿度、照度、人感、電力（買電／売電）                        |
| remote  | IR／AC／LIGHTのアプライアンスに定義された signals を送信できる   |

※ 今後、さらに対応デバイスやエンティティを拡張予定です。

---

## サンプル：リモートエンティティの使い方

Nature Remoに定義された `signals` 情報をもとに `remote` エンティティが生成されます。
Home Assistant上からremote.send_commandを送信できます。

### 例：サービス呼び出し

以下のように `remote.send_command` を使って信号を送信します：

```yaml
service: remote.send_command
target:
  entity_id: remote.living_room_remote  # リモートエンティティID
data:
  command: "電源"  # Remoに登録されたボタン名
```

---

## 作者様情報

- 作成者：[@nanosns](https://github.com/nanosns)(NaNaRin)
- 所属・運営：[@NaNaLinks](https://github.com/NaNaLinks)
- SNS： [note](https://note.com/nanomana), [Qiita](https://qiita.com/NaNaRin), [X](https://x.com/NaNaRin_ks)

---

## ライセンス

MIT License

