---
title: 送信ポートまたは送信ポート グループを参加解除する方法 |Microsoft Docs
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
ms.openlocfilehash: ee33b2ea9711b19e23067b164ecef9084541ba87
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967747"
---
# <a name="how-to-unenlist-a-send-port-or-send-port-group"></a>送信ポートまたは送信ポート グループを参加解除する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートまたは送信ポート グループを参加解除する方法について説明します。 送信ポートまたは送信ポート グループを参加解除すると、そこに関連付けられていたすべてのサブスクリプションが削除されます。 送信ポートまたは送信ポート グループは、実行中であるか停止されているかに関係なく参加解除できます。 参加解除された送信ポートまたは送信ポート グループは自動的に停止されます。  
  
 送信ポートまたは送信ポート グループの参加解除が必要になる状況としては、バインドを編集したい場合や、送信ポートまたは送信ポート グループを BizTalk Server 環境から削除したい場合などが考えられます。  
  
 実行中または参加済みの送信ポート グループに対して最後に参加させた送信ポートを参加解除することはできません。 送信ポート グループを参加解除しても、そのグループに属する各送信ポートの状態は変わりません。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-unenlist-a-send-port-or-send-port-group"></a>送信ポートまたは送信ポート グループを参加解除するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**アプリケーション**、送信ポートまたは送信ポート グループにするを含むアプリケーションを展開し、参加を解除します。  
  
3. クリックして**送信ポート**または**送信ポート グループ**送信ポートまたは送信ポート グループを右クリックし、クリックして**参加解除**します。  
  
## <a name="see-also"></a>参照  
 [送信ポートと送信ポート グループの管理](../core/managing-send-ports-and-send-port-groups.md)