---
title: 処理前または処理後のスクリプトをアプリケーションから削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [scripts], deleting
- deleting, scripts
- managing [applications], scripts
- scripts, deleting
- applications, scripts
ms.assetid: 7911f098-97f2-4a5d-87fe-20b55231113e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c9742b6c523f193a8670c1171f38949ef5dd1cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010011"
---
# <a name="how-to-remove-a-pre--or-post-processing-script-from-an-application"></a>処理前または処理後のスクリプトをアプリケーションから削除する方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、処理前または処理後のスクリプトをアプリケーションから削除する方法について説明します。 これにより、BizTalk 管理データベースからスクリプトが削除されます。そのため、アプリケーションの.msi ファイルにスクリプトがエクスポートされません。 ローカル ファイル システムに存在しているスクリプトは削除されません。  
  
 スクリプトを含むアプリケーションをローカル ファイル システムにインストールし、このスクリプトがアンインストール中に実行される場合は、このスクリプトをファイルシステムから削除して、アプリケーションのアンインストール中に実行されないようにする必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
## <a name="to-remove-a-script-from-an-application"></a>アプリケーションからスクリプトを削除するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、削除するスクリプトが含まれる BizTalk グループ、スクリプトが含まれるアプリケーションの順に展開します。  
  
3. をクリックして、**リソース**フォルダーは、スクリプトを右クリックし、順にクリックします**削除**します。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1. 次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。  
  
2. 次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
    **BTSTask RemoveResource** [**/applicationname は:**<em>値</em>] **/Luid:**<em>値</em>[**/Server:** <em>値</em>] [**/database:**<em>値</em>]  
  
    例:  
  
    **BTSTask RemoveResource applicationname: myapplication/Luid:"MyApplication:MyScript.vbs"**  
  
   |パラメーター|説明|  
   |---------------|-----------------|  
   |**/ApplicationName**|削除する BizTalk スクリプトが存在する BizTalk アプリケーションの名前。 名前にスペースが含まれる場合は、名前を二重引用符 (") で囲む必要があります。 このパラメーターを指定しなかった場合、既定のアプリケーションが使用されます。|  
   |**/Luid**|スクリプトのローカル一意識別子 (LUID)。 LUID を取得するにを使用して、 [ListApp コマンド](../core/listapp-command.md)します。|  
   |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
   |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [前処理および後処理のスクリプトを管理します。](../core/managing-pre-and-post-processing-scripts.md)   
 [RemoveResource コマンド](../core/removeresource-command.md)