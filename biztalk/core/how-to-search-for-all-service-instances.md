---
title: "すべてのサービス インスタンスを検索する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service instances, Query tab [Administration Console]
- Query tab [Administration Console], service instances
- Query tab [Administration Console], searching
- service instances, searching
- instances, services
ms.assetid: 48cb885c-aaf1-44e8-9810-2e70cf63db81
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e96622fad23c28c0d4147f64a11cc540e88e7f97
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-search-for-all-service-instances"></a>すべてのサービス インスタンスを検索する方法
使用することができます、**クエリ** タブで、BizTalk Server 管理コンソールのすべてのサービス インスタンスを検索します。 実行中のインスタンスまたは中断されたインスタンスがある場合、特定のサービスの種類の参加を解除することはできません。 特定のサービスの種類の参加を解除する前に、すべてのサービス インスタンスを検索して、実行中または中断されたインスタンスがないことを確認してください。  
  
> [!NOTE]
>  URI によるグループ化とフィルター選択を行うと、検索結果には送信ポートと受信ポートのみが表示されます。 URI によるグループ化とフィルター選択はオーケストレーションには使用できないので、表示される結果にオーケストレーションは含まれません。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、BizTalk Server Operators グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-search-for-all-service-instances"></a>すべてのサービス インスタンスを検索するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] を展開し、[BizTalk グループ] をクリックします。  
  
3.  詳細ウィンドウで、をクリックして、**新しいクエリ**タブです。  
  
4.  **クエリ式**グループにおいて、**値**列で、選択**進行中のすべてのサービス インスタンス**ドロップダウン リスト ボックスからです。  
  
5.  **フィールド名**列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(**\***)、次の 1 つ以上選択します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**Application Name**|BizTalk Server アプリケーションの名前を指定します。|  
    |**作成日時**|指定した日付の前または後に作成されたすべてのサービス インスタンスを検索します。|  
    |**結果をグループ化**|アプリケーション、ホスト名、サービス クラス、サービス インスタンスの状態、またはサービス名で結果をグループ化できます。|  
    |**Host Name**|BizTalk ホストの名前を指定します。|  
    |**インスタンスの状態**|実行中のすべてのインスタンス、中断されたすべてのインスタンス、アクティブなインスタンス、退避済みのインスタンス、実行準備完了のインスタンス、スケジュール済みのインスタンス、中断された再開不可のインスタンス、または中断された再開可能なインスタンスを検索できます。|  
    |**最大一致数**|一致項目の表示数を指定します (必須)。 通常は 50 (既定値) に設定します。<br /><br /> [結果をグループ化する条件] を選択した場合、レコード数の合計ではなく、グループ数が表示されます。|  
    |**サービス クラス**|[分離アダプター]、[メッセージング]、[メッセージング、分離アダプター]、[MSMQT]、[オーケストレーション]、または [ルーティング エラー報告] を指定して検索できます。|  
    |**サービス インスタンス ID**|サービス インスタンスをサービス インスタンス ID でグループ化またはフィルター選択できます。|  
    |**サービス名**|サービス インスタンスをサービス名でグループ化またはフィルター選択できます。|  
    |**サービスの種類 ID**|サービス インスタンスをサービスの種類 ID でグループ化またはフィルター選択できます。|  
  
6.  完了、**値**で行う選択範囲の適切な列、**フィールド名**列です。  
  
7.  実行し、必要に応じて、クエリに行を追加、**フィールド名**、**演算子**、および**値**列、およびクリック**実行クエリ**です。  
  
## <a name="see-also"></a>参照  
 [管理コンソールの [クエリ] タブを使用します。](../core/using-the-administration-console-query-tab.md)