---
title: オーケストレーションをアプリケーションから削除する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, orchestrations
- deleting, orchestrations
- managing [orchestrations], deleting
- orchestrations, applications
- orchestrations, deleting
ms.assetid: e6d635ea-3513-42de-a667-b56c536e5328
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef4909f5430ae2d0435d519823abe9735cbc1cc4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255194"
---
# <a name="how-to-remove-an-orchestration-from-an-application"></a>オーケストレーションをアプリケーションから削除する方法
ここでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、オーケストレーションを BizTalk アプリケーションから削除する方法について説明します。 オーケストレーションをアプリケーションから削除すると、BizTalk グループの BizTalk 管理データベースからも削除されます。  
  
 オーケストレーションを削除すると、次の処理が行われます。  
  
-   オーケストレーションが BizTalk 管理データベースから削除されます。  
  
-   オーケストレーションを含む BizTalk アセンブリも BizTalk 管理データベースから削除されますが、ローカル ファイル システムまたはグローバル アセンブリ キャッシュ (GAC) 内に存在する場合、そのアセンブリは削除されません。  
  
-   削除する BizTalk アセンブリ、アセンブリに含まれるすべてのアイテムは BizTalk 管理データベースから削除されます。  
  
 オーケストレーションをアプリケーションから削除する前に、次の重要事項を考慮します。  
  
-   他のアイテムがこのオーケストレーションに依存関係を持っている場合、または削除されるアセンブリに含まれるアイテムに依存関係を持っている場合は、オーケストレーションを削除するとアイテムが適切に動作しなくなります。 依存関係に関する背景情報については、次を参照してください。[の依存関係とアプリケーションの配置](../core/dependencies-and-application-deployment.md)です。  
  
-   実行中のインスタンスを含むオーケストレーションは削除できません。 実行中のインスタンスはすべて終了する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="to-remove-an-orchestration-from-an-application"></a>オーケストレーションをアプリケーションから削除するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**アプリケーション**、し、削除するオーケストレーションを含むアプリケーションを展開します。  
  
3.  をクリックして**オーケストレーション**、オーケストレーションを右クリックし、クリックして**参加解除**です。  
  
4.  オーケストレーションを選択して、順にポイント**ビュー**、クリックして**インスタンス情報**です。  
  
5.  クエリ結果ウィンドウで、オーケストレーション インスタンスを右クリックし、をクリックして**Terminate**です。  
  
    > [!NOTE]
    >  参加解除、インスタンス、実行を終了および停止できますすべてのアプリケーションでオーケストレーションを一度に、アプリケーションの完全停止 オプションを使用して、」の説明に従って[起動し、BizTalk アプリケーションを停止する方法](../core/how-to-start-and-stop-a-biztalk-application.md)です。  
  
6.  をクリックして**オーケストレーション**、オーケストレーションを右クリックし、クリックして**削除**です。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。  
  
2.  次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
     **BTSTask RemoveResource** [**/applicationname は:***値*] **/Luid:***値*[**/Server:***値*] [**/database:***値*]  
  
     例:  
  
     **BTSTask RemoveResource applicationname: myapplication/Luid:"MyApp.Orchestrations、バージョン 1.0.0.0、Culture = neutral, PublicKeyToken = = 0123456789ABCDEF"**  
  
    |パラメーター|Description|  
    |---------------|-----------------|  
    |**/ApplicationName**|削除するオーケストレーションが存在する BizTalk アプリケーションの名前。 名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。 このパラメーターを指定しなかった場合、既定のアプリケーションが使用されます。|  
    |**/Luid**|オーケストレーションのローカル一意識別子 (LUID)。 使用して、LUID を取得することができます、 [ListApp コマンド](../core/listapp-command.md)です。|  
    |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前です。 Database パラメーターを指定する場合は必須です。 Server パラメーターおよび Database パラメーターを指定しなかった場合、グループの既定の BizTalk 管理データベースが使用されます。|  
    |**/データベース**|BizTalk 管理データベースの名前。 Server パラメーターを指定する場合は必須です。 Server パラメーターおよび Database パラメーターを指定しなかった場合、グループの既定の BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの管理](../core/managing-orchestrations.md)   
 [RemoveResource コマンド](../core/removeresource-command.md)