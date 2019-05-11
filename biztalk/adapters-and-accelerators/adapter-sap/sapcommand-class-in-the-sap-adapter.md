---
title: SAP アダプターの SAPCommand クラス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPCommand, supported methods, classes, and constructors
ms.assetid: 55ad334e-1cc3-47c1-8764-be0f4e93f8b5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f822f7e0cc54385cfc53a99a0a3843d1df241718
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372975"
---
# <a name="sapcommand-class-in-the-sap-adapter"></a>SAP アダプターの SAPCommand クラス
このコマンドは、SAP バックエンドで実行する SQL クエリを表します。 [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]現在の選択と EXEC ステートメントでのみサポートしています。 SELECT ステートメントには、1 つの SAP テーブルからのデータの抽出が有効にして、EXEC ステートメントは、SAP サーバーでの Rfc を実行するユーザーを有効にします。  
  
 これは、派生元**System.Data.Common.DbCommand**します。  
  
## <a name="supported-properties"></a>サポートされているプロパティ  
  
|名前|Get/Set|説明|  
|----------|--------------|-----------------|  
|**CommandText**|Get と Set|SELECT ステートメントと EXEC ステートメントをサポートしています。 SELECT ステートメントの詳細については、次を参照してください。 [SAP で SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)します。 EXEC ステートメントの詳細については、次を参照してください。 [sap EXEC ステートメントの構文](../../adapters-and-accelerators/adapter-sap/syntax-for-an-exec-statement-in-sap.md)します。|  
|**CommandTimeout**|Get と Set|サポートされていません。|  
|**CommandType**|Get と Set|CommandType.Text がサポートされています。|  
|**Connection**|Get と Set|コマンドを実行する SAP の基になる接続します。|  
|**DesignTimeVisible**|取得|サポートされていません。 False を返します。|  
|**パラメーター**|取得|このコマンドで使用されるパラメーターのコレクション。|  
|**UpdatedRowSource**|-|サポートされていません。|  
  
## <a name="supported-methods"></a>サポートされているメソッド  
  
|名前|説明|  
|----------|-----------------|  
|**Cancel()**|バッチ内のデータの取得中にコマンドを取り消します。 キャンセルは、バッチが取得された後に発生します。|  
|**ExecuteNonQuery()**|任意の DataReader は出力されません。 ただし、値は、バインドされたパラメーターを使用して利用できるになります。|  
|**ExecuteReader()**|結果セットとして、すべての複合型のエクスポートとテーブル パラメーターの DataReader を出力します。 値は、バインドされたパラメーターを使用しても取得できます。|  
|**ExecuteReader(CommandBehavior)**|サポートされている CommandBehaviors は次のとおりです。<br /><br /> -Default します。<br />-SingleResult<br />-SingleRow<br />-Dataonly|  
|**ExecuteScalar()**|マップされます。<br /><br /> -CommandBehaviour.SingleRow SELECT ステートメント。<br />-CommandBehaviour.SingleResult EXEC ステートメントです。|  
|**Prepare()**|-EXEC サポートは、パラメーターをバインドします。<br />-選択のサポートは、パラメーターをバインドします。|  
  
## <a name="supported-constructors"></a>サポートされているコンス トラクター  
  
|名前|説明|  
|----------|-----------------|  
|**SAPCommand()**|SAPCommand の新しいインスタンスを作成します。|  
|**SAPCommand(string)**|SAPCommand コマンド テキストを使用します。|  
|**SAPCommand(string, SAPConnection)**|コマンドが実行されるコマンド テキスト SAPConnection オブジェクトを使用して SAPCommand|  
  
## <a name="see-also"></a>参照  
 [SAP アダプターを使用した ADO.NET インターフェイスを拡張します。](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)