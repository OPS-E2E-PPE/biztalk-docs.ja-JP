---
title: アプリケーションから .NET アセンブリ、証明書、またはその他のリソース アイテムを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0af1ab10400b51515b3041e12935e571eb76be69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397959"
---
# <a name="how-to-remove-a-net-assembly-certificate-or-other-resource-artifact-from-an-application"></a>アプリケーションから .NET アセンブリ、証明書、またはその他のリソース アイテムを削除する方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンドラインを使用して BizTalk アプリケーションから次のリソース アイテムを削除する方法を説明します。 このトピックの手順を使用すると、BizTalk 管理データベースからアイテムが削除されます。 これらの場所のいずれかに存在する場合、成果物ファイル システム、証明書ストア、インターネット インフォメーション サービス (IIS)、または、Windows レジストリから削除されません。 さらに、バインド ファイルを削除する場合、バインドは変更されません: バインド ファイルのみが削除されます。  
  
- .NET アセンブリ  
  
- COM コンポーネント  
  
- 証明書  
  
- アドホック ファイル  
  
- BAM 定義  
  
- バインド ファイル  
  
- 仮想ディレクトリ  
  
  仮想ディレクトリがアプリケーションをインポートまたは追加するには、いずれかに明示的に追加された場合は、このトピックの手順を使用して削除できます。 明示的に追加されていないではなく参照で追加した受信場所の構成時に、このトピックの手順を使用して削除することはできません。 これは、仮想ディレクトリが BizTalk 管理データベースに格納されていないためにです。 アプリケーションの .msi ファイルをエクスポートするときに、仮想ディレクトリを IIS から取得したし、.msi ファイルに追加します。 .Msi ファイルをインポートするときに仮想ディレクトリがそのグループの BizTalk 管理データベースに追加されます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
## <a name="to-remove-a-resource-artifact-from-an-application"></a>アプリケーションからリソース アイテムを削除するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1. クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk Server 管理コンソールを展開、およびを削除するリソース アイテムが含まれる BizTalk グループを展開し、成果物を含むアプリケーションを展開します。  
  
3. をクリックして、**リソース**フォルダーは、アイテムを右クリックし、順にクリックします**削除**します。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1. 次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。  
  
2. 次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
    **BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]  
  
    例:  
  
    **BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyAssembly, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**  
  
   |パラメーター|説明|  
   |---------------|-----------------|  
   |**/ApplicationName**|削除するアイテムが含まれる BizTalk アプリケーションの名前です。 指定しなかった場合、既定のアプリケーションが使用されます。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
   |**/Luid**|成果物のローカルで一意の識別子 (LUID)。 LUID を取得するにを使用して、 **ListApp** 」の説明に従って、コマンド[ListApp コマンド](../core/listapp-command.md)します。|  
   |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
   |**/Database**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [.NET アセンブリ、証明書、およびその他のリソースを管理します。](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [RemoveResource コマンド](../core/removeresource-command.md)