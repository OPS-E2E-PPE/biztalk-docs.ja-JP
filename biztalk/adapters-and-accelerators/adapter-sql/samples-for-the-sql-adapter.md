---
title: SQL アダプタのサンプル |Microsoft Docs
description: BizTalk Server、WCF サービス モデル、および WCF チャネル モデルで使用できる SQL WCF アダプタのサンプル
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2438696-bc51-46df-81ca-00c17a52736e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f7ff1e686fd8de344c4de4513fbda84003c69a8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982635"
---
# <a name="samples-for-the-sql-adapter"></a>SQL アダプタのサンプル

サンプルは[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]に分類されます。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] サンプル  
  
- WCF サービス モデルのサンプル  
  
- WCF チャネル モデルのサンプル  
  
サンプルについては、「 [BizTalk Adapter Pack 2010: SQL アダプタ サンプル](https://www.microsoft.com/download/details.aspx?id=22455)します。 テーブル、データベースなどのサンプルで使用されるオブジェクトを作成するための SQL スクリプトと手順が含まれます。 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
サンプルを次に示します。
  
## <a name="biztalk-server-samples"></a>BizTalk Server のサンプル  
  
|  サンプルのディレクトリ名  |                                                                                          説明                                                                                          |
|-------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ExecuteStoredProcedure  |      アダプターを使用して SQL Server データベース内のストアド プロシージャを呼び出す方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。      |
|       SelectTable       |  アダプターを使用して SQL Server データベース テーブルでの選択操作を実行する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。  |
|   CompositeOperations   |    アダプターを使用して SQL Server データベースでの複合操作を実行する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。    |
|      TypedPolling       |   アダプターを使用して SQL Server データベースで厳密に型指定されたポーリングを実行する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。   |
|   FILESTREAMOperation   | アダプターを使用してデータベースを SQL Server 2008 の FILESTREAM 操作を実行する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 |
| IncrementalNotification | アダプターを使用して SQL Server データベースからインクリメンタル通知を受信する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 |
| Employee_PurchaseOrder  |                  サンプルに基づいて[チュートリアル 2: 従業員 - 発注プロセス SQL アダプターを使用して](tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md)します。                  |
  
## <a name="wcf-service-model-samples"></a>WCF サービス モデルのサンプル   
  
|サンプルのディレクトリ名|説明|  
|---------------------------|-----------------|  
|EmployeeBasicOps|Insert、Select、Update を実行して、アダプターを使用して SQL Server データベースでの操作を削除する方法を示します。|  
|ExecuteReader|アダプターを使用して SQL Server データベースで ExecuteReader 操作を呼び出す方法を示します。|  
|Execute_StoredProc|アダプターを使用して SQL Server データベースでストアド プロシージャを呼び出す方法を示します。|  
|Execute_TypedStoredProcedure|厳密に型指定されたアダプターを使用して SQL Server データベースでストアド プロシージャを呼び出す方法を示します。|  
|Records_FILESTREAM_Op|アダプターを使用して SQL Server データベース テーブル内の FILESTREAM データを更新する方法を示します。|  
|ScalarFunction_ServiceModel|アダプターを使用して SQL Server データベースのスカラー関数を呼び出す方法を示します。|  
|TableFunction_ServiceModel|アダプターを使用して SQL Server データベースのテーブル値関数を呼び出す方法を示します。|  
|Polling_ServiceModel|アダプターを使用して SQL Server データベースからのポーリングに基づいたデータ変更メッセージを受信する方法を示します。|  
|TypedPolling_ServiceModel|アダプターを使用して SQL Server データベースからのポーリングに基づいたデータ変更メッセージを厳密に型指定されたを受信する方法を示します。|  
|Notification_ServiceModel|アダプターを使用して SQL Server データベースからクエリ通知を受信する方法を示します。|  
  
## <a name="wcf-channel-model-samples"></a>WCF チャネル モデルのサンプル 
  
|サンプルのディレクトリ名|説明|  
|---------------------------|-----------------|  
|EmployeeInsertOp|アダプターを使用して SQL Server データベースに対して、挿入操作を実行する方法を示します。|  
|Polling_ChannelModel|アダプターを使用して SQL Server データベースからのポーリングに基づいたデータ変更メッセージを受信する方法を示します。|  
  
## <a name="see-also"></a>参照  
[SQL アプリケーションを開発する](develop-your-sql-applications.md)