---
title: "送信ポートまたは送信ポート グループを参加させる方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- enlisting, send port groups
- enlisting, send ports
- send port groups, enlisting
- send ports, enlisting
- managing [send ports], enlisting
- managing [send port groups], enlisting
ms.assetid: d4298b8e-7dc7-4382-af86-c4db0982b7e0
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb42a4ceaa88ca3d04b5dfb6d6d3afc11847421a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enlist-a-send-port-or-send-port-group"></a>送信ポートまたは送信ポート グループを参加させる方法
このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートまたは送信ポート グループを参加させる方法について説明します。 送信ポートまたは送信ポート グループを参加させると、送信ポートまたは送信ポート グループが BizTalk ホストに関連付けられ、送信ポートまたは送信ポート グループのサブスクリプションが作成されます。 送信ポート グループに送信ポートが含まれていない場合は、送信ポート グループを参加させてもサブスクリプションは作成されません。 また、送信ポート グループを参加させても、送信ポート グループに含まれている送信ポートの状態は変わりません。  
  
> [!NOTE]
>  送信ポートまたは送信ポート グループを開始すると、自動的に参加させることができます。 既定では、アプリケーションを開始すると、そこに含まれるすべてのアイテムを開始して参加させることができます。 詳細については、次を参照してください。[送信ポートまたは送信ポート グループを開始する方法](../core/how-to-start-a-send-port-or-send-port-group.md)です。 参照してください[起動し、BizTalk アプリケーションを停止する方法](../core/how-to-start-and-stop-a-biztalk-application.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-enlist-a-send-port-or-send-port-group"></a>送信ポートまたは送信ポート グループを参加させるには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**アプリケーション**、し、送信ポートまたはする送信ポート グループを含むアプリケーションを展開参加します。  
  
3.  をクリックして**送信ポート**または**送信ポート グループ**送信ポートまたは送信ポート グループを右クリックし、クリックして**Enlist**です。  
  
## <a name="see-also"></a>参照  
 [送信ポートと送信ポート グループの管理](../core/managing-send-ports-and-send-port-groups.md)