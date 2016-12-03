# Webアプリケーションのレイヤー
- View
  - 表示
  - WebAPIの直接的なレスポンスはクライアント側で動作するJSONやXML形式に変換するのが一般的
  - Javaだと
    - Jersey
      - Controllerの戻り値をJSONに変換
- Controller
  - エンドユーザからのリクエストを受取り、適切なロジック(Service)を呼び出し、それに関連付けるデータを返す
- Service
  - Controllerに呼ばれ実際の処理を行う
  - メインのロジック
- DAO(Data Access Object)
  - DABの操作
  - Serviceが利用
  - 使用するDBを変更する、テーブルのカラムを拡張する等を扱う

# DTO
- DataTransferObject
- OOPのデザインパターン
- 関連するデータを1つにまとめ、データの格納・読み出しのためのメソッドを定義したオブジェクトのこと

## Bean、Entitiy、VO(VisualObject)、Formとの違い
- Bean: Javaの基本的な考え方として、DTOとEntity、Formを内包する
- Entity: テーブルのカラムを格納するBeanというイメージ
- Form: Web上の画面の入力/出力情報を保有
- VO: お金や時間など価値そのものを表す
