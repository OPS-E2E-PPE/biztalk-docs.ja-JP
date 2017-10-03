---
title: "SAP アダプターで SAPCommand クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SAPCommand, supported methods, classes, and constructors
ms.assetid: 55ad334e-1cc3-47c1-8764-be0f4e93f8b5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee083ed5afea06a5d350e9d73a9103adf157d8b4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sapcommand-class-in-the-sap-adapter"></a>SAP アダプターで SAPCommand クラス
このコマンドでは、SAP バックエンドで実行する SQL クエリを表します。 [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]現在 SELECT ステートメントと EXEC ステートメントのみをサポートします。 SELECT ステートメントには、1 つの SAP テーブルからのデータの抽出が有効にして、EXEC ステートメントは、SAP サーバーでの Rfc を実行するユーザーを有効にします。  
  
 これは、派生元**System.Data.Common.DbCommand**です。  
  
## <a name="supported-properties"></a>サポートされているプロパティ  
  
|名前|取得/設定|Description|  
|----------|--------------|-----------------|  
|**CommandText**|Get および Set|SELECT ステートメントおよび EXEC ステートメントをサポートしています。 SELECT ステートメントの詳細については、次を参照してください。 [SAP の SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)です。 EXEC ステートメントの詳細については、次を参照してください。 [SAP の EXEC ステートメントの構文](../../adapters-and-accelerators/adapter-sap/syntax-for-an-exec-statement-in-sap.md)です。|  
|**CommandTimeout**|Get および Set|サポートされていません。|  
|**CommandType**|Get および Set|CommandType.Text をサポートします。|  
|**接続**|Get および Set|コマンドが実行される基になる SAP 接続です。|  
|**DesignTimeVisible**|取得|サポートされていません。 False を返します。|  
|**パラメーター**|取得|このコマンドで使用されるパラメーター コレクション。|  
|**UpdatedRowSource**|-|サポートされていません。|  
  
## <a name="supported-methods"></a>サポートされているメソッド  
  
|名前|Description|  
|----------|-----------------|  
|**Cancel()**|バッチ内のデータの取得中に、コマンドをキャンセルします。 キャンセルは、バッチが取得された後に発生します。|  
|**ExecuteNonQuery()**|任意の DataReader は出力されません。 ただし、値がバインドされたパラメーター経由で使用可能になります。|  
|**ExecuteReader()**|結果セットとして、すべての複合型のエクスポートおよびテーブルのパラメーターに DataReader を出力します。 値は、バインドされたパラメーターを使用して取得することもできます。|  
|**ExecuteReader(CommandBehavior)**|サポートされている CommandBehaviors は次のとおりです。<br /><br /> -既定値します。<br />-SingleResult<br />-SingleRow<br />-SchemaOnly|  
|**ExecuteScalar()**|割り当てられます。<br /><br /> -CommandBehaviour.SingleRow SELECT ステートメント。<br />-CommandBehaviour.SingleResult EXEC ステートメントです。|  
|**Prepare()**|-EXEC サポートは、パラメーターをバインドします。<br />-選択のサポートは、パラメーターをバインドします。|  
  
## <a name="supported-constructors"></a>サポートされているコンス トラクター  
  
|名前|Description|  
|----------|-----------------|  
|**SAPCommand()**|SAPCommand の新しいインスタンスを作成します。|  
|**SAPCommand(string)**|コマンド テキストを含む SAPCommand です。|  
|**SAPCommand (string, SAPConnection)**|コマンドが実行されるコマンド テキストと SAPConnection オブジェクトを使用して、SAPCommand|  
  
## <a name="see-also"></a>参照  
 [SAP アダプターと ADO.NET インターフェイスを拡張します。](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)