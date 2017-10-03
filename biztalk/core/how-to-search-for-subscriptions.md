---
title: "サブスクリプションを検索する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Query tab [Administration Console], subscriptions
- Query tab [Administration Console], searching
- subscriptions, viewing
- subscriptions, searching
ms.assetid: 95f8fd20-2750-412b-a67b-18976e7706e2
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f1830a4c1dddfa3dcfc2a1177b69410dd8ee0ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-search-for-subscriptions"></a>サブスクリプションを検索する方法
使用することができます、**クエリ** タブのサブスクリプションを検索するには、BizTalk Server 管理コンソールでします。 これは、システム内に定義されているすべてのサブスクリプションを確認する場合に便利です。 ルーティング エラーのトラブルシューティングを行う際、構成が正しくないためにエラーの原因となっているサブスクリプションがあるかどうかを確認できます。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、BizTalk Server Operators グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-search-for-subscriptions"></a>サブスクリプションを検索するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]です。  
  
2.  コンソール ツリーで、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] を展開し、[BizTalk グループ] をクリックします。  
  
3.  詳細ウィンドウで、をクリックして、**新しいクエリ**タブです。  
  
4.  **クエリ式**グループにおいて、**値**列で、選択**サブスクリプション**ドロップダウン リスト ボックスからです。  
  
5.  **フィールド名**列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(**\***)、次の 1 つ以上選択します。  
  
    |アイテム|Description|  
    |----------|-----------------|  
    |**最大一致数**|一致項目の表示数を指定します。|  
    |**サービス インスタンス ID**|サブスクリプションをサービス インスタンス ID でフィルター選択できます。|  
    |**サービス名**|サブスクリプションをサービス名でフィルター選択できます。|  
    |**サブスクリプションの種類**|サブスクリプションをアクティベーションのサブスクリプションまたはインスタンスのサブスクリプションでフィルター選択できます。|  
  
6.  完了、**値**で行う選択範囲の適切な列、**フィールド名**列です。  
  
7.  実行し、必要に応じて、クエリに行を追加、**フィールド名**、**演算子**、および**値**列、およびクリック**実行クエリ**です。  
  
## <a name="see-also"></a>参照  
 [管理コンソールの [クエリ] タブを使用します。](../core/using-the-administration-console-query-tab.md)