---
title: "アプリケーションと BizTalk グループからポリシーを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deleting, policies
- managing [policies], applications
- managing [policies], deleting
- groups, policies
- managing [policies], groups
- applications, policies
ms.assetid: e9882cb3-8808-4258-a107-a24905290288
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4bb4b162d90811a4eddaa513556ecb1f6c6cd8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-a-policy-from-an-application-and-the-biztalk-group"></a>アプリケーションおよび BizTalk グループからポリシーを削除する方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、BizTalk グループのアプリケーションおよびルール エンジン データベースからポリシーを削除する方法を説明します。  
  
 ポリシーを削除する前に、次の点に注意してください。  
  
-   展開済みのポリシーは削除できません。 ポリシーを解除する必要があります最初[またはポリシーを展開解除方法](../core/how-to-deploy-or-undeploy-a-policy.md)です。 ポリシーは、展開解除すると非アクティブとなり、BizTalk グループ内でそれを使用しているすべてのアプリケーションで動作しなくなります。  
  
-   ポリシーを削除すると、ポリシーはルール データベースから削除されます。 このポリシーを再度使用する場合は、ポリシーを削除する前に .xml ファイルにインポートする必要があります。 手順については、次を参照してください。[ポリシーをエクスポートする方法](../core/how-to-export-a-policy.md)です。  
  
-   ポリシーが他のアプリケーションで使用されている場合、削除したポリシーはそのアプリケーションでも無効になります。 ポリシーを削除する前に、そのポリシーを参照している他のアプリケーションでポリシーを使用する必要がないか確認してください。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="to-remove-a-policy"></a>ポリシーを削除するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**、削除するには、ポリシーが含まれる BizTalk グループを展開し、ポリシーを含むアプリケーションを展開  
  
3.  をクリックして**ポリシー**ポリシーを右クリックし、クリックして**削除**です。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。  
  
2.  次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
     **BTSTask RemoveResource** [**/applicationname は:***値*] **/Luid:***値*[**/Server:***値*] [**/database:***値*]  
  
     例:  
  
     **BTSTask RemoveResource applicationname: myapplication/Luid:"Rule/Policy1/1.0"**  
  
    |パラメーター|Description|  
    |---------------|-----------------|  
    |**/ApplicationName**|削除するポリシーが存在する BizTalk アプリケーションの名前。 このパラメーターを指定しなかった場合、既定のアプリケーションが使用されます。|  
    |**/Luid**|ポリシーのローカル一意識別子 (LUID)。 使用して、LUID を取得することができます、 **ListApp**コマンドを」の説明に従って[ListApp コマンド](../core/listapp-command.md)です。|  
    |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前です。 Database パラメーターを指定する場合は必須です。 Server パラメーターおよび Database パラメーターを指定しなかった場合、グループの既定の BizTalk 管理データベースが使用されます。|  
    |**/データベース**|BizTalk 管理データベースの名前。 Server パラメーターを指定する場合は必須です。 Server パラメーターおよび Database パラメーターを指定しなかった場合、グループの既定の BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [ポリシーの管理](../core/managing-policies.md)