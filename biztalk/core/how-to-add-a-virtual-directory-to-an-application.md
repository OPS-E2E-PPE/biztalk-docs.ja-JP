---
title: 仮想ディレクトリをアプリケーションに追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- virtual directories
- managing [applications], virtual directories
- applications, virtual directories
- virtual directories, applications
ms.assetid: a5726696-bd65-49d9-8814-a078afe8c067
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bfd9c47fbd25c57d1c025806e5eb9dae6bda72b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343312"
---
# <a name="how-to-add-a-virtual-directory-to-an-application"></a>仮想ディレクトリをアプリケーションに追加する方法
このトピックでは、BTSTask コマンド ライン ツールを使用して BizTalk アプリケーションに仮想ディレクトリを追加する方法を説明します。 このオプションでは使用できません、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 カスタム Web サービス記述またはとのやり取りの ASP.NET Web サイトを作成した場合は、仮想ディレクトリを追加する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]仮想ディレクトリ、アプリケーションを展開するとします。  
  
 」の説明に従って、別の方法をアプリケーションに仮想ディレクトリは SOAP または HTTP 仮想ディレクトリを指定することで、追加する受信場所、 [HTTP の受信場所を構成する方法](../core/how-to-configure-an-http-receive-location.md)します。 すべてのケースでは、仮想ディレクトリが BizTalk 管理データベースに追加されます。 表示されます、コマンドラインを使用して、仮想ディレクトリを追加すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、追加したアプリケーションのリソース フォルダーと同様、を使用すると、アプリケーション内のアイテムの一覧で[ListApp コマンド](../core/listapp-command.md)します。 後で、アプリケーションをエクスポートして別の BizTalk グループにインポートし、リソース フォルダーに、仮想ディレクトリが表示されます。  
  
 仮想ディレクトリをアプリケーションに追加すると、次の点に注意してください。  
  
-   上書きオプションを指定することで、アプリケーションに既に存在する仮想ディレクトリを上書きすることができます。 既存の仮想ディレクトリに追加するものと同じ名前がある場合にのみ、上書きオプションが必要です。 指定されていない場合、仮想ディレクトリが追加される 1 つとして同じ名前のアプリケーションに既に存在します、追加操作は失敗します。  
  
-   Https が含まれる URL を使用して仮想ディレクトリを追加する場合は、https ではなく、指定した URL に http を使用する必要があります。 Https を使用する場合は、仮想ディレクトリを追加する操作は失敗します。 を URL に http で追加する場合でも、インターネット インフォメーション サービス メタベースに URL の https 設定が有効、になり、仮想ディレクトリが正常に機能します。  
  
-   64 ビット版は、Web サービスから仮想ディレクトリを追加して、32 ビット コンピューター上の仮想ディレクトリを含むアプリケーションをインストールしようとした、仮想ディレクトリはインストールされません。 64 ビット コンピューターで、インストールされている必要があります。  
  
> [!IMPORTANT]
>  仮想ディレクトリを含むアプリケーションをインポートするときに、仮想ディレクトリのセキュリティ設定されていたアプリケーションのエクスポート中に、.msi ファイルが生成されたときにします。 アプリケーションをエクスポートする前に、運用環境にアプリケーションを展開する場合、設定がセキュリティ要件を満たしているかを確認してください。  
>   
>  ただし、仮想ディレクトリは、先の環境に既に存在する場合は、既存の仮想ディレクトリのセキュリティ設定が有効になります。 展開する仮想ディレクトリと一致するようには変更されません。 ここでは、既存の仮想ディレクトリのセキュリティ設定が要件を満たしていることを確認する必要があります。  
  
> [!CAUTION]
>  仮想ディレクトリは、HTTPS (Hypertext Transfer Protocol over Secure Socket Layer) プロトコルを使用している場合、そのセキュリティ設定は、エクスポート中は保持されませんし、インポートすると、仮想ディレクトリは、ルートのセキュリティ設定を継承します。 セキュリティ設定が要件を満たしているかを確認する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループに属するアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-add-a-virtual-directory-to-an-application"></a>仮想ディレクトリをアプリケーションに追加するには  
  
1. 次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。  
  
2. 次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
    **BTSTask AddResource** [/**ApplicationName:**<em>値</em>] **/Type:System.BizTalk:WebDirectory****[/overwrite]****/Source:**<em>値</em>[**/Destination:**<em>値</em>] [**/Server:** <em>値</em>] [**/database:**<em>値</em>]  
  
    例:  
  
    **BTSTask AddResource applicationname: myapplication/Type:System.BizTalk:WebDirectory/overwrite/Source:<http://Host1:90/MyVirtualDirectory> /Destination:<http://Host2:90/MyVirtualDirectory> /Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
   |パラメーター|値|  
   |---------------|-----------|  
   |**/ApplicationName**|仮想ディレクトリを追加する BizTalk アプリケーションの名前。 アプリケーション名が指定されなかった場合、グループの既定の BizTalk アプリケーションが使用されます。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
   |**/Type**|**System.BizTalk:WebDirectory** (この値小文字は区別されません)。|  
   |**/Overwrite**|既存の仮想ディレクトリを更新するオプション。 指定されていない場合、追加される仮想ディレクトリ、AddResources 操作は失敗と同じ名前を持つアプリケーションで仮想ディレクトリが既に存在します。|  
   |**/ソース**|ソース仮想ディレクトリの URI。|  
   |**/変換先**|.Msi ファイルから、アプリケーションがインストールされている場合、仮想ディレクトリに割り当てる URI。 このパラメーターが指定されていない場合、ソース パラメーターの値として使用されます localhost のホスト。|  
   |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
   |**/Database**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [.NET アセンブリ、証明書、およびその他のリソースを管理します。](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource コマンド:仮想ディレクトリ](../core/addresource-command-virtual-directory.md)   
 [BizTalk アプリケーションの作成と変更](../core/creating-and-modifying-biztalk-applications.md)