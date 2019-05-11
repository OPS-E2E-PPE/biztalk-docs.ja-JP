---
title: 実行中のサービス インスタンスを検索する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service instances, viewing
- service instances, Query tab [Administration Console]
- Query tab [Administration Console], service instances
- Query tab [Administration Console], searching
- service instances, searching
- service instances, running
ms.assetid: fc65bf33-c013-4e6a-b9fd-b4536811e7b4
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9a09a2ed8f5f209549d7eb5246db4c4509eccd1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384019"
---
# <a name="how-to-search-for-running-service-instances"></a>実行中のサービス インスタンスを検索する方法
使用することができます、**クエリ** タブで、特定の検索するには、BizTalk Server 管理コンソールに退避された、アクティブ、ブレークポイント、スケジュール、およびサービス インスタンスを再試行しています。  

## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、BizTalk Server Operators グループのメンバーとしてログオンする必要があります。  

### <a name="to-search-for-running-service-instances"></a>実行中のサービス インスタンスを検索するには  

1. クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

2. コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、し、[BizTalk グループ] をクリックします。  

3. 詳細ウィンドウでをクリックして、**新しいクエリ**タブ。  

4. **クエリ式**グループに、**値**列で、**サービス インスタンスを実行している**ドロップダウン リスト ボックスから。  

5. **フィールド名**列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(* *\\* * *)、次の 1 つ以上選択します。  


   |          アイテム          |                                                             説明                                                             |
   |------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
   |  **Application Name**  |                                                   BizTalk Server アプリケーションです。                                                   |
   |   **作成時刻**    |                             検索する前に、または指定日付より後に作成されたサービス インスタンスを実行しています。                              |
   |  **結果をグループ化**  |  アプリケーション、操作の種類、サービス クラス、サービス インスタンスの状態、保留中のホスト名またはサービス名で結果をグループ化することができます。  |
   |     **Host Name**      |                                                    BizTalk ホストの名前。                                                    |
   |  **インスタンスの状態**   |             インスタンス、およびスケジュール済みのインスタンスを実行する準備がアクティブなインスタンス、退避済みのインスタンスを検索できます。             |
   |  **最大一致数**   |                                                  表示する一致の数。                                                  |
   | **保留中の操作** |                      中断または終了の保留中のサービス インスタンスの実行を検索することができます。                       |
   |   **サービス クラス**    | 分離アダプターは; を検索することができます。メッセージング。メッセージング、および分離アダプタです。MSMQT;オーケストレーションです。または、ルーティング エラー報告します。 |
   |    **[サービス名]**    |                                 グループ化したり、フィルター処理をサービス名でサービス インスタンスを実行します。                                  |
   |  **サービスの種類 ID**   |                                        グループ化したりフィルター サービスがメッセージ ID を入力します                                         |


6. 完了、**値**で行った選択の適切な列、**フィールド名**列。  

7. 実行して、必要に応じて、クエリに行を追加、**フィールド名**、**演算子**、および**値**列、およびクリック**実行クエリ**します。  

## <a name="see-also"></a>参照  
 [管理コンソールの [クエリ] タブの使用](../core/using-the-administration-console-query-tab.md)