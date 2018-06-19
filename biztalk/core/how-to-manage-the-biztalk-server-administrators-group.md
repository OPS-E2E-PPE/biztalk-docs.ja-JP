---
title: BizTalk Server 管理者グループを管理する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Administrators group, user accounts
- BizTalk Administrators group
- user accounts, BizTalk Administrators group
- Windows Management Instrumentation (WMI), administering
- BizTalk Administrators group, privileges
- security, BizTalk Administrators group
- Administration Console [BizTalk Server], security
- Administration Console [BizTalk Server], administering
- BizTalk Administrators group, about BizTalk Administrators group
ms.assetid: 60ea689b-0b93-4fcc-b49c-6436e7be473f
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fe92c9c43ccef242d8c14b5f1aa48e0b1a8d852
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254754"
---
# <a name="how-to-manage-the-biztalk-server-administrators-group"></a>BizTalk Server 管理者グループを管理する方法
BizTalk Server 管理者グループには、管理タスクの実行に最低限必要な権限が割り当てられています。 BizTalk Server 管理コンソールまたは WMI プロバイダを使用して管理タスクを実行できるようにするには、ユーザーを BizTalk Server 管理者グループに追加します。 また、BizTalk Server 管理コンソールまたは WMI プロバイダを使用して管理タスクを実行する必要がなくなった場合は、ユーザーを BizTalk Server 管理者グループから削除します。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、管理者グループまたはドメイン管理者グループのメンバである必要があります。  
  
### <a name="to-add-users-to-the-local-biztalk-server-administrators-group"></a>ユーザーをローカルの BizTalk Server 管理者グループに追加するには  
  
1.  をクリックして**開始**、 をポイント**管理ツール**、順にクリック**コンピューターの管理**です。  
  
2.  展開**システム ツール**、展開**ローカル ユーザーとグループ**、をクリックし、**グループ**フォルダーです。 フォルダの内容が詳細ペインに表示されます。  
  
3.  詳細ペインでクリックして**BizTalk Server 管理者**です。  
  
4.  **アクション** メニューのをポイント**すべてのタスク**、クリックして**グループに追加**です。  
  
5.  **BizTalk Server 管理者のプロパティ**ダイアログ ボックスで、をクリックして**追加**です。  
  
6.  **ファイルの場所**一覧で、ドメインまたはコンピューター名を選択します。  
  
7.  一覧で、ユーザーとコンピューターのドメインまたは手順 6 で選択したコンピューターに関連付けられているを含む、選択は、追加するユーザー アカウント**追加**、クリックして**OK**です。  
  
8.  をクリックして**OK**を閉じる、 **BizTalk Server 管理者のプロパティ** ダイアログ ボックス。  
  
### <a name="to-remove-users-from-local-the-biztalk-server-administrators-group"></a>ユーザーをローカルの BizTalk Server 管理者グループから削除するには  
  
1.  をクリックして**開始**、 をポイント**管理ツール**、順にクリック**コンピューターの管理**です。  
  
2.  展開**システム ツール**、展開**ローカル ユーザーとグループ**、をクリックし、**グループ**フォルダーです。 フォルダの内容が詳細ペインに表示されます。  
  
3.  詳細ペインでクリックして**BizTalk Server 管理者**です。  
  
4.  **アクション** メニューのをクリックして**プロパティ**です。  
  
5.  **BizTalk Server 管理者のプロパティ** ダイアログ ボックスで、ユーザー アカウントをクリックして、削除する**削除**です。  
  
6.  **[OK]** をクリックします。  
  
### <a name="to-add-users-to-the-domain-biztalk-server-administrators-group"></a>ユーザーをドメインの BizTalk Server 管理者グループに追加するには  
  
1.  ドメイン管理者アカウントを使用して SQL Server データベースが参加しているドメイン コントローラにログオンします。  
  
2.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリック**Active Directory ユーザーとコンピューター**に開始、 **Active Directory ユーザーとコンピューター**コンソールです。  
  
    1.  コンソール ツリーで、メンバを追加するフォルダとして、BizTalk Server 管理者グループを含むフォルダを展開します。  
  
    2.  詳細ウィンドウで、BizTalk Server 管理者グループを右クリックし、をクリックして**プロパティ**です。  
  
    3.  **メンバー**  タブで、をクリックして**追加**です。  
  
    4.  **を選択するオブジェクト名の入力**、ユーザーの名前を入力して、をクリックして**OK**です。  
  
### <a name="to-remove-users-from-the-domain-biztalk-server-administrators-group"></a>ユーザー ドメインの BizTalk Server 管理者グループから削除するには  
  
1.  ドメイン管理者アカウントを使用して SQL データベースが参加しているドメイン コントローラにログオンします。  
  
2.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリック**Active Directory ユーザーとコンピューター**に開始、 **Active Directory ユーザーとコンピューター**コンソールです。  
  
    1.  コンソール ツリーで、メンバを追加するフォルダとして、BizTalk Server 管理者グループを含むフォルダを展開します。  
  
    2.  詳細ウィンドウで、BizTalk Server 管理者グループを右クリックし、をクリックして**プロパティ**です。  
  
    3.  **メンバー**  タブで、削除、およびをクリックするメンバーをクリックして**削除**です。  
  
    4.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のセキュリティを管理します。](../core/managing-biztalk-server-security.md)   
 [管理ホストおよびサービス アカウント](../core/managing-hosts-and-service-accounts.md)   
 [Windows グループとユーザー アカウントを管理するためのベスト プラクティス](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)   
 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)   
 [Windows グループおよびユーザー アカウントの管理](../core/managing-windows-groups-and-user-accounts.md)