---
title: "BizTalk グループから BizTalk アプリケーションを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- undeploying, applications
- applications, deleting
- applications, groups
- undeploying, deleting
- managing [applications], deleting
- deleting, applications
- applications, undeploying
- managing [applications], groups
- groups, applications
ms.assetid: 968a6436-ae1a-4f85-bb44-e704826a0197
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 269ef99a3244d0aba55d9dad856c0262d0d14ba0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-delete-a-biztalk-application-from-the-biztalk-group"></a>BizTalk グループから BizTalk アプリケーションを削除する方法
BizTalk グループからアプリケーションを削除できます。 アプリケーションを削除すると、グループの BizTalk データベースからアプリケーションのデータがすべて削除され、BizTalk Server 管理コンソールにアプリケーションが表示されなくなります。 アプリケーションはアンインストールされません。  
  
 アプリケーションを削除する前に、次の点を考慮してください。  
  
-   アプリケーションを削除する前に、アプリケーションを停止しておく必要があります。 」の説明に従って、アプリケーションを停止する完全停止オプションを使用する必要があります[起動し、BizTalk アプリケーションを停止する方法](../core/how-to-start-and-stop-a-biztalk-application.md)です。  
  
-   アプリケーションを削除できるのは、削除対象のアプリケーションを他のアプリケーションが参照していない場合だけです。 削除するアプリケーションを他のアプリケーションが参照している場合、先に他のアプリケーションから参照を削除する必要があります。 手順については、次を参照してください。[を別のアプリケーションへの参照を削除する方法](../core/how-to-remove-a-reference-to-another-application.md)です。  
  
-   削除対象のアプリケーションの送信ポート グループに、他のアプリケーションの送信ポートが属している場合、そのアプリケーションは削除できません。 メンバーとなっている送信ポートを参加解除してから、アプリケーションを削除する必要があります。 手順については、次を参照してください。[送信ポートまたは送信ポート グループを参加解除する方法](../core/how-to-unenlist-a-send-port-or-send-port-group.md)です。  
  
-   削除対象のアプリケーションに、パーティによって参照されている送信ポートが含まれている場合、そのアプリケーションは削除できません。 パーティから参照を削除するか、送信ポートを削除するか、または送信ポートを別のアプリケーションに移動します。 これらのタスクの実行方法の詳細については、次を参照してください。[方法を表示または編集するパーティ](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca)、[送信ポートを削除する方法](../core/how-to-delete-a-send-port.md)、または[別のアプリケーションにアイテムを移動する方法](../core/how-to-move-an-artifact-to-a-different-application.md)です。  
  
-   既定のアプリケーションは削除できません。 別のアプリケーションを既定にしてから削除する必要があります。 手順については、次を参照してください。[を既定のアプリケーションを変更する方法](../core/how-to-change-the-default-application.md)です。  
  
-   削除対象のアプリケーションのオーケストレーションに、中断したインスタンスが含まれている場合、そのアプリケーションは削除できません。  
  
-   BizTalk アプリケーションを完全に展開解除、行う必要がありますもで説明した手順[を BizTalk アプリケーションをアンインストールする方法](../core/how-to-uninstall-a-biztalk-application.md)、」の説明に従って、他のファイルと設定を削除する必要がありますもと[を削除する方法その他のファイルと BizTalk アプリケーションの設定](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="to-delete-a-biztalk-application"></a>BizTalk アプリケーションを削除するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**BizTalk グループを展開し、展開、**アプリケーション**です。  
  
3.  アプリケーションのフォルダーを右クリックし、をクリックして**削除**です。  
  
4.  をクリックして**はい**削除を確認します。  
  
     BizTalk Server は、BizTalk データベースからアプリケーションのデータをすべて削除し、BizTalk Server 管理コンソールからアプリケーションを削除します。  
  
     BizTalk Server がアプリケーション アイテムを削除できない場合、削除操作が失敗します。 この場合、BizTalk Server は削除操作のロールバックを試行します。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。  
  
2.  次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
     **BTSTask RemoveApp/applicationname は:** *値*[**/Server:***値*] [**/database:** *値*]  
  
     例:  
  
     **BTSTask RemoveApp applicationname:**  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |**/ApplicationName**|削除する BizTalk アプリケーションの名前。 名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
    |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前です。 Database パラメーターを指定する場合は必須です。 Server パラメーターおよび Database パラメーターを指定しなかった場合、グループの既定の BizTalk 管理データベースが使用されます。|  
    |**/データベース**|BizTalk 管理データベースの名前。 Server パラメーターを指定する場合は必須です。 Server パラメーターおよび Database パラメーターを指定しなかった場合、グループの既定の BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションを展開解除](../core/undeploying-biztalk-applications.md)   
 [BizTalk アプリケーションの展開](../core/deploying-biztalk-applications.md)