---
title: "アプリケーションから .NET アセンブリ、証明書、またはその他のリソース アイテムを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- virtual directories, deleting
- managing [.NET assemblies], deleting
- managing [applications], COM components
- managing [applications], deleting artifcats
- managing [certificates], deleting
- deleting, binding files
- binding files, deleting
- managing, COM components
- COM components, deleting
- managing [artifacts], deleting
- .NET assemblies, deleting
- deleting, virtual directories
- deleting, definitions [BAM]
- applications, .NET assemblies
- certificates, deleting
- deleting, .NET assemblies
- deleting, artifacts
- deleting, certificates
ms.assetid: b84eebac-261d-495f-80cd-ddda5bb08bef
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a82ffc63ff041aec1e9151e8198e2a7c3e74b3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-a-net-assembly-certificate-or-other-resource-artifact-from-an-application"></a>.NET アセンブリ、証明書またはその他のリソース アイテムをアプリケーションから削除する方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンドラインを使用して BizTalk アプリケーションから、次のリソース アイテムを削除する方法について説明します。 このトピックの手順を実行すると、BizTalk 管理データベースからアイテムが削除されます。 ただし、ファイル システム、証明書ストア、インターネット インフォメーション サービス (IIS)、または Windows レジストリからは削除されません。 また、バインド ファイルを削除した場合、バインド ファイルが削除されるのみで、バインドそのものは変更されません。  
  
-   .NET アセンブリ  
  
-   COM コンポーネント  
  
-   証明書  
  
-   アドホック ファイル  
  
-   BAM 定義  
  
-   バインド ファイル  
  
-   仮想ディレクトリ  
  
 インポートまたは追加によって仮想ディレクトリを明示的にアプリケーションに追加した場合は、このトピックの手順を使用して仮想ディレクトリを削除できます。 仮想ディレクトリを明示的に追加せず、受信場所の構成時に参照で追加した場合は、このトピックの手順を使用して仮想ディレクトリを削除することはできません。 これは、仮想ディレクトリが BizTalk 管理データベースに格納されないためです。 アプリケーションの .msi ファイルをエクスポートすると、IIS から仮想ディレクトリが取得され、.msi ファイルに追加されます。 .msi ファイルをインポートすると、そのグループの BizTalk 管理データベースに仮想ディレクトリが追加されます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="to-remove-a-resource-artifact-from-an-application"></a>アプリケーションからリソース アイテムを削除するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、[[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 管理]、削除するリソース アイテムが含まれる BizTalk グループ、リソース アイテムが含まれるアプリケーションの順に展開します。  
  
3.  クリックして、**リソース**フォルダーは、アイテムを右クリックし、をクリックして**削除**です。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。  
  
2.  次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
     **BTSTask RemoveResource** [**/applicationname は:***値*] **/Luid:***値*[**/Server:***値*] [**/database:***値*]  
  
     例:  
  
     **BTSTask RemoveResource applicationname: myapplication/Luid:"MyAssembly, バージョン 1.0.0.0、Culture = neutral, PublicKeyToken = = 0123456789ABCDEF"**  
  
    |パラメーター|Description|  
    |---------------|-----------------|  
    |**/ApplicationName**|削除するアイテムが存在する BizTalk アプリケーションの名前。 指定しなかった場合、既定のアプリケーションが使用されます。 名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
    |**/Luid**|アイテムのローカル一意識別子 (LUID)。 使用して、LUID を取得することができます、 **ListApp**コマンドを」の説明に従って[ListApp コマンド](../core/listapp-command.md)です。|  
    |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
    |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [.NET アセンブリ、証明書、およびその他のリソースの管理](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [RemoveResource コマンド](../core/removeresource-command.md)