---
title: サブスクリプションを検索する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Query tab [Administration Console], subscriptions
- Query tab [Administration Console], searching
- subscriptions, viewing
- subscriptions, searching
ms.assetid: 95f8fd20-2750-412b-a67b-18976e7706e2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 475510273ec8d97c7aa848667967c6917fc2c61c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334801"
---
# <a name="how-to-search-for-subscriptions"></a>サブスクリプションを検索する方法
使用することができます、**クエリ** タブでサブスクリプションを検索するには、BizTalk Server 管理コンソール。 これは、すべてのシステムで定義されているサブスクリプションを確認する場合に便利です。 ルーティング エラーのトラブルシューティングを行うため、ルーティング エラーの原因と、かどうかこれらのいずれかが正しく構成されていない、表示するサブスクリプションを確認できます。  

## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、BizTalk Server Operators グループのメンバーとしてログオンする必要があります。  

### <a name="to-search-for-subscriptions"></a>サブスクリプションを検索するには  

1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]します。  

2. コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、し、[BizTalk グループ] をクリックします。  

3. 詳細ウィンドウでをクリックして、**新しいクエリ**タブ。  

4. **クエリ式**グループに、**値**列で、**サブスクリプション**ドロップダウン リスト ボックスから。  

5. **フィールド名**列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(* *\\* * *)、次の 1 つ以上選択します。  


   |          アイテム           |                                    説明                                    |
   |-------------------------|-----------------------------------------------------------------------------------|
   |   **最大一致数**   |                         表示する一致の数。                         |
   | **サービス インスタンス ID** |               サービス インスタンス ID でサブスクリプションをフィルター処理できます。                |
   |    **[サービス名]**     |                   サブスクリプションは、サービス名でフィルター処理できます。                   |
   |  **サブスクリプションの種類**  | アクティベーションのサブスクリプションでサブスクリプションをフィルターすることも、インスタンスのサブスクリプションを処理することができます。 |


6. 完了、**値**で行った選択の適切な列、**フィールド名**列。  

7. 実行して、必要に応じて、クエリに行を追加、**フィールド名**、**演算子**、および**値**列、およびクリック**実行クエリ**します。  

## <a name="see-also"></a>参照  
 [管理コンソールの [クエリ] タブの使用](../core/using-the-administration-console-query-tab.md)