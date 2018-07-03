---
title: 送信ポートまたは送信ポート グループを開始する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- starting, send port groups
- starting, send ports
- managing [send port groups], starting
- managing [send ports], starting
- send port groups, starting
- send ports, starting
ms.assetid: f17c0b7c-cad7-4c5e-a08c-3ebf838faa54
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f3f88eca5a0c919de2c278bf1a11f8565de3f0f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971443"
---
# <a name="how-to-start-a-send-port-or-send-port-group"></a>送信ポートまたは送信ポート グループを開始する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートまたは送信ポート グループを開始する方法について説明します。 メッセージを処理できるようにするには、送信ポートまたは送信ポート グループを開始する必要があります。 参加解除した送信ポート グループまたは送信ポートを開始した場合、BizTalk は、送信ポートまたは送信ポート グループを参加させてから開始します。 送信ポート グループを開始するには、グループ内の 1 つ以上の送信ポートが参加済みの状態になっている必要があります。 送信ポート グループを開始または停止しても、そのグループに属する各送信ポートの状態は変わりません。  
  
> [!NOTE]
>  既定では、BizTalk アプリケーションを開始すると、そこに含まれるすべてのアイテムが開始されます。 詳細については、次を参照してください。 [BizTalk アプリケーション開始および停止方法](../core/how-to-start-and-stop-a-biztalk-application.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server Operators グループまたは BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-start-a-send-port-or-send-port-group"></a>送信ポートまたは送信ポート グループを開始するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**アプリケーション**、送信ポートまたは送信ポート グループにするを含むアプリケーションを展開し、起動します。  
  
3. をクリックして**送信ポート**または**送信ポート グループ**送信ポートまたは送信ポート グループを右クリックし、クリックして**開始**します。  
  
## <a name="see-also"></a>参照  
 [送信ポートと送信ポート グループの管理](../core/managing-send-ports-and-send-port-groups.md)