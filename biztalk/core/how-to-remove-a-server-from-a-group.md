---
title: グループからサーバーを削除する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, servers
- managing [groups], deleting servers
- servers, deleting
- deleting, groups
- servers
- managing [servers], deleting from groups
- groups, deleting
- servers, groups
- deleting, servers
ms.assetid: 85596e18-fa17-4f44-bc20-2e4cb578e109
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b69eb694da320e598c7d0cfe5a03d58e0a723a8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255386"
---
# <a name="how-to-remove-a-server-from-a-group"></a>サーバーをグループから削除する方法
サーバーは、1 つの BizTalk グループに関連付けられたのみできます。 サーバーが別のグループに既に属している場合、まず現在のグループからサーバーを削除し、その後でサーバーを新しいグループに追加する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、Windows 管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-remove-a-server-from-a-group"></a>サーバーをグループから削除するには  
  
1.  BizTalk Server グループから削除するコンピューター、をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalkServerの構成**.  
  
2.  メニュー バーで、をクリックして**機能の構成解除**です。  
  
3.  **機能の構成解除**ダイアログ ボックスで、**グループ**、順にクリック**OK**です。  
  
    > [!CAUTION]
    >  グループの構成を解除すると、そのコンピューターで既に構成されているすべての依存機能の構成が解除されます。  
  
4.  **[はい]** をクリックします。  
  
5.  Microsoft BizTalk Server 構成ウィザードでクリックして**次**です。  
  
     グループ、および、そのグループに依存する機能の構成が解除されます。  
  
6.  **[完了]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [グループを管理します。](../core/managing-groups.md)   
 [BizTalk グループ](../core/biztalk-groups.md)   
 [サーバー グループを追加する方法](../core/how-to-add-a-server-to-a-group.md)   
 [1 つのグループからサーバーを移動する方法](../core/how-to-move-a-server-from-one-group-to-another.md)   
 [グループのプロパティを変更する方法](../core/how-to-modify-group-properties.md)   
 [サーバーを管理します。](../core/managing-servers.md)