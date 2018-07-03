---
title: Oracle データベースで SQLEXECUTE 操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DML
- data manipulation language
- operations, DML
- SQLEXECUTE
ms.assetid: d7f881e4-c668-4f8e-b08a-ea6614b65910
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfae55d12ce3b244001bf04aef48ff40b97d97a1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000513"
---
# <a name="sqlexecute-operation-in-oracle-database"></a>Oracle データベースで SQLEXECUTE 操作
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle データベース アイテムに対する操作の標準セットを明らかになります。 これらの操作を使用して、Oracle 関数またはプロシージャの呼び出しなどで行うまたは基本的な SQL データ操作言語 (DML) 操作でテーブルを実行できます。 ただし、ある可能性があります、ビジネス ロジックによって操作を実行する必要があるシナリオを[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]記録されません。 たとえば、しをたい場合があります。  
  
- 表示されませんがデータベースのアイテムに対して操作を実行、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 たとえば、CURVAL または Oracle のシーケンスの NEXTVAL を取得します。  
  
- データ定義言語の操作を実行します。たとえば、テーブルを作成します。  
  
- デザイン時に存在しませんでしたが、データベース成果物に対して操作を実行します。たとえば、ビジネス ロジックによって作成される一時テーブル内のレコードを更新します。  
  
- 操作よりもテーブルでより複雑な DML 操作を実行する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェス; JOIN 句を含むクエリを実行するなど。  
  
  このようなシナリオでの[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]SQLEXECUTE 操作を表示します。 SQLEXECUTE 操作にルート ノード (/) の下に表示される、**カテゴリを選択**ペインで、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]と[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]します。  
  
  SQLEXECUTE 操作を使用すると、Oracle データベースでパラメーター化 SQL ステートメントを実行できます。 SQLEXECUTE 操作では、セットごとに、同じ SQL ステートメントを実行するためのパラメーター セットで構成される入力パラメーター ブロックをサポートしています。 SQLEXECUTE 操作は、ジェネリック レコード セット内の SQL ステートメントの結果を返します。  
  
> [!NOTE]
>  渡すことができ、プロシージャ、関数、および SQLEXECUTE 操作内のパッケージには、IN OUT パラメーター。 Oracle データベースで指定されたパラメーターで呼び出された成果物が実行されます。ただし、SQLEXECUTE 操作がタイムアウトの値を返されませんとクライアントの OUT パラメーター。 専用の操作を呼び出して実行をお勧めプロシージャ、関数、またはパッケージを呼び出す場合を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]これら Oracle の成果物を公開します。  
  
 詳細については。  
  
- SQLEXECUTE 操作を使用して実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[SQLEXECUTE 操作を使用して BizTalk Server によって実行](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-biztalk-server.md)します。  
  
- SQLEXECUTE 操作を実行する WCF サービス モデルを使用して参照してください[SQLEXECUTE 操作を WCF サービス モデルを使用して実行](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)します。  
  
- WCF チャネル モデルを使用して、SQLEXECUTE 操作を実行するを参照してください[WCF チャネル モデルを使用して、SQLEXECUTE 操作の実行](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)します。  
  
- メッセージの構造と SQLEXECUTE 操作を実行するための SOAP アクションを参照してください[SQLEXECUTE 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md)します。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)