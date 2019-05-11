---
title: 1 つのグループからサーバーを移動する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, servers
- groups, moving
- managing [groups], moving servers
- servers, moving
- managing [servers], moving
- servers, groups
ms.assetid: 3f789a62-f597-426b-9cea-74c1fe22b694
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3ef92cecddc32915a194cd5058e7337511ab609
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335953"
---
# <a name="how-to-move-a-server-from-one-group-to-another"></a>サーバーをあるグループから別のグループに移動する方法
サーバーは、1 つの BizTalk Server グループに関連付けられた場合のみできます。 サーバーを別の 1 つのグループに移動するには、最初に、構成を解除して、元のグループからサーバーを削除し、新しいグループにサーバーを追加する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、SSO 管理者グループのメンバーおよび Windows 管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-move-a-server-from-one-biztalk-group-to-another"></a>別の 1 つの BizTalk グループからサーバーを移動するには  
  
1. を別の BizTalk グループから移動するコンピューターに次のようにクリックします。**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリックし、 **BizTalkServerの構成**.  
  
2. メニュー バーでクリックして**機能の構成解除**します。  
  
3. **機能の構成解除**ダイアログ ボックスで、**エンタープライズ SSO**を選択します**グループ**、順にクリックします**OK**します。  
  
   > [!CAUTION]
   >  グループを構成解除のコンピューターに既に構成されているすべての依存機能構成が解除されます。  
  
4. **[はい]** をクリックします。  
  
5. **Microsoft BizTalk Server 構成**ウィンドウで、をクリックして**次**します。  
  
    エンタープライズ SSO、グループ、および、依存する機能では、構成されています。  
  
6. **[完了]** をクリックします。  
  
7. **Microsoft BizTalk Server 構成**ウィンドウで、**カスタム構成**します。  
  
8. **データベース サーバー名**サーバーを移動する、BizTalk グループの SQL server の名前を入力します。  
  
9. **サービス資格情報**、適切なユーザー名とサービスを使用し、パスワードを入力**構成**します。  
  
10. 画面の左側にあるナビゲーション ツリーで、クリックして**エンタープライズ SSO**します。  
  
11. **エンタープライズ シングル サインオン**] ページで [**既存の SSO システムに参加**します。  
  
     サーバー名とデータベース名を指している BizTalk Server グループのマスター SSO データベース サーバー、サーバーを移動することを確認します。  
  
12. 画面の左側にあるナビゲーション ツリーで、クリックして**グループ**します。  
  
13. **グループ**] ページで [**既存の BizTalk グループに参加**します。  
  
     サーバー名とデータベース名を指す BizTalk Server グループのデータベース サーバーを移動することを確認します。  
  
14. メニュー バーでクリックして**構成の適用**このコンピューターでエンタープライズ シングル サインオンとグループの両方を構成します。  
  
## <a name="see-also"></a>参照  
 [グループの管理](../core/managing-groups.md)   
 [BizTalk グループ](../core/biztalk-groups.md)   
 [サーバー グループを追加する方法](../core/how-to-add-a-server-to-a-group.md)   
 [グループからサーバーを削除する方法](../core/how-to-remove-a-server-from-a-group.md)   
 [グループのプロパティを変更する方法](../core/how-to-modify-group-properties.md)   
 [構成フレームワークを使用した作業](../install-and-config-guides/working-with-the-configuration-framework.md)   
 [ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md)   
 [サーバーの管理](../core/managing-servers.md)