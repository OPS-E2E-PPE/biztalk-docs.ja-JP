---
title: 送信ポート グループから送信ポートを削除する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: d109064a1286bcd622479a4075ef2d23dc8d320c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254522"
---
# <a name="how-to-remove-a-send-port-from-a-send-port-group"></a>送信ポート グループから送信ポートを削除する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポート グループから特定の送信ポートを削除する方法について説明します。 送信ポートを送信ポート グループから削除しても、アプリケーションや BizTalk 管理データベースからは削除されません。  
  
 削除する送信ポートは、あらかじめ停止状態または参加解除状態にしておく必要があります。  
  
> [!NOTE]
>  メッセージをルーティングするには、送信ポート グループは、少なくとも 1 つの送信ポートを含める必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-remove-a-send-port-from-a-send-port-group"></a>送信ポート グループから送信ポートを削除するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポート グループから送信ポートを削除する BizTalk アプリケーションを展開します。  
  
3.  をクリックして**送信ポート グループ**送信ポート グループを右クリックし、クリックして**プロパティ**です。  
  
4.  **名前**をクリックしてをクリックし、削除、送信ポート**削除**です。  
  
## <a name="see-also"></a>参照  
 [作成して、送信ポート グループを構成します。](../core/creating-and-configuring-send-port-groups.md)   
 [作成して、送信ポートの構成](../core/creating-and-configuring-send-ports.md)