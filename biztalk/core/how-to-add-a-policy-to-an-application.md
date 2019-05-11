---
title: アプリケーションにポリシーを追加する方法 |Microsoft Docs
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
ms.openlocfilehash: 01c67abd388f91e18072599e1697bde4acacaee8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387229"
---
# <a name="how-to-add-a-policy-to-an-application"></a>ポリシーをアプリケーションに追加する方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、BizTalk アプリケーションにポリシーを追加する方法について説明します。 管理コンソールを使用する場合は、一度に複数のポリシーを追加できます。 ポリシーをアプリケーションに追加すると、そのアプリケーションおよびそれを参照する他のアプリケーションでポリシーを使用できるようになります。  
  
 ポリシーをアプリケーションに追加する際には、次の点に注意してください。  
  
-   前に、ポリシーを追加するには、アプリケーションに、ポリシーは、BizTalk グループのルール エンジン データベースに存在する必要があります、必ずパブリッシュして、」の説明に従って[ポリシーをインポートする方法](../core/how-to-import-a-policy.md)します。  
  
    > [!NOTE]
    >  ルール エンジン展開ウィザードを使用してルール エンジン データベースからポリシーを削除すると、そのポリシーは、管理コンソールでは表示されたままになりますが、公開することはできません。 ルール エンジン展開ウィザードの詳細については、次を参照してください。[とボキャブラリを展開およびポリシーの展開を解除する方法](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)します。  
  
-   ポリシーは、BizTalk グループの別のアプリケーションに存在することはできません。  
  
    > [!IMPORTANT]
    >  複数のアプリケーションでポリシーを共有するには、ポリシーを格納する独立したアプリケーションを作成した後、そのポリシーを使用する別のアプリケーションからポリシーを格納するアプリケーションへの参照を作成する必要があります。 これは、ポリシーを含むアプリケーションを停止すると、ポリシーが自動的に展開解除され、ポリシーを使用するアプリケーションで機能しなくなるためです。 参照を追加する方法の詳細については、次を参照してください。[別のアプリケーションへの参照を追加する方法](../core/how-to-add-a-reference-to-another-application.md)します。  
  
-   ポリシーを有効にして機能させるには、ポリシーを展開する必要があります。 ポリシーは、アプリケーションの起動時に自動的に展開または手動で展開する」の説明に従って[展開またはポリシーを展開解除する方法](../core/how-to-deploy-or-undeploy-a-policy.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
## <a name="to-add-a-policy-to-an-application"></a>ポリシーをアプリケーションに追加するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで [[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、BizTalk グループの順に展開します。  
  
3. アプリケーションを展開し、アプリケーションのポリシーを追加し、右クリックする**ポリシー**します。  
  
4. をポイント**追加**クリック**ポリシー**します。  
  
5. 各ポリシーおよびクリックして、追加のバージョンのチェック ボックスをオン**OK**します。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1. 次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。  
  
2. 次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
    **BTSTask AddResource** [**/applicationname は:**<em>値</em>] **/Type:System.BizTalk:Rules** **[上書き]** **/Name:**<em>値</em>**/Version:**<em>値</em>[**/Server:**<em>値</em>] [**/Database:**<em>値</em>]  
  
   > [!NOTE]
   >  パラメーター値は大文字と小文字が区別されます。 パラメーター名では大文字と小文字が区別されません。 このコマンドを使ってポリシーをアプリケーションに追加した場合、ポリシーで使用されているボキャブラリもすべて自動的に追加されます。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
    例:  
  
    **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Rules /Overwrite /Name:MyPolicy /Version:1.0 /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
   |パラメーター|値|  
   |---------------|-----------|  
   |**/ApplicationName**|ポリシーを追加する BizTalk アプリケーションの名前。 アプリケーション名が指定されなかった場合、グループの既定の BizTalk アプリケーションが使用されます。 スペースが含まれる名前は、二重引用符 (") で囲む必要があります。|  
   |**/Type**|**System.BizTalk:Rules**|  
   |**/Overwrite**|既存のポリシーを更新するためのオプション。 指定しなかった場合、追加するポリシーと同じ名前のポリシーが既にアプリケーションに存在した場合、AddResource 操作は失敗します。|  
   |**/Name**|ポリシーの名前。|  
   |**/Version**|ポリシーのバージョン番号です。|  
   |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前です。 Database パラメーターを指定する場合は必須です。 Server パラメーターおよび Database パラメーターを指定しなかった場合、グループの既定の BizTalk 管理データベースが使用されます。|  
   |**/Database**|BizTalk 管理データベースの名前。 Server パラメーターを指定する場合は必須です。 Server パラメーターおよび Database パラメーターを指定しなかった場合、グループの既定の BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [ポリシーの管理](../core/managing-policies.md)   
 [作成して、BizTalk アプリケーションの変更](../core/creating-and-modifying-biztalk-applications.md)   
 [AddResource コマンド:ポリシー](../core/addresource-command-policy.md)