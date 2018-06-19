---
title: 送信ポートまたは送信ポート グループを停止する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [send ports], stopping
- managing [send port groups], stopping
- stopping, send ports
- send port groups, stopping
- stopping, send port groups
- send ports, stopping
ms.assetid: a7a5eab3-34fe-4417-900a-c37ec16ec009
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94ac3391a7a14955198f7e7635765665d48af1ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255322"
---
# <a name="how-to-stop-a-send-port-or-send-port-group"></a>送信ポートまたは送信ポート グループを停止する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートまたは送信ポート グループを停止する方法について説明します。 送信ポートまたは送信ポート グループを停止すると、それ以降、メッセージは処理されなくなります。 BizTalk Server は、停止された送信ポートまたは送信ポート グループに対する、すべてのアクティベーション メッセージを中断します。 ただし、送信ポート グループを停止しても、そこに含まれる個々の送信ポートの状態は変わりません。  
  
> [!NOTE]
>  既定では、BizTalk アプリケーションを開始すると、そこに含まれるすべてのアイテムが開始されます。 詳細については、次を参照してください。[起動し、BizTalk アプリケーションを停止する方法](../core/how-to-start-and-stop-a-biztalk-application.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server Operators グループまたは BizTalk Server 管理者グループのメンバー アカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-stop-a-send-port-or-send-port-group"></a>送信ポートまたは送信ポート グループを停止するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**アプリケーション**、し、送信ポートまたはする送信ポート グループを含むアプリケーションを展開停止します。  
  
3.  をクリックして**送信ポート**または**送信ポート グループ**送信ポートを右クリックし、または送信ポートと、をクリックして**停止**です。  
  
## <a name="see-also"></a>参照  
 [送信ポートと送信ポート グループの管理](../core/managing-send-ports-and-send-port-groups.md)