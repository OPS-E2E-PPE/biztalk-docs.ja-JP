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
ms.openlocfilehash: 6ce54faf09b45a46d2ac5150e1c2bbbe88c8ccac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018925"
---
# <a name="how-to-remove-a-send-port-from-a-send-port-group"></a>送信ポート グループから送信ポートを削除する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポート グループから特定の送信ポートを削除する方法について説明します。 送信ポートを送信ポート グループから削除しても、アプリケーションや BizTalk 管理データベースからは削除されません。  
  
 削除する送信ポートは、あらかじめ停止状態または参加解除状態にしておく必要があります。  
  
> [!NOTE]
>  メッセージをルーティングするには、送信ポート グループは、少なくとも 1 つの送信ポートを含める必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-remove-a-send-port-from-a-send-port-group"></a>送信ポート グループから送信ポートを削除するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループを展開し、送信ポート グループから送信ポートを削除する BizTalk アプリケーションを展開します。  
  
3. クリックして**送信ポート グループ**送信ポート グループを右クリックし、クリックして**プロパティ**します。  
  
4. **名前**、してをクリックし、削除、送信ポートをクリックします。**削除**します。  
  
## <a name="see-also"></a>参照  
 [作成と送信ポート グループの構成](../core/creating-and-configuring-send-port-groups.md)   
 [送信ポートの作成および構成](../core/creating-and-configuring-send-ports.md)