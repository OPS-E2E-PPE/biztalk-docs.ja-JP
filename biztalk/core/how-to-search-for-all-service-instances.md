---
title: すべてのサービス インスタンスを検索する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service instances, Query tab [Administration Console]
- Query tab [Administration Console], service instances
- Query tab [Administration Console], searching
- service instances, searching
- instances, services
ms.assetid: 48cb885c-aaf1-44e8-9810-2e70cf63db81
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbc3bc4383d3f2bd36a18adfdac33cca80482a72
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334800"
---
# <a name="how-to-search-for-all-service-instances"></a>すべてのサービス インスタンスを検索する方法
使用することができます、**クエリ** タブですべてのサービス インスタンスを検索するには、BizTalk Server 管理コンソール。 任意の実行中または中断されたインスタンスがある場合は、特定のサービスの種類の参加を解除することはできません。 たとえば、特定のサービスの種類の参加を解除する前に、実行中または中断されたインスタンスがないことを確認するすべてのサービス インスタンスを検索できます。  

> [!NOTE]
>  ときにグループ化とフィルタ リング、URI でのみ送信および受信ポートは、結果に表示されます。 グループ化し、URI でのフィルター処理には、オーケストレーションでは、表示される結果に含まれていないことはできません。  

## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、BizTalk Server Operators グループのメンバーとしてログオンする必要があります。  

### <a name="to-search-for-all-service-instances"></a>すべてのサービス インスタンスを検索するには  

1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

2. コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、し、[BizTalk グループ] をクリックします。  

3. 詳細ウィンドウでをクリックして、**新しいクエリ**タブ。  

4. **クエリ式**グループに、**値**列で、**進行中のすべてのサービス インスタンス**ドロップダウン リスト ボックスから。  

5. **フィールド名**列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(* *\\* * *)、次の 1 つ以上選択します。  


   |        プロパティ         |                                                                                                              目的                                                                                                              |
   |-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  **Application Name**   |                                                                                                   BizTalk Server アプリケーションです。                                                                                                    |
   |    **作成時刻**    |                                                                                指定した日付の前後に作成されたすべてのサービス インスタンスを検索します。                                                                                |
   |  **結果をグループ化**   |                                                              アプリケーション、ホスト名、サービス クラス、サービス インスタンスの状態、またはサービス名で結果をグループ化することができます。                                                               |
   |      **Host Name**      |                                                                                                    BizTalk ホストの名前。                                                                                                     |
   |   **インスタンスの状態**   | 実行中のすべてのインスタンス、中断されたすべてのインスタンス、アクティブなインスタンス、退避済みのインスタンスを検索すること、インスタンス、スケジュール済みのインスタンス、中断、再開不可のインスタンスまたは一時停止、再開可能なインスタンスを実行する準備ができました。 |
   |   **最大一致数**   |               一致項目の数 (必須) を表示します。 これは通常、50、既定値に設定します。<br /><br /> 結果をグループ化する場合、グループ、レコードの合計数ではない数が表示されます。               |
   |    **サービス クラス**    |                                                 分離アダプターは; を検索することができます。メッセージング。メッセージング、および分離アダプタです。MSMQT;オーケストレーションです。または、ルーティング エラー報告します。                                                  |
   | **サービス インスタンス ID** |                                                                                  グループ化したり、サービス インスタンスをサービス インスタンス ID でフィルター処理                                                                                   |
   |    **[サービス名]**     |                                                                                      グループ化またはサービス インスタンスをサービス名でフィルター処理できます。                                                                                      |
   |   **サービスの種類 ID**   |                                                                                    グループ化したり、サービス インスタンスをサービスの種類 ID でフィルター処理                                                                                     |


6. 完了、**値**で行った選択の適切な列、**フィールド名**列。  

7. 実行して、必要に応じて、クエリに行を追加、**フィールド名**、**演算子**、および**値**列、およびクリック**実行クエリ**します。  

## <a name="see-also"></a>参照  
 [管理コンソールの [クエリ] タブの使用](../core/using-the-administration-console-query-tab.md)