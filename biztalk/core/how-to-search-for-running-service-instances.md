---
title: "実行中のサービス インスタンスを検索する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service instances, viewing
- service instances, Query tab [Administration Console]
- Query tab [Administration Console], service instances
- Query tab [Administration Console], searching
- service instances, searching
- service instances, running
ms.assetid: fc65bf33-c013-4e6a-b9fd-b4536811e7b4
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8873747b39d6fa178b813d361b72ccf24f44b54a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-search-for-running-service-instances"></a>実行中のサービス インスタンスを検索する方法
使用することができます、**クエリ** タブで、特定の検索するには、BizTalk Server 管理コンソールの退避、アクティブ、ブレークポイント、スケジュール、およびサービス インスタンスを再試行します。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、BizTalk Server Operators グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-search-for-running-service-instances"></a>実行中のサービス インスタンスを検索するには  
  
1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] を展開し、[BizTalk グループ] をクリックします。  
  
3.  詳細ウィンドウで、をクリックして、**新しいクエリ**タブです。  
  
4.  **クエリ式**グループの 、**値**列をオン**サービス インスタンスを実行している**ドロップダウン リスト ボックスからです。  
  
5.  **フィールド名**列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(**\***)、次の 1 つ以上選択します。  
  
    |アイテム|Description|  
    |----------|-----------------|  
    |**Application Name**|BizTalk Server アプリケーションの名前を指定します。|  
    |**作成日時**|指定した日付の前または後に作成された実行中のサービス インスタンスを検索します。|  
    |**結果をグループ化**|アプリケーション、ホスト名、保留中の操作の種類、サービス クラス、サービス インスタンスの状態、またはサービス名で結果をグループ化できます。|  
    |**Host Name**|BizTalk ホストの名前を指定します。|  
    |**インスタンスの状態**|アクティブなインスタンス、退避済みのインスタンス、実行準備完了のインスタンス、およびスケジュール済みのインスタンスを検索できます。|  
    |**最大一致数**|一致項目の表示数を指定します。|  
    |**保留中の操作**|中断または終了の操作が保留されている、実行中のサービス インスタンスを検索できます。|  
    |**サービス クラス**|[分離アダプター]、[メッセージング]、[メッセージング、分離アダプター]、[MSMQT]、[オーケストレーション]、または [ルーティング エラー報告] を指定して検索できます。|  
    |**サービス名**|実行中のサービス インスタンスをサービス名でグループ化またはフィルター選択できます。|  
    |**サービスの種類 ID**|メッセージをサービスの種類 ID でグループ化またはフィルター選択できます。|  
  
6.  完了、**値**で行う選択範囲の適切な列、**フィールド名**列です。  
  
7.  実行し、必要に応じて、クエリに行を追加、**フィールド名**、**演算子**、および**値**列、およびクリック**実行クエリ**です。  
  
## <a name="see-also"></a>参照  
 [管理コンソールの [クエリ] タブを使用します。](../core/using-the-administration-console-query-tab.md)