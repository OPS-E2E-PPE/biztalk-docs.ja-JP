---
title: "SQL アダプタ サンプル |Microsoft ドキュメント"
description: "BizTalk Server、WCF サービス モデル、および WCF チャネル モデルで使用できる SQL WCF アダプタのサンプル"
ms.custom: 
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2438696-bc51-46df-81ca-00c17a52736e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0729b18dc900800ed39ccae31acfdd37b38b4573
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="samples-for-the-sql-adapter"></a>SQL アダプタのサンプル

サンプルを[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]に分類されます。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]サンプル  
  
-   WCF サービス モデルのサンプル  
  
-   WCF チャネル モデルのサンプル  
  
サンプルはいただけます[BizTalk Adapter Pack 2010: SQL アダプタ サンプル](https://www.microsoft.com/download/details.aspx?id=22455)です。 テーブル、データベースなどのサンプルで使用されるオブジェクトを作成するための SQL スクリプトと手順が含まれます。 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
サンプルを次に示します。
  
## <a name="biztalk-server-samples"></a>BizTalk Server のサンプル  
  
|サンプルのディレクトリ名|Description|  
|---------------------------|-----------------|  
|ExecuteStoredProcedure|付いたアダプターを使用して SQL Server データベース内のストアド プロシージャを呼び出す方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。|  
|SelectTable|アダプターを使用して SQL Server データベース テーブルでの選択操作を実行する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。|  
|CompositeOperations|付いたアダプターを使用してデータベースを SQL Server で合成の操作を実行する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。|  
|TypedPolling|アダプターを使用して SQL Server データベースで厳密に型指定されたポーリングを実行する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。|  
|FILESTREAMOperation|付いたアダプターを使用してデータベースを SQL Server 2008 での FILESTREAM 操作を実行する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。|  
|IncrementalNotification|付いたアダプターを使用して SQL Server データベースからインクリメンタル通知を受信する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。|  
|Employee_PurchaseOrder|サンプルがに基づいて[チュートリアル 2: 従業員の発注プロセスには、SQL アダプターを使用して](tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md)です。|  
  
## <a name="wcf-service-model-samples"></a>WCF サービス モデルのサンプル   
  
|サンプルのディレクトリ名|Description|  
|---------------------------|-----------------|  
|EmployeeBasicOps|Insert、Select、Update を実行し、アダプターを使用して SQL Server データベースの操作を削除する方法を示します。|  
|ExecuteReader|アダプターを使用して SQL Server データベースでは ExecuteReader 操作を呼び出す方法を示します。|  
|Execute_StoredProc|アダプターを使用して SQL Server データベースにストアド プロシージャを呼び出す方法を示します。|  
|Execute_TypedStoredProcedure|アダプターを使用して SQL Server データベースの厳密に型指定されたストアド プロシージャを呼び出す方法を示します。|  
|Records_FILESTREAM_Op|アダプターを使用して SQL Server データベース テーブルに FILESTREAM データを更新する方法を示します。|  
|ScalarFunction_ServiceModel|アダプターを使用して SQL Server データベースのスカラー関数を呼び出す方法を示します。|  
|TableFunction_ServiceModel|アダプターを使用して SQL Server データベースにテーブル値関数を呼び出す方法を示します。|  
|Polling_ServiceModel|アダプターを使用して SQL Server データベースからデータ変更のポーリングに基づいたメッセージを受信する方法を示します。|  
|TypedPolling_ServiceModel|メッセージを受信する厳密に型指定されたポーリング ベース データが変更されて、アダプターを使用して SQL Server データベースからの方法を示します。|  
|Notification_ServiceModel|アダプターを使用して SQL Server データベースからクエリ通知を受信する方法を示します。|  
  
## <a name="wcf-channel-model-samples"></a>WCF チャネル モデルのサンプル 
  
|サンプルのディレクトリ名|Description|  
|---------------------------|-----------------|  
|EmployeeInsertOp|アダプターを使用して SQL Server データベースで挿入操作を実行する方法を示します。|  
|Polling_ChannelModel|アダプターを使用して SQL Server データベースからデータ変更のポーリングに基づいたメッセージを受信する方法を示します。|  
  
## <a name="see-also"></a>参照  
[SQL アプリケーションを開発する](develop-your-sql-applications.md)