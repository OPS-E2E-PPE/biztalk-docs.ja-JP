---
title: BizTalk Server 管理者グループを管理する方法 |Microsoft Docs
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
ms.openlocfilehash: a7b22fff1ff8216021ba11038d5ee275f4dd0bb4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336712"
---
# <a name="how-to-manage-the-biztalk-server-administrators-group"></a>BizTalk Server 管理者グループを管理する方法
BizTalk Server 管理者グループは、管理タスクを実行するために必要最小限の特権を持ちます。 BizTalk Server 管理コンソールまたは WMI プロバイダーを使用して管理タスクを実行できるように、BizTalk Server 管理者グループにユーザーを追加します。 削除することもユーザー、BizTalk Server 管理者グループから、BizTalk Server 管理コンソールまたは WMI プロバイダーを使用して管理タスクを実行するが不要になったときにします。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行する管理者または Domain Admins グループのメンバーがあります。  
  
### <a name="to-add-users-to-the-local-biztalk-server-administrators-group"></a>ローカルの BizTalk Server 管理者グループにユーザーを追加するには  
  
1.  クリックして**開始**、 をポイント**管理ツール**、順にクリックします**コンピュータの管理**します。  
  
2.  展開**システム ツール**、展開**ローカル ユーザーとグループ**、 をクリックし、**グループ**フォルダー。 詳細ウィンドウで、フォルダーの内容が表示されます。  
  
3.  詳細ウィンドウで次のようにクリックします。 **BizTalk Server 管理者**します。  
  
4.  **アクション**メニューで、**すべてのタスク**、 をクリックし、**をグループに追加**。  
  
5.  **BizTalk Server 管理者のプロパティ**ダイアログ ボックスで、をクリックして**追加**します。  
  
6.  **検索**一覧で、ドメインまたはコンピューター名を選択します。  
  
7.  ユーザーおよびドメインまたは手順 6 で選択したコンピュータに関連付けられているコンピューターの一覧で、追加のユーザー アカウントを選択します。**追加**、 をクリックし、 **OK**。  
  
8.  クリックして**OK**を閉じる、 **BizTalk Server 管理者のプロパティ** ダイアログ ボックス。  
  
### <a name="to-remove-users-from-local-the-biztalk-server-administrators-group"></a>ローカルの BizTalk Server 管理者グループからユーザーを削除するには  
  
1.  クリックして**開始**、 をポイント**管理ツール**、順にクリックします**コンピュータの管理**します。  
  
2.  展開**システム ツール**、展開**ローカル ユーザーとグループ**、 をクリックし、**グループ**フォルダー。 詳細ウィンドウで、フォルダーの内容が表示されます。  
  
3.  詳細ウィンドウで次のようにクリックします。 **BizTalk Server 管理者**します。  
  
4.  **アクション** メニューのをクリックして**プロパティ**します。  
  
5.  **BizTalk Server 管理者のプロパティ** ダイアログ ボックスで、ユーザー アカウントをクリックして、削除する場合、select**削除**します。  
  
6.  **[OK]** をクリックします。  
  
### <a name="to-add-users-to-the-domain-biztalk-server-administrators-group"></a>ドメインの BizTalk Server 管理者グループにユーザーを追加するには  
  
1.  Domain Admins アカウントを使用して、SQL Server データベースが参加しているドメイン コント ローラーにログオンします。  
  
2.  クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**Active Directory ユーザーとコンピューター**に開始、 **Active Directory ユーザーとコンピューター**コンソール。  
  
    1.  コンソール ツリーで、メンバーを追加する BizTalk Server 管理者グループを含むフォルダーをクリックします。  
  
    2.  詳細ペインで、BizTalk Server 管理者グループを右クリックし、**プロパティ**します。  
  
    3.  **メンバー** ] タブで [**追加**します。  
  
    4.  **を選択するオブジェクト名の入力**、ユーザーの名前を入力し、クリックして**OK**します。  
  
### <a name="to-remove-users-from-the-domain-biztalk-server-administrators-group"></a>ユーザー ドメインの BizTalk Server 管理者グループから削除するには  
  
1.  ドメイン コント ローラーにログオンが SQL データベースは、Domain Admins アカウントを使用して結合されます。  
  
2.  クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**Active Directory ユーザーとコンピューター**に開始、 **Active Directory ユーザーとコンピューター**コンソール。  
  
    1.  コンソール ツリーで、メンバーを追加する BizTalk Server 管理者グループを含むフォルダーをクリックします。  
  
    2.  詳細ペインで、BizTalk Server 管理者グループを右クリックし、**プロパティ**します。  
  
    3.  **メンバー**  タブをクリックしてをクリックし、削除、削除するメンバー**削除**します。  
  
    4.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のセキュリティを管理します。](../core/managing-biztalk-server-security.md)   
 [ホストの管理とサービス アカウント](../core/managing-hosts-and-service-accounts.md)   
 [Windows グループとユーザー アカウントを管理するためのベスト プラクティス](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)   
 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)   
 [Windows ループおよびユーザー アカウントの管理](../core/managing-windows-groups-and-user-accounts.md)