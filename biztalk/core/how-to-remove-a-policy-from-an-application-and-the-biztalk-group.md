---
title: アプリケーションおよび BizTalk グループからポリシーを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, policies
- managing [policies], applications
- managing [policies], deleting
- groups, policies
- managing [policies], groups
- applications, policies
ms.assetid: e9882cb3-8808-4258-a107-a24905290288
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d555549e693ed6cc5f8ab972008c76e236ee863
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001355"
---
# <a name="how-to-remove-a-policy-from-an-application-and-the-biztalk-group"></a>アプリケーションおよび BizTalk グループからポリシーを削除する方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、BizTalk グループのアプリケーションおよびルール エンジン データベースからポリシーを削除する方法を説明します。  
  
 ポリシーを削除する前に、次の点に注意してください。  
  
-   展開済みのポリシーは削除できません。 ポリシーを解除する必要がありますまず[展開またはポリシーを展開解除する方法](../core/how-to-deploy-or-undeploy-a-policy.md)します。 ポリシーは、展開解除すると非アクティブとなり、BizTalk グループ内でそれを使用しているすべてのアプリケーションで動作しなくなります。  
  
-   ポリシーを削除すると、ポリシーはルール データベースから削除されます。 このポリシーを再度使用する場合は、ポリシーを削除する前に .xml ファイルにインポートする必要があります。 手順については、[ポリシーをエクスポートする方法](../core/how-to-export-a-policy.md)を参照してください。  
  
-   ポリシーが他のアプリケーションで使用されている場合、削除したポリシーはそのアプリケーションでも無効になります。 ポリシーを削除する前に、そのポリシーを参照している他のアプリケーションでポリシーを使用する必要がないか確認してください。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
## <a name="to-remove-a-policy"></a>ポリシーを削除するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**、削除するには、ポリシーが含まれる BizTalk グループを展開し、ポリシーを含むアプリケーションを展開  
  
3. クリックして**ポリシー**ポリシーを右クリックし、クリックして**削除**します。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1. 次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。  
  
2. 次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
    **BTSTask RemoveResource** [**/applicationname は:**<em>値</em>] **/Luid:**<em>値</em>[**/Server:** <em>値</em>] [**/database:**<em>値</em>]  
  
    例:  
  
    **BTSTask RemoveResource applicationname: myapplication/Luid:"Rule/Policy1/1.0"**  
  
   |パラメーター|説明|  
   |---------------|-----------------|  
   |**/ApplicationName**|削除するポリシーが存在する BizTalk アプリケーションの名前。 このパラメーターを指定しなかった場合、既定のアプリケーションが使用されます。|  
   |**/Luid**|ポリシーのローカル一意識別子 (LUID)。 LUID を取得するにを使用して、 **ListApp** 」の説明に従って、コマンド[ListApp コマンド](../core/listapp-command.md)します。|  
   |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前です。 Database パラメーターを指定する場合は必須です。 Server パラメーターおよび Database パラメーターを指定しなかった場合、グループの既定の BizTalk 管理データベースが使用されます。|  
   |**/データベース**|BizTalk 管理データベースの名前。 Server パラメーターを指定する場合は必須です。 Server パラメーターおよび Database パラメーターを指定しなかった場合、グループの既定の BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [ポリシーの管理](../core/managing-policies.md)