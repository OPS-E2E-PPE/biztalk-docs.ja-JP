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
ms.openlocfilehash: cf8051c013e8e8861a8746c6bb1421c882d7dd22
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014091"
---
# <a name="how-to-add-a-virtual-directory-to-an-application"></a>仮想ディレクトリをアプリケーションに追加する方法
このトピックでは、BTSTask コマンド ライン ツールを使用して BizTalk アプリケーションに仮想ディレクトリを追加する方法について説明します。 このオプションは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールでは利用できません。 カスタム Web サービスを記述するか、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] とのインターフェイス用に ASP.NET Web サイトを作成して、アプリケーションに仮想ディレクトリを展開する場合、仮想ディレクトリを追加できます。  
  
 」の説明に従って、別の方法をアプリケーションに仮想ディレクトリは SOAP または HTTP 仮想ディレクトリを指定することで、追加する受信場所、 [HTTP の受信場所を構成する方法](../core/how-to-configure-an-http-receive-location.md)します。 いずれの場合も、仮想ディレクトリは BizTalk 管理データベースに追加されます。 表示されます、コマンドラインを使用して、仮想ディレクトリを追加すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、追加したアプリケーションのリソース フォルダーと同様、を使用すると、アプリケーション内のアイテムの一覧で[ListApp コマンド](../core/listapp-command.md)します。 後でアプリケーションをエクスポートして別の BizTalk グループにインポートした場合、仮想ディレクトリはその [リソース] フォルダーに表示されます。  
  
 仮想ディレクトリをアプリケーションに追加する際には、次の点に注意してください。  
  
-   上書きオプションを指定することで、アプリケーションに既に存在する仮想ディレクトリを上書きできます。 既存の仮想ディレクトリに追加するものと同じ名前がある場合にのみ、上書きオプションが必要です。 指定されていない場合、仮想ディレクトリが追加される 1 つとして同じ名前のアプリケーションに既に存在します、追加操作は失敗します。  
  
-   URL に https が含まれる仮想ディレクトリを追加する場合、URL には https ではなく http を使用する必要があります。 https を使用した場合、仮想ディレクトリの追加操作は失敗します。 URL に http を指定したとしても、インターネット インフォメーション サービス メタベースでは、依然として、その URL の https 設定が有効であるため、仮想ディレクトリは正常に機能します。  
  
-   64 ビット版の Web サービスから仮想ディレクトリを追加し、その仮想ディレクトリを含むアプリケーションを 32 ビット コンピューターにインストールしようとしても、仮想ディレクトリはインストールされません。 64 ビット コンピューターにインストールする必要があります。  
  
> [!IMPORTANT]
>  仮想ディレクトリを含むアプリケーションをインポートすると、仮想ディレクトリのセキュリティ設定は、アプリケーションのエクスポートで .msi ファイルが生成されたときに使用されていた設定になります。 アプリケーションを実稼働環境に展開する場合は、アプリケーションをエクスポートする前に、設定がセキュリティの要件を満たしていることを確認してください。  
>   
>  ただし、その仮想ディレクトリが展開先の環境に既に存在する場合は、既存の仮想ディレクトリのセキュリティ設定が有効になります。 展開しようとしている仮想ディレクトリのセキュリティ設定に合わせて変更されることはありません。 この場合は、既存の仮想ディレクトリのセキュリティ設定が要件を満たしているかどうかの確認が必要になります。  
  
> [!CAUTION]
>  仮想ディレクトリで HTTPS (Hypertext Transfer Protocol over Secure Socket Layer) プロトコルが使用されている場合、その仮想ディレクトリのセキュリティ設定はエクスポート時に維持されず、インポート時にはルートのセキュリティ設定が継承されます。 したがって、そのセキュリティ設定が要件を満たしているかどうかの確認が必要になります。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループに属するアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-add-a-virtual-directory-to-an-application"></a>仮想ディレクトリをアプリケーションに追加するには  
  
1. 次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。  
  
2. 次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
    **BTSTask AddResource** [/**ApplicationName:**<em>値</em>] **/Type:System.BizTalk:WebDirectory****[/overwrite]****/Source:**<em>値</em>[**/Destination:**<em>値</em>] [**/Server:** <em>値</em>] [**/database:**<em>値</em>]  
  
    例:  
  
    **BTSTask AddResource applicationname: myapplication/Type: System.BizTalk:WebDirectory/overwrite/Source:<http://Host1:90/MyVirtualDirectory> /Destination:<http://Host2:90/MyVirtualDirectory> /Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
   |パラメーター|値|  
   |---------------|-----------|  
   |**/ApplicationName**|仮想ディレクトリを追加する BizTalk アプリケーションの名前。 アプリケーション名が指定されなかった場合、グループの既定の BizTalk アプリケーションが使用されます。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
   |**/型**|**System.BizTalk:WebDirectory** (この値小文字は区別されません)。|  
   |**/上書き**|既存の仮想ディレクトリを更新するためのオプション。 指定しなかった場合、追加する仮想ディレクトリと同じ名前の仮想ディレクトリが既にアプリケーションに存在した場合、AddResources 操作は失敗します。|  
   |**/ソース**|コピー元仮想ディレクトリの URI。|  
   |**/変換先**|アプリケーションが .msi ファイルからインストールされたときに、仮想ディレクトリに割り当てる URI。 このパラメーターを指定しなかった場合、Source パラメーターの値が localhost と組み合わせて使用されます。|  
   |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
   |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [.NET アセンブリ、証明書、およびその他のリソースを管理します。](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource コマンド: 仮想ディレクトリ](../core/addresource-command-virtual-directory.md)   
 [BizTalk アプリケーションの作成と変更](../core/creating-and-modifying-biztalk-applications.md)