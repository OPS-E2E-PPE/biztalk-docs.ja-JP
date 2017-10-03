---
title: "参加させる、またはロールに対してパーティを参加解除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [role links], enlisting
- enlisting, role links
- role links, unenlisting
- role links, enlisting
- managing [role links], unenlisting
ms.assetid: 06fc2a64-3add-400c-9f9d-fab22fdf5366
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8af988a001e63ba210e5d5c224eeb486800b7286
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enlist-or-unenlist-a-party-for-a-role"></a>ロールに対してパーティを参加させる、または参加解除する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、ロールに対してパーティを参加させる、または参加解除する方法について説明します。 ロールにパーティを参加させるとパーティがロールに割り当てられ、パーティを参加解除するとパーティがロールから削除されます。  
  
 ロールに対してパーティを参加させる、または参加解除する場合は、次の点に注意してください。  
  
-   参加させるパーティをあらかじめ作成しておく必要があります。 手順については、次を参照してください。[パーティを作成する方法](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044)です。  
  
-   ロールに対してパーティを参加させる、または参加解除する場合、アプリケーションを再起動する必要はありません。  
  
> [!NOTE]
>  アプリケーション開発者が開発プロセス中にパーティを参加させる、または参加解除するには、このトピックの手順を実行します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-enlist-or-unenlist-a-party-for-a-role"></a>ロールに対してパーティを参加させる、または参加解除するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**アプリケーション**、し、参加するロール リンクを含むアプリケーションを展開またはパーティの参加を解除します。  
  
3.  をクリックして**ロール リンク**、参加または、パーティの参加を解除し、をクリックするロール リンクを右クリックして**プロパティ**です。  
  
4.  パーティを参加させるには、次の手順を実行します。  
  
    -   をクリックして**Enlist**参加させるパーティをクリックします。  
  
    -   をクリックして**バインド**で、**送信ポート**ドロップダウン リストで、クリックして、送信ポートのこのパーティに使用する をクリック**ok** 2 回クリックします。  
  
5.  パーティの参加を解除するパーティをクリックすると、をクリックして**参加解除**、順にクリック**OK**です。  
  
## <a name="see-also"></a>参照  
 [ロール リンクの管理](../core/managing-role-links.md)