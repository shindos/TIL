# JNDI
- Java Naming and Directory Interface
  - Javaから以下を扱うためのインターフェースを規定した仕様
    - ネーミングサービス
    - ディレクトリサービス
- ざっくりこんなの
```
InitialContext ictx = new InitialContext();
DataSource ds = (DataSource) ictx.lookup("java:comp/env/jdbc/SampleDS");
```

## ネーミングサービス
- 名前をオブジェクトに関連付ける(bind)
- 名前をもとに、関連付けられたオブジェクトを検索する(lookup)
- バインディング
  - 名前とオブジェクトの関連付け

## ディレクトリー・サービス
- ネーミングサービスの拡張版
- ネーミング・サービスは名前から単にオブジェクト（への参照）を検索するのに対し、ディレクトリー・サービスはオブジェクトの属性も扱う
- 代表例: DNS(DomainNameSystem)
