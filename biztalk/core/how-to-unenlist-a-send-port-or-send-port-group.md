---
title: 送信ポートまたは送信ポート グループを参加解除する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- unenlisting, send port groups
- send port groups, unenlisting
- managing [send ports], unenlisting
- managing [send port groups], unenlisting
- unenlisting, send ports
- send ports, unenlisting
ms.assetid: 3185adad-2efa-4abd-a532-77ae6c7b4c1d
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac2599ae3d06a75506de244a4f996a9e77cef6ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256674"
---
# <a name="how-to-unenlist-a-send-port-or-send-port-group"></a>送信ポートまたは送信ポート グループを参加解除する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートまたは送信ポート グループを参加解除する方法について説明します。 送信ポートまたは送信ポート グループを参加解除すると、そこに関連付けられていたすべてのサブスクリプションが削除されます。 送信ポートまたは送信ポート グループは、実行中であるか停止されているかに関係なく参加解除できます。 参加解除された送信ポートまたは送信ポート グループは自動的に停止されます。  
  
 送信ポートまたは送信ポート グループの参加解除が必要になる状況としては、バインドを編集したい場合や、送信ポートまたは送信ポート グループを BizTalk Server 環境から削除したい場合などが考えられます。  
  
 実行中または参加済みの送信ポート グループに対して最後に参加させた送信ポートを参加解除することはできません。 送信ポート グループを参加解除しても、そのグループに属する各送信ポートの状態は変わりません。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-unenlist-a-send-port-or-send-port-group"></a>送信ポートまたは送信ポート グループを参加解除するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**アプリケーション**、し、送信ポートまたはする送信ポート グループを含むアプリケーションを展開参加を解除します。  
  
3.  をクリックして**送信ポート**または**送信ポート グループ**送信ポートまたは送信ポート グループを右クリックし、クリックして**参加解除**です。  
  
## <a name="see-also"></a>参照  
 [送信ポートと送信ポート グループの管理](../core/managing-send-ports-and-send-port-groups.md)