---
title: サーバー グループを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, servers
- adding, servers
- managing [groups], adding servers
- servers, groups
- managing [servers], adding to groups
ms.assetid: 6eca1eeb-1a56-4470-b3bc-c64865cf6270
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8edccbd9bec7c4ef027b1e185e3af6e56a19340
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979371"
---
# <a name="how-to-add-a-server-to-a-group"></a>グループにサーバーを追加する方法
BizTalk Server 構成ウィザードを使用して、BizTalk グループにサーバーを追加できます。 BizTalk グループにサーバーを追加して、BizTalk Server 環境をスケール アウトします。  
  
 サーバーは、1 つの BizTalk グループに関連付けられた場合のみできます。 サーバーが別のグループに既に属している場合、まず現在のグループからサーバーを削除し、その後でサーバーを新しいグループに追加する必要があります。 BizTalk グループからサーバーを削除する方法の詳細については、次を参照してください。[グループからサーバーを削除する方法](../core/how-to-remove-a-server-from-a-group.md)します。  
  
> [!NOTE]
>  BizTalk Server 環境内の異なるサーバーに関連付けられた BizTalk グループどうしは、メッセージの交換以外の連携を行いません。  
  
> [!IMPORTANT]
>  BizTalk Server ランタイムは、BizTalk グループに追加するコンピューターにインストールする必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、SSO 管理者グループのメンバーおよび Windows 管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-add-a-server-to-a-biztalk-group"></a>サーバーを BizTalk グループに追加するには  
  
1. BizTalk Server グループに追加するコンピューターで次のようにクリックします**開始**、 をクリック**すべてのプログラム**、 をクリック[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 構成**.  
  
2. **Microsoft BizTalk Server 構成**、**カスタム構成**します。  
  
3. **データベース サーバー名**、BizTalk グループ、サーバーの参加先の SQL Server の名前を入力します。  
  
4. **サービス資格情報**、適切なユーザー名とサービスを使用し、パスワードを入力**構成**します。  
  
5. 画面の左側にあるナビゲーション ツリーで、クリックして**エンタープライズ SSO**します。  
  
6. **エンタープライズ シングル サインオン**] ページで [**既存の SSO システムに参加**します。  
  
    参加先 BizTalk Server グループのマスター SSO データベース サーバーに対する、適切なサーバー名およびデータベース名が指定されていることを確認してください。  
  
7. 画面の左側にあるナビゲーション ツリーで、クリックして**グループ**します。  
  
8. **グループ**] ページで [**既存の BizTalk グループに参加**します。  
  
    参加先 BizTalk Server グループのデータベースに対する、適切なサーバー名およびデータベース名が指定されていることを確認してください。  
  
9. メニュー バーでクリックして**構成の適用**このコンピューターでエンタープライズ シングル サインオンとグループの両方を構成します。  
  
## <a name="see-also"></a>参照  
 [構成フレームワークを使用した作業](../install-and-config-guides/working-with-the-configuration-framework.md)   
 [グループの管理](../core/managing-groups.md)   
 [BizTalk グループ](../core/biztalk-groups.md)   
 [1 つのグループからサーバーを移動する方法](../core/how-to-move-a-server-from-one-group-to-another.md)   
 [グループからサーバーを削除する方法](../core/how-to-remove-a-server-from-a-group.md)   
 [グループのプロパティを変更する方法](../core/how-to-modify-group-properties.md)   
 [サーバーの管理](../core/managing-servers.md)