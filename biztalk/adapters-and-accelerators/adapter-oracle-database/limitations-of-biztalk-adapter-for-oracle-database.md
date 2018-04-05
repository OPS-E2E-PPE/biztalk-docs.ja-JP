---
title: Oracle Database の BizTalk アダプターの制限事項 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter, limitations of
ms.assetid: eab4ddea-f986-43c2-82bb-b9fe37961a5b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd6cfea523333752c0ee18fefbc6a1848057fe36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="limitations-of-biztalk-adapter-for-oracle-database"></a>Oracle Database の BizTalk アダプターの制限事項
## <a name="general"></a>全般  
 次はの既知の制限、 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]:  
  
-   いくつかの例外がなければ、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプターの以前のリリースと互換性ができます。 前回のリリースから発生した変更の一覧、次を参照してください。 [BizTalk adapter for Oracle データベースの主な特徴](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md)です。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] XML 型をサポートしていません。  
  
-   SQLEXECUTE 操作は、外の値を返しませんまたはプロシージャ、関数、またはパッケージに IN OUT パラメーターです。 このため、呼び出す必要がありますプロシージャ、関数、およびパッケージ専用の操作を使用している、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]これら Oracle の成果物用に公開します。  
  
-   プログラミングでは、プロキシを使用して Oracle データベースからデータを取得するときに、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] 65536 以上のノードを持つ XML メッセージを逆シリアル化ではありません。 応答メッセージに 65536 のノード少ないがあることを確認してください。 この制限は、アプリケーションの app.config ファイルを変更することで回避できます。 手順については、次を参照してください。 [Oracle データベース アダプターの運用上の問題のトラブルシューティングを行う](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md)です。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]は入力文字列し、アダプターによって実行される、SQL コマンドを構築します。 ただし、入力文字列も実行を取得する他の SQL コマンドが含まれ、操作コントラクトを中断する可能性があります。  
  
     アダプターがストアド プロシージャへの入力の REF CURSOR を提供するシナリオを検討してください。 このようなシナリオでは、アダプター クライアント必要があります提供コマンドを実行すると、REF CURSOR を取得します。 アダプターは、ストアド プロシージャに REF カーソル上で渡します。 ただし、REF CURSOR を取得するためのコマンドは、データベースにいくつか追加の変更を実行する場合、ストアド プロシージャを実行するため、操作コントラクトは解除されます。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]のみに最大 2 つのレベルの入れ子の UDT をサポートしています。  
  
-   アダプターを使用するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、WCF カスタムの資格情報の送信ポートが正しくない要求メッセージは処理されません。 正しい資格情報を指定すると、Oracle データベースにメッセージを送信し、応答を受信します。 ただし、応答メッセージでは、出力ポートを使用できません。 このようなシナリオでは、ホスト インスタンスを再起動する必要があります。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] (レコード型、テーブルの種類、UDT、および VARRAY) などの複合型の内部 BFILE データ型をサポートしていません。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]循環参照が含まれるユーザー定義型 (Udt) をサポートしていません。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]のフィールドを含むサポート レコードいないは、レコード型の PL/SQL テーブルを入力します。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を NULL に VARRAY で最初の要素の値を設定するクライアントを有効にしません。  
  
-   PL/SQL テーブルを除く、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]はパッケージ内で定義されている Udt をサポートしていません。  
  
## <a name="limitations-due-to-odpnet"></a>ODP.NET のための制限事項  
 次はの既知の制限、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ODP.NET の制限のため。  
  
-   Oracle データ型の 10 進値を受け取る、ODP.NET は例外をスローしません、入力値には、アルファベット文字が含まれている場合。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用 ODP.NET、Oracle データベース アダプターのインターフェイスをすぎる例外はスローされません、アルファベット文字を渡すときにします。 例:  
  
    -   挿入操作の値"54r"を渡すことは、例外はスローされません。代わりに「54」の値が挿入されます。  
  
    -   挿入操作の値"r54"を渡すことは、例外はスローされません。値「0」は、代わりに挿入されます。  
  
-   制限のため、ODP.NET、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]厳密に型指定され、弱い型指定の REF カーソルを使用するオーバー ロードされたプロシージャの使用をサポートしていません。 内部的には、アダプターは、REF CURSOR だけとして厳密に型指定され、弱い型指定の両方の REF CURSOR を扱います。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]数値フィールドをインデックス化されていない PL/SQL テーブルをサポートしていません。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]は含まれていない任意の要素の連想配列をサポートしていません。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]はローカル タイム ゾーンの属性 (TimeStampLTZ) を持つ TimeStamp データ型が含まれている Udt をサポートしていません。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Udt を含むをサポートしていない、"です"。 (期間)、名前にします。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] IN OUT パラメーターとして BLOB、CLOB、および NCLOB データ型が含まれている Udt をサポートしていません。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Varray の Varray の次の単純型をサポートしていません: BFILE、IntervalDS、IntervalYM、TimeStampLTZ、および TimeStampTZ です。  
  
-   連想配列の制限、により PL/SQL テーブルまたはデータ型を次のいずれかが含まれるレコードの PL/SQL テーブルでサポートされていない、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:  
  
    -   BFILE  
  
    -   BLOB  
  
    -   CLOB  
  
    -   IntervalDS  
  
    -   IntervalYM  
  
    -   Long  
  
    -   NCLOB  
  
    -   RowID  
  
    -   TimeStamp  
  
    -   TimeStampLTZ  
  
    -   TimeStampTZ  
  
## <a name="see-also"></a>参照  
 [Oracle データベースの BizTalk アダプターを理解します。](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)