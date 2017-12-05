---
title: "アプリケーションから BizTalk アセンブリを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [applications], assemblies
- assemblies, deleting
- deleting, assemblies
- applications, assemblies
- managing [assemblies], deleting
ms.assetid: 0691c3b6-476d-4e01-b50b-47d7c0b299bf
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89e46b8610114149e8618811361090d8644f82aa
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-remove-a-biztalk-assembly-from-an-application"></a>BizTalk アセンブリをアプリケーションから削除する方法
ここでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、BizTalk アセンブリを BizTalk アプリケーションから削除する方法について説明します。 この操作を実行すると、アセンブリおよびそのアセンブリに含まれるアイテム (オーケストレーション、スキーマ、パイプラインなど) は、アプリケーションおよび BizTalk 管理データベースから削除されます。  
  
 BizTalk アセンブリを削除する前に、次の重要事項を考慮します。  
  
-   BizTalk アセンブリを削除すると、アセンブリ ファイルは、グローバル アセンブリ キャッシュ (GAC) またはローカル ファイル システム内に存在する場合、自動的に削除されません。 そのアセンブリ ファイルは手動で削除する必要があります。 手順については、次を参照してください。 [GAC からアセンブリをアンインストールする方法](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4)と[するその他のファイルを削除すると、BizTalk アプリケーションの設定方法](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)です。  
  
-   パイプラインを含む BizTalk アセンブリを削除すると、同じアプリケーション内でそのパイプラインを使用する送信ポートはすべてリセットされて、既定の PassThruTransmit パイプラインを使用するようになります。  
  
-   他のアイテムが依存する BizTalk アセンブリは削除できません。 最初に、依存関係にあるアイテムを削除する必要があります。 それから、BizTalk アセンブリを削除できます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="to-remove-a-biztalk-assembly-from-an-application"></a>アプリケーションから BizTalk アセンブリを削除するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、BizTalk Server 管理コンソールを展開し、削除するには、BizTalk アセンブリを含む BizTalk グループを展開し、BizTalk アセンブリを含むアプリケーションの順に展開します。  
  
3.  クリックして、**リソース**フォルダーは、BizTalk アセンブリを右クリックし、をクリックして**削除**です。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。  
  
2.  次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
     **BTSTask RemoveResource** [**/applicationname は:***値*] **/Luid:***値*[**/Server:***値*] [**/database:***値*]  
  
     例:  
  
     **BTSTask RemoveResource applicationname: myapplication/Luid:"MyApp.Orchestrations、バージョン 1.0.0.0、Culture = neutral, PublicKeyToken = = 0123456789ABCDEF"**  
  
    |パラメーター|Description|  
    |---------------|-----------------|  
    |**/ApplicationName**|削除する BizTalk アセンブリが含まれる BizTalk アプリケーションの名前。 このパラメーターを指定しなかった場合、既定のアプリケーションが使用されます。 名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
    |**/Luid**|BizTalk アセンブリのローカル一意識別子 (LUID)。 使用して、LUID を取得することができます、 **ListApp**コマンドを」の説明に従って[ListApp コマンド](../core/listapp-command.md)です。|  
    |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
    |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [BizTalk アセンブリの管理](../core/managing-biztalk-assemblies.md)   
 [RemoveResource コマンド](../core/removeresource-command.md)