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
ms.openlocfilehash: 7dbd8a3a7c3450fcf36d66467cd95a38e39583dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333777"
---
# <a name="how-to-unenlist-a-send-port-or-send-port-group"></a>送信ポートまたは送信ポート グループを参加解除する方法
このトピックでは、送信ポートを参加解除、または送信ポート グループを BizTalk Server 管理コンソールを使用する方法について説明します。 送信ポートまたは送信ポート グループを参加解除、その送信ポートに関連付けられているすべてのサブスクリプションを排除または送信ポート グループ。 実行中と停止の両方の送信ポートの参加を解除したり、送信ポート グループができます。 送信ポートまたは送信ポート グループを自動的に参加解除するには、そのは停止します。  
  
 送信ポートを参加解除、または送信ポート グループ、そのバインドを編集したいなどのポートまたは送信ポート グループを BizTalk Server 環境からの送信を削除するかどうかまたはします。  
  
 参加しているまたは実行中である送信ポート グループ内の最後の参加させた送信ポートを参加解除することはできません。 送信ポート グループを参加解除しても、それに含まれる送信ポートの状態は変わりません。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-unenlist-a-send-port-or-send-port-group"></a>送信ポートを参加解除または送信ポート グループ  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**アプリケーション**、送信ポートまたは送信ポート グループにするを含むアプリケーションを展開し、参加を解除します。  
  
3. クリックして**送信ポート**または**送信ポート グループ**送信ポートまたは送信ポート グループを右クリックし、クリックして**参加解除**します。  
  
## <a name="see-also"></a>参照  
 [送信ポートと送信ポート グループの管理](../core/managing-send-ports-and-send-port-groups.md)