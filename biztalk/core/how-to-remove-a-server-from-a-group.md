---
title: グループからサーバーを削除する方法 |Microsoft Docs
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
ms.openlocfilehash: 19c4381f7ca011698aa647f0d7a4a7ccf9ca91a4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017629"
---
# <a name="how-to-remove-a-server-from-a-group"></a>サーバーをグループから削除する方法
サーバーは、1 つの BizTalk グループに関連付けられた場合のみできます。 サーバーが別のグループに既に属している場合、まず現在のグループからサーバーを削除し、その後でサーバーを新しいグループに追加する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、Windows 管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-remove-a-server-from-a-group"></a>サーバーをグループから削除するには  
  
1. BizTalk Server グループから削除するコンピューターで次のようにクリックします**開始**、 をクリック**すべてのプログラム**、 をクリック[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalkServerの構成。**.  
  
2. メニュー バーでクリックして**機能の構成解除**します。  
  
3. **機能の構成解除**ダイアログ ボックスで、**グループ**、 をクリックし、 **OK**。  
  
   > [!CAUTION]
   >  グループの構成を解除すると、そのコンピューターで既に構成されているすべての依存機能の構成が解除されます。  
  
4. **[はい]** をクリックします。  
  
5. Microsoft BizTalk Server 構成ウィザードで次のようにクリックします。**次**します。  
  
    グループ、および、そのグループに依存する機能の構成が解除されます。  
  
6. **[完了]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [グループの管理](../core/managing-groups.md)   
 [BizTalk グループ](../core/biztalk-groups.md)   
 [サーバー グループを追加する方法](../core/how-to-add-a-server-to-a-group.md)   
 [1 つのグループからサーバーを移動する方法](../core/how-to-move-a-server-from-one-group-to-another.md)   
 [グループのプロパティを変更する方法](../core/how-to-modify-group-properties.md)   
 [サーバーの管理](../core/managing-servers.md)