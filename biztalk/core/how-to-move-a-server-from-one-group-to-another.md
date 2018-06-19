---
title: 1 つのグループからサーバーを移動する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 1c9e5dfdf266d2205283afa7cd9804c31fc93ff3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254570"
---
# <a name="how-to-move-a-server-from-one-group-to-another"></a>サーバーをあるグループから別のグループに移動する方法
1 つの BizTalk Server グループに関連付けることができるサーバーは 1 つだけです。 サーバーをあるグループから別のグループに移動するには、まず元のグループの構成を解除してそのグループからサーバーを削除したうえで、新しいグループに追加する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、SSO 管理者グループのメンバーおよび Windows 管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-move-a-server-from-one-biztalk-group-to-another"></a>サーバーをあるサーバーから別の BizTalk グループに移動するには  
  
1.  BizTalk グループから別に移動するコンピューターでをクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalkServer構成**.  
  
2.  メニュー バーで、をクリックして**機能の構成解除**です。  
  
3.  **機能の構成解除**ダイアログ ボックスで、**エンタープライズ SSO**を選択**グループ**、順にクリック**OK**です。  
  
    > [!CAUTION]
    >  グループの構成を解除すると、そのコンピューターで既に構成されているすべての依存機能の構成が解除されます。  
  
4.  **[はい]** をクリックします。  
  
5.  **Microsoft BizTalk Server 構成**ウィンドウで、をクリックして**次**です。  
  
     エンタープライズ SSO、グループ、および、それらに依存する機能の構成が解除されます。  
  
6.  **[完了]** をクリックします。  
  
7.  **Microsoft BizTalk Server 構成**ウィンドウで、**カスタム構成**です。  
  
8.  **データベース サーバー名**サーバーを移動する、BizTalk グループの SQL server の名前を入力します。  
  
9. **サービス資格情報**、適切なユーザー名とサービスを使用し、パスワードを入力**構成**です。  
  
10. 画面の左側にあるナビゲーション ツリーで、クリックして**エンタープライズ SSO**です。  
  
11. **エンタープライズ シングル サインオン**] ページで [**既存の SSO システムに参加**です。  
  
     移動先 BizTalk Server グループのマスター SSO データベース サーバーに対する、適切なサーバー名およびデータベース名が指定されていることを確認してください。  
  
12. 画面の左側にあるナビゲーション ツリーで、クリックして**グループ**です。  
  
13. **グループ**] ページで [**既存の BizTalk グループに参加**です。  
  
     移動先 BizTalk Server グループのデータベースに対する、適切なサーバー名およびデータベース名が指定されていることを確認してください。  
  
14. メニュー バーで、をクリックして**構成の適用**をこのコンピューターでエンタープライズ シングル サインオンとグループの両方を構成します。  
  
## <a name="see-also"></a>参照  
 [グループを管理します。](../core/managing-groups.md)   
 [BizTalk グループ](../core/biztalk-groups.md)   
 [サーバー グループを追加する方法](../core/how-to-add-a-server-to-a-group.md)   
 [グループからサーバーを削除する方法](../core/how-to-remove-a-server-from-a-group.md)   
 [グループのプロパティを変更する方法](../core/how-to-modify-group-properties.md)   
 [構成フレームワークを使用した作業](../install-and-config-guides/working-with-the-configuration-framework.md)   
 [ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md)   
 [サーバーを管理します。](../core/managing-servers.md)