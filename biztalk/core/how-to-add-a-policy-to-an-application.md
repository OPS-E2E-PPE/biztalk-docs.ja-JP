---
title: アプリケーションにポリシーを追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [policies], adding to applications
- policies, applications
- applications, policies
- policies, adding to applications
ms.assetid: 93b3ce5e-8c63-4c64-9bdc-1747541ba9a8
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ad9eaf1e2f14e51e60ad3f18e31cdaa72fa906a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248106"
---
# <a name="how-to-add-a-policy-to-an-application"></a>ポリシーをアプリケーションに追加する方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、BizTalk アプリケーションにポリシーを追加する方法について説明します。 管理コンソールを使用する場合は、一度に複数のポリシーを追加できます。 ポリシーをアプリケーションに追加すると、そのアプリケーションおよびそれを参照する他のアプリケーションでポリシーを使用できるようになります。  
  
 ポリシーをアプリケーションに追加する際には、次の点に注意してください。  
  
-   前に、ポリシーを追加するには、アプリケーションに、ポリシーが BizTalk グループのルール エンジン データベースに存在する必要があります発行して、」の説明に従って[ポリシーをインポートする方法](../core/how-to-import-a-policy.md)です。  
  
    > [!NOTE]
    >  ルール エンジン展開ウィザードを使用してルール エンジン データベースからポリシーを削除すると、そのポリシーは、管理コンソールでは表示されたままになりますが、公開することはできません。 ルール エンジン展開ウィザードの詳細については、次を参照してください。[展開と展開解除ポリシーとボキャブラリを方法](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)です。  
  
-   ポリシーは、BizTalk グループの別のアプリケーションに存在することはできません。  
  
    > [!IMPORTANT]
    >  複数のアプリケーションでポリシーを共有するには、ポリシーを格納する独立したアプリケーションを作成した後、そのポリシーを使用する別のアプリケーションからポリシーを格納するアプリケーションへの参照を作成する必要があります。 これは、ポリシーを含むアプリケーションを停止すると、ポリシーが自動的に展開解除され、ポリシーを使用するアプリケーションで機能しなくなるためです。 参照を追加する方法の詳細については、次を参照してください。[を別のアプリケーションへの参照を追加する方法](../core/how-to-add-a-reference-to-another-application.md)です。  
  
-   ポリシーを有効にして機能させるには、ポリシーを展開する必要があります。 ポリシーは、アプリケーションの起動時に自動的に展開または手動で展開する」の説明に従って[またはポリシーを展開解除方法](../core/how-to-deploy-or-undeploy-a-policy.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="to-add-a-policy-to-an-application"></a>ポリシーをアプリケーションに追加するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで [[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、BizTalk グループの順に展開します。  
  
3.  アプリケーションを展開し、ポリシーを追加し、右クリックするアプリケーション**ポリシー**です。  
  
4.  指す**追加** をクリック**ポリシー**です。  
  
5.  各ポリシーおよびをクリックし、追加のバージョンのチェック ボックスをオン**OK**です。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。  
  
2.  次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
     **BTSTask AddResource** [**/applicationname は:***値*] **/Type:System.BizTalk:Rules** [**上書き**] **/名:***値***/Version:***値*[**/Server:***値*] [**/Database:***値*]  
  
    > [!NOTE]
    >  パラメーター値は大文字と小文字が区別されます。 パラメーター名では大文字と小文字が区別されません。 このコマンドを使ってポリシーをアプリケーションに追加した場合、ポリシーで使用されているボキャブラリもすべて自動的に追加されます。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
     例:  
  
     **BTSTask AddResource applicationname: myapplication/Type:System.BizTalk:Rules/overwrite/Name:MyPolicy/Version:1.0/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |**/ApplicationName**|ポリシーを追加する BizTalk アプリケーションの名前。 アプリケーション名が指定されなかった場合、グループの既定の BizTalk アプリケーションが使用されます。 スペースが含まれる名前は、二重引用符 (") で囲む必要があります。|  
    |**/型**|**System.BizTalk:Rules**|  
    |**/上書き**|既存のポリシーを更新するためのオプション。 指定しなかった場合、追加するポリシーと同じ名前のポリシーが既にアプリケーションに存在した場合、AddResource 操作は失敗します。|  
    |**/名前**|ポリシーの名前。|  
    |**/バージョン**|ポリシーのバージョン番号です。|  
    |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前です。 Database パラメーターを指定する場合は必須です。 Server パラメーターおよび Database パラメーターを指定しなかった場合、グループの既定の BizTalk 管理データベースが使用されます。|  
    |**/データベース**|BizTalk 管理データベースの名前。 Server パラメーターを指定する場合は必須です。 Server パラメーターおよび Database パラメーターを指定しなかった場合、グループの既定の BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [ポリシーの管理](../core/managing-policies.md)   
 [作成して、BizTalk アプリケーションの変更](../core/creating-and-modifying-biztalk-applications.md)   
 [AddResource コマンド: ポリシー](../core/addresource-command-policy.md)