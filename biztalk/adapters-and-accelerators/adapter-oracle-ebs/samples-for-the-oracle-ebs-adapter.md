---
title: Oracle EBS アダプターのサンプル |Microsoft Docs
description: BizTalk Server、WCF サービス モデル、および WCF チャネル モデルで使用できる oracle Enterprise Business Suite の WCF アダプタのサンプル
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 12f19f13-3b01-40d6-b12c-811f99841040
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4fdffd6d24ce18c38c45a086ea0f6376241d21d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000891"
---
# <a name="samples-for-the-oracle-ebs-adapter"></a>Oracle EBS アダプター用のサンプル
サンプルは[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]に分類されます。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] サンプル  
  
- WCF サービス モデルのサンプル  
  
- WCF チャネル モデルのサンプル  
  
- Microsoft Office SharePoint Server のサンプル  
  
  サンプルについては、「 [BizTalk Adapter Pack 2010: Oracle E-business Suite アダプター サンプル](https://www.microsoft.com/download/details.aspx?id=6464)します。 インターフェイス テーブル、同時実行プログラム、テーブル、およびサンプルで使用されるパッケージを作成するための SQL スクリプトが含まれます。 
  
> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
 サンプルを次に示します。 
  
## <a name="biztalk-server-samples"></a>BizTalk Server のサンプル  
  
|    サンプルのディレクトリ名     |                                                                                                                                                                        説明                                                                                                                                                                        |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     InterfaceTableInsert     |                                                                                   Oracle E-business Suite を使用して、インターフェイス テーブルにレコードを挿入する方法を示します[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。                                                                                    |
|      ConcurrentProgram       |                                                                                       Oracle E-business Suite を使用して同時実行プログラムを呼び出す方法を示します、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。                                                                                       |
|          RequestSet          |                                                                                          Oracle E-business Suite を使用して設定要求を呼び出す方法を示します、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。                                                                                           |
|      MsgContextProperty      | によって公開されているメッセージ コンテキスト プロパティを使用する方法を示します、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite を使用して成果物の操作を実行するアプリケーションのコンテキストを設定する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 |
| OracleEBS_CompositeOperation |                                                                                      Oracle E-business Suite を使用して複合操作を実行する方法を示します、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。                                                                                       |
|   OracleNotifyIncremental    |                                                                                   Oracle を使用してから「インクリメント」のクエリ通知メッセージを受信する方法を示します、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。                                                                                    |
| PollingUsingSelectStatement  |                                                                            SELECT ステートメントを使用して、ポーリング クエリを構成しを使用して結果を受信する方法を示します、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。                                                                            |
|    PollingUsingStoredProc    |                                                                            使用して結果を受信およびストアド プロシージャを使用して、ポーリング クエリを構成する方法を示します、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。                                                                            |
  
## <a name="wcf-service-model-sasamplesmples"></a>WCF サービス モデル Sasamplesmples  
  
|サンプルのディレクトリ名|説明|  
|---------------------------|-----------------|  
|ConcProgram_ServiceModel|アダプターを使用して Oracle E-business Suite での同時実行プログラムを呼び出す方法を示します。|  
|ExecuteReader|アダプターを使用して Oracle E-business Suite で ExecuteReader 操作を呼び出す方法を示します。|  
|Interface_Table_Ops|アダプターを使用して Oracle E-business Suite のインターフェイス テーブルでの操作を実行する方法を示します。|  
|LargeDataTypes_ServiceModel|アダプターを使用して Oracle E-business Suite での大規模なデータ型の列を持つテーブルに対する操作を実行する方法を示します。|  
|Notification_ServiceModel|アダプターを使用して Oracle E-business Suite の背後にあるデータベースから通知を受け取る方法を示します。|  
|SelectPolling_ServiceModel|SELECT ステートメントを使用して、アダプターを使用して Oracle E-business Suite のインターフェイス テーブルをポーリングする方法を示します。|  
|StoredProcPolling_ServiceModel|ストアド プロシージャを使用して、アダプターを使用して Oracle E-business Suite 内のテーブルをポーリングする方法を示します。|  
  
## <a name="wcf-channel-model-samples"></a>WCF チャネル モデルのサンプル  
  
|サンプルのディレクトリ名|説明|  
|---------------------------|-----------------|  
|InsertOperation|アダプターを使用して Oracle E-business Suite のインターフェイス テーブルで挿入操作を実行する方法を示します。|  
|SelectPolling_ChannelModel|SELECT ステートメントを使用して、アダプターを使用して Oracle E-business Suite のインターフェイス テーブルをポーリングする方法を示します。|  
  
## <a name="microsoft-office-sharepoint-server-samples"></a>Microsoft Office SharePoint Server のサンプル  
  
| サンプルのディレクトリ名 |                                                                                                                                                                  説明                                                                                                                                                                   |
|-----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      MOSS_Sample      | 使用する方法を示します、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite の成果物から Windows Communication Foundation (WCF) サービスを作成し、ビジネス データ一覧 Web パーツを使用して Microsoft Office SharePoint Server にデータを表示する WCF サービスを使用します。 |
  
## <a name="see-also"></a>参照  
[Oracle E-business Suite アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)