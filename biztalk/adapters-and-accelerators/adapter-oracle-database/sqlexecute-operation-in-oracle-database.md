---
title: "Oracle データベースで SQLEXECUTE 操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DML
- data manipulation language
- operations, DML
- SQLEXECUTE
ms.assetid: d7f881e4-c668-4f8e-b08a-ea6614b65910
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ac8d5c8284e1f273d4b9aef17e79e25636dc581
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sqlexecute-operation-in-oracle-database"></a>Oracle データベースで SQLEXECUTE 操作
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle のデータベース成果物の操作の標準セットを表示します。 これらの操作を使用すると、Oracle 関数またはプロシージャの呼び出しなどの操作または基本的な SQL データ操作言語 (DML) 操作でテーブルを実行できます。 ただし、シナリオが考えられます、ビジネス ロジックによって操作を実行する必要があること、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]発生しません。 たとえばをする可能性があります。  
  
-   表示されませんがデータベースのアイテムに対して操作を実行、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 たとえば、CURVAL または Oracle シーケンスの NEXTVAL を取得します。  
  
-   操作データ定義言語です。たとえば、テーブルを作成します。  
  
-   デザイン時に存在しませんでした、データベースの成果物の操作を実行します。たとえば、ビジネス ロジックによって作成される一時テーブル内のレコードを更新します。  
  
-   操作よりもテーブルでより複雑な DML 操作を実行する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェス; たとえば、クエリを実行して、含む JOIN 句です。  
  
 これらのシナリオでは、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] SQLEXECUTE 操作を表示します。 SQLEXECUTE 操作がルート ノード (/) の下に表示される、**カテゴリを選択**ペインで、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]と[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]です。  
  
 SQLEXECUTE 操作を使用すると、Oracle データベースでパラメーター化された SQL ステートメントを実行できます。 SQLEXECUTE 操作には、セットごとに、同じ SQL ステートメントを実行できるようにするパラメーター セットで構成される入力パラメーター ブロックがサポートされています。 SQLEXECUTE 操作は、レコード セットの汎用的な SQL ステートメントの結果を返します。  
  
> [!NOTE]
>  IN を渡すことができ、プロシージャ、関数、および SQLEXECUTE 操作内のパッケージに IN OUT パラメーターです。 Oracle データベースで指定されたパラメーターで呼び出された成果物が実行されます。ただし、SQLEXECUTE 操作返さない外の値と、クライアントに IN OUT パラメーターです。 プロシージャ、関数、またはパッケージを起動する場合をお勧めすることによって、専用の操作を呼び出すことを[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]これら Oracle の成果物用に公開します。  
  
 詳細については。  
  
-   使用して、SQLEXECUTE 操作を実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[SQLEXECUTE 操作を使用して BizTalk Server によって実行](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-biztalk-server.md)です。  
  
-   SQLEXECUTE 操作を実行して、モデルを使用して、WCF サービスを参照してください[SQLEXECUTE 操作を WCF サービス モデルを使用して実行](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)です。  
  
-   WCF チャネル モデルを使用して、SQLEXECUTE 操作を実行するを参照してください[WCF チャネル モデルを使用して SQLEXECUTE 操作を実行](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)です。  
  
-   メッセージの構造と SQLEXECUTE 操作を実行するための SOAP アクションを参照してください[SQLEXECUTE 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)