---
title: Oracle Database の BizTalk アダプターの制限事項 |Microsoft Docs
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
ms.openlocfilehash: 8138449cf3af067c9a76848f203c7e1809f6adbc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986611"
---
# <a name="limitations-of-biztalk-adapter-for-oracle-database"></a>Oracle Database の BizTalk アダプターの制限事項
## <a name="general"></a>全般  
 次の制限事項を呼びます、 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]:  
  
- いくつかの例外がなければ、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]はアダプターの以前のリリースと互換性があります。 前回のリリース以降に発生した変更の一覧、次を参照してください。 [BizTalk Adapter for Oracle Database での主な機能](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md)します。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] XML 型をサポートしていません。  
  
- SQLEXECUTE 操作がタイムアウトの値を返しませんまたはプロシージャ、関数、またはパッケージには、IN OUT パラメーター。 このためを呼び出す必要がありますプロシージャ、関数、およびパッケージ専用の操作を使用している、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]これら Oracle の成果物を公開します。  
  
- プログラミングでは、プロキシを使用して Oracle データベースからデータを取得するときに、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] 65536 の複数のノードを持つ XML メッセージを逆シリアル化ではありません。 応答メッセージが 65536 のノード以下を確認します。 この制限を回避するには、アプリケーションの app.config ファイルを変更します。 手順については、次を参照してください。 [Oracle データベース アダプターを使用した運用上の問題のトラブルシューティングを行う](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md)します。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]は入力文字列し、アダプターによって実行される SQL コマンドを構築します。 ただし、入力文字列では、他の SQL コマンドも実行される場合があり、操作コントラクトが壊れる可能性があります。  
  
   アダプター ストアド プロシージャへの入力の REF CURSOR を提供しているシナリオを検討してください。 このようなシナリオでアダプター クライアントする必要があります提供コマンド、実行すると、REF CURSOR を取得します。 アダプターは、ストアド プロシージャに、REF CURSOR を次に渡します。 ただし、REF CURSOR を取得するためのコマンドは、データベースにいくつか追加の変更を実行する場合、ストアド プロシージャを実行するため、操作コントラクトがなくなります。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]のみに最大 2 つのレベルの入れ子の UDT をサポートしています。  
  
- アダプターを使用するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、資格情報、wcf-custom 送信ポートが正しくない要求メッセージは処理されません。 正しい資格情報を指定すると、Oracle データベースにメッセージを送信し、応答を受信します。 ただし、応答メッセージでは、出力ポートを使用できません。 このようなシナリオでは、ホスト インスタンスを再起動する必要があります。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] (レコードの種類、テーブル型、UDT、および VARRAY) などの複合型、BFILE データ型をサポートしていません。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]は循環参照があるユーザー定義型 (Udt) をサポートしていません。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]のフィールドを含むレコードのないサポートは、レコードの種類の PL/SQL テーブルを入力します。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Null の VARRAY で最初の要素の値を設定するクライアントを有効にしません。  
  
- PL/SQL のテーブルを除く、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]はパッケージ内で定義されている Udt をサポートしていません。  
  
## <a name="limitations-due-to-odpnet"></a>ODP.NET に関する制約  
 次の制限事項を呼びます、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ODP.NET の制限のため。  
  
- Oracle データ型の 10 進数の値を受け取る、ODP.NET は例外をスローしない入力の値には、アルファベット文字が含まれている場合。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]は ODP.NET、Oracle データベース アダプターとのインターフェイスも例外はスローされません、アルファベット文字を渡すときにします。 以下に例を示します。  
  
  -   挿入操作では値"54r"を渡すことは、例外はスローされません。値「54」は、代わりに挿入されます。  
  
  -   挿入操作の値を"r54"を渡すことは、例外はスローされません。値「0」は、代わりに挿入されます。  
  
- ODP.NET 制限のため、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]厳密に型指定された、厳密に型指定の REF CURSOR を使用してオーバー ロードされたプロシージャの使用をサポートしていません。 内部的には、アダプターは、REF CURSOR だけとして厳密に型指定された、厳密に型指定の REF CURSOR の両方を処理します。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]数値フィールドでインデックス化されていない PL/SQL テーブルをサポートしません。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]は任意の要素が含まれていない連想配列をサポートしていません。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]はローカル タイム ゾーンの属性 (TimeStampLTZ) を持つ TimeStamp データ型が含まれている Udt をサポートしていません。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]が含まれている Udt をサポートしていませんが、"." (期間)、名前にします。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] IN OUT パラメーターとして BLOB、CLOB、NCLOB データ型が含まれている Udt をサポートしていません。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Varray の Varray の次の単純型をサポートしていません: BFILE、IntervalDS、IntervalYM、TimeStampLTZ、および TimeStampTZ します。  
  
- 連想配列の制限のため PL/SQL テーブルまたは次のデータ型のいずれかが含まれているレコードの PL/SQL テーブルでサポートされていない、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:  
  
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
 [BizTalk Adapter for Oracle Database について](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)