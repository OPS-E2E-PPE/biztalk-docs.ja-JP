---
title: "送信ポートまたは送信ポート グループを開始する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- starting, send port groups
- starting, send ports
- managing [send port groups], starting
- managing [send ports], starting
- send port groups, starting
- send ports, starting
ms.assetid: f17c0b7c-cad7-4c5e-a08c-3ebf838faa54
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 558a9b8444a38607f18757ff09196e44a3ae0b71
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-start-a-send-port-or-send-port-group"></a>送信ポートまたは送信ポート グループを開始する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートまたは送信ポート グループを開始する方法について説明します。 メッセージを処理できるようにするには、送信ポートまたは送信ポート グループを開始する必要があります。 参加解除した送信ポート グループまたは送信ポートを開始した場合、BizTalk は、送信ポートまたは送信ポート グループを参加させてから開始します。 送信ポート グループを開始するには、グループ内の 1 つ以上の送信ポートが参加済みの状態になっている必要があります。 送信ポート グループを開始または停止しても、そのグループに属する各送信ポートの状態は変わりません。  
  
> [!NOTE]
>  既定では、BizTalk アプリケーションを開始すると、そこに含まれるすべてのアイテムが開始されます。 詳細については、次を参照してください。[起動し、BizTalk アプリケーションを停止する方法](../core/how-to-start-and-stop-a-biztalk-application.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server Operators グループまたは BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-start-a-send-port-or-send-port-group"></a>送信ポートまたは送信ポート グループを開始するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**アプリケーション**、し、送信ポートまたはする送信ポート グループを含むアプリケーションを展開起動します。  
  
3.  をクリックして**送信ポート**または**送信ポート グループ**送信ポートまたは送信ポート グループを右クリックし、クリックして**開始**です。  
  
## <a name="see-also"></a>参照  
 [送信ポートと送信ポート グループの管理](../core/managing-send-ports-and-send-port-groups.md)