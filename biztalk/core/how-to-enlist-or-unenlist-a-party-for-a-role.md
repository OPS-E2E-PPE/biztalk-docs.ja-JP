---
title: 参加またはロールに対してパーティを参加解除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [role links], enlisting
- enlisting, role links
- role links, unenlisting
- role links, enlisting
- managing [role links], unenlisting
ms.assetid: 06fc2a64-3add-400c-9f9d-fab22fdf5366
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 046e51424427973534d9e4defdbf6e8d58eb8b2f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966251"
---
# <a name="how-to-enlist-or-unenlist-a-party-for-a-role"></a>ロールに対してパーティを参加させる、または参加解除する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、ロールに対してパーティを参加させる、または参加解除する方法について説明します。 ロールにパーティを参加させるとパーティがロールに割り当てられ、パーティを参加解除するとパーティがロールから削除されます。  
  
 ロールに対してパーティを参加させる、または参加解除する場合は、次の点に注意してください。  
  
-   参加させるパーティをあらかじめ作成しておく必要があります。 手順については、次を参照してください。[パーティを作成する方法](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044)します。  
  
-   ロールに対してパーティを参加させる、または参加解除する場合、アプリケーションを再起動する必要はありません。  
  
> [!NOTE]
>  アプリケーション開発者が開発プロセス中にパーティを参加させる、または参加解除するには、このトピックの手順を実行します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-enlist-or-unenlist-a-party-for-a-role"></a>ロールに対してパーティを参加させる、または参加解除するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**アプリケーション**、参加するロール リンクを含むアプリケーションを展開し、またはパーティの参加を解除します。  
  
3. クリックして**ロール リンク**、参加や、パーティを参加解除 をクリックするロール リンクを右クリックして**プロパティ**します。  
  
4. パーティを参加させるには、次の手順を実行します。  
  
   -   クリックして**参加**に参加させるパーティをクリックします。  
  
   -   をクリックして**バインド**で、**送信ポート**ドロップダウン リストで、クリック、送信をこのパーティに使用するポートの順にクリックします**OK** 2 回です。  
  
5. パーティの参加を解除するパーティをクリックし**参加解除**、 をクリックし、 **OK**。  
  
## <a name="see-also"></a>参照  
 [ロール リンクの管理](../core/managing-role-links.md)