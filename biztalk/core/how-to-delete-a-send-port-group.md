---
title: 送信ポート グループを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send port groups, deleting
- managing [send port groups], deleting
- deleting, send port groups
ms.assetid: 90c01e58-d35c-4cb2-ac6d-92199199fb42
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bf0e1a75799671ecd2e52515481c3d3be32ee67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013691"
---
# <a name="how-to-delete-a-send-port-group"></a>送信ポート グループを削除する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポート グループを BizTalk アプリケーションから削除する方法について説明します。 送信ポート グループを BizTalk アプリケーションから削除すると、そのグループの BizTalk 管理データベースからも送信ポート グループが削除されます。 送信ポート グループを削除しても、そこに含まれる送信ポートは削除されません。  
  
 送信ポート グループを削除できるのは、次の条件を満たしている場合だけです。  
  
-   送信ポート グループにオーケストレーションがバインドされていない:  次の手順で、バインドを削除するには、ケースの場合は、[オーケストレーションをバインド解除する方法](../core/how-to-unbind-an-orchestration.md)します。  
  
-   送信ポート グループが停止および参加解除されている:  停止、および送信ポートを参加解除については、[送信ポートまたは送信ポート グループを参加解除する方法](../core/how-to-unenlist-a-send-port-or-send-port-group.md)と[送信ポートまたは送信ポート グループを停止する方法](../core/how-to-stop-a-send-port-or-send-port-group.md)を参照してください。  
  
-   送信ポート グループがパーティで参照されていない:  パーティから送信ポート グループへの参照を削除する方法の詳細については、[方法を表示または編集するパーティ](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca)を参照してください。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-delete-a-send-port-group"></a>送信ポート グループを削除するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]展開し、BizTalk グループを展開し、**アプリケーション**、し、削除する送信ポート グループを含むアプリケーションを展開します。  
  
3. をクリックして**送信ポート グループ**送信ポート グループを右クリックし、クリックして**削除**します。  
  
## <a name="see-also"></a>参照  
 [送信ポート グループの作成および構成](../core/creating-and-configuring-send-port-groups.md)