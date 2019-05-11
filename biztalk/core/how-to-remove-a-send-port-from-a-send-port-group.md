---
title: 送信ポート グループから送信ポートを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send port groups, deleting send ports
- managing [send port groups], deleting send ports
- managing [send ports], deleting send ports
- deleting, send ports
- send ports, deleting from send port groups
ms.assetid: a2289bfe-5bc9-4bc7-949c-5152ffb5bc62
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c9ab95b645d3bcdcef249de9b65fcf3891677d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335049"
---
# <a name="how-to-remove-a-send-port-from-a-send-port-group"></a>送信ポート グループから送信ポートを削除する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポート グループから送信ポートを削除する方法を説明します。 これを行うと、送信ポートは、アプリケーションまたは BizTalk 管理データベースから削除されません。  
  
 送信ポートを削除する前にこれは、停止または参加解除の状態に存在する必要があります。  
  
> [!NOTE]
>  メッセージをルーティングするには、送信ポート グループは、少なくとも 1 つの送信ポートを含める必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-remove-a-send-port-from-a-send-port-group"></a>送信ポート グループから送信ポートを削除するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループと、送信ポート グループから送信ポートを削除する BizTalk アプリケーションを展開します。  
  
3. クリックして**送信ポート グループ**送信ポート グループを右クリックし、クリックして**プロパティ**します。  
  
4. **名前**、してをクリックし、削除、送信ポートをクリックします。**削除**します。  
  
## <a name="see-also"></a>参照  
 [作成と送信ポート グループの構成](../core/creating-and-configuring-send-port-groups.md)   
 [送信ポートの作成および構成](../core/creating-and-configuring-send-ports.md)