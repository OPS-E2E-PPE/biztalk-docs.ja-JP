---
title: .NET アセンブリをアプリケーションに追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [.NET assemblies], adding to applications
- managing [applications], .NET assemblies
- managing [.NET assemblies], applications
- applications, .NET assemblies
- .NET assemblies, adding to applications
ms.assetid: 75dc3303-a622-40df-881e-3109cbc81c91
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15e439b4a3e6821d0d0842efa72b4543ca8f4614
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975531"
---
# <a name="how-to-add-a-net-assembly-to-an-application"></a>.NET アセンブリをアプリケーションに追加する方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、BizTalk アセンブリではない .NET アセンブリを BizTalk アプリケーションに追加する方法について説明します。 .NET アセンブリをアプリケーションに追加する際には、次の重要事項を念頭に置いてください。  
  
-   アプリケーションに既に存在するアセンブリを上書きする場合は、[上書き] オプションを指定します。 [上書き] オプションは、両方のアセンブリが同じ LUID を持つ場合にのみ必要です。 このオプションを指定せず、追加するアセンブリと同じ LUID を持つアセンブリがアプリケーション内に既に存在する場合、追加操作は失敗します。 アプリケーションのアイテムの Luid を表示するにを使用して、 [ListApp コマンド](../core/listapp-command.md)します。  
  
-   .NET アセンブリを追加すると、1 つ以上のアセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールするために、次のオプションを指定できます。  
  
    -   **グローバル アセンブリ キャッシュへの追加に (gacutil) のリソースを追加します。** このオプションを選択すると、アセンブリがアプリケーションに追加されるときに、このトピックで説明する手順を実行した結果として、アセンブリはローカル コンピューターの GAC にインストールされます。  
  
    -   **MSI ファイルのインポート (gacutil) のグローバル アセンブリ キャッシュに追加します。** このオプションを選択すると、アプリケーションが .msi ファイルにエクスポートされ、.msi ファイルが BizTalk グループにインポートされた場合、アセンブリはインポート処理の一部として、ローカル コンピューターの GAC にインストールされます。 ポリシーおよびポリシーが依存するアセンブリがアプリケーションに含まれている場合は、このオプションをオンにします。 ポリシーが含まれているアプリケーションをインポートする場合、そのポリシーが依存するアセンブリが GAC に存在している必要があります。したがって、このオプションをオンにする必要があります。  
  
    -   **MSI ファイル インストール (gacutil)、グローバル アセンブリ キャッシュに追加します。** このオプションを選択すると、アプリケーションが .msi ファイルにエクスポートされ、アプリケーションが .msi ファイルからコンピューターにインストールされた場合、アセンブリはインポート処理の一部として、ローカル コンピューターの GAC にインストールされます。  
  
    -   **COM コンポーネント (regasm) に表示されるようにします。** このオプションをオンにすると、アプリケーションを .msi ファイルにエクスポートし、その .msi ファイルからアプリケーションをコンピューターにインストールした場合、マネージド COM アセンブリが、インストール処理の一部として、ローカル コンピューターの Windows レジストリに追加されます。 このオプションを指定する場合は、[エクスポート先] でファイルの場所も指定する必要があります。  
  
    -   **コンポーネント (regsvcs) を登録サービスを提供します。** このオプションをオンにすると、アプリケーションを .msi ファイルにエクスポートし、その .msi ファイルからアプリケーションをコンピューターにインストールした場合、マネージド COM+ アセンブリが、インストール処理の一部として、ローカル コンピューターの Windows レジストリに追加されます。 このオプションを指定する場合は、[エクスポート先] でファイルの場所も指定する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
## <a name="to-add-a-net-assembly-to-an-application"></a>.NET アセンブリをアプリケーションに追加するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]展開し、BizTalk グループを展開し、**アプリケーション**、し、.NET アセンブリを追加するアプリケーションを展開します。  
  
3. 右クリックし、**リソース**フォルダーをポイントして**追加**、 をクリックし、**リソース**します。  
  
4. クリックして**追加**でアセンブリをクリックします。 をクリック**オープン**します。  
  
5. **ファイルの種類**ドロップダウン リストで、 **System.BizTalk:Assembly**します。  
  
6. **オプション**、このアセンブリの配置オプションを選択します。  
  
7. **先**ファイル名を含む .msi ファイルから、アプリケーションのインストール時にコピーするファイルのある場所の完全なパスを入力します。 このパスを指定しないと、インストールでローカル ファイル システムにファイルがコピーされません。 アプリケーションのインストール フォルダーにファイルをコピーする場合、%BTAD_InstallDir% 環境変数をパスで使用できます。この環境変数は、アプリケーションのインストール フォルダーの値を、アプリケーションのインストール時に受け取ります。 このように、コピー先を指定する際には、アプリケーションのインストール フォルダーのパスを知る必要はありません。  
  
    例: **%BTADInstall_Dir%\Assemblies\Orchestrations.dll**  
  
8. をクリックして、**依存関係**タブし、このアセンブリが依存するアイテムを表示します。  
  
9. このアセンブリが依存するアイテムがこのアプリケーションに存在しないと、それを追加する場合**アプリケーションに追加**、成果物を参照し、クリックして**オープン**。  
  
10. 完了したら、 **[OK]** をクリックします。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1. 次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。  
  
2. コマンド プロンプトで次のコマンドを入力します。このとき、下の表を参考にして適切な値に置き換えます。  
  
    **BTSTask AddResource** [**/applicationname は:**<em>値</em>] **/Type:System.BizTalk:Assembly** **[/overwrite]****/Source:**<em>値</em>[**/Destination:**<em>値</em>] [**/Options:GacOnAdd**<em>&#124;</em> **GacOnInstall**<em>&#124;</em>**GacOnImport**&#124;**RegasmOnInstall** &#124; **RegsvcsOnInstall**] [**/Server:**<em>値</em>] [**/database:** <em>値</em>]  
  
    例:  
  
    **BTSTask AddResource applicationname: myapplication/Type:System.BizTalk:Assembly/overwrite/Source:"C:\Source Assemblies\MyAssembly.dll"/Destination:"%BTAD_InstallDir%\New Assemblies\MyAssembly.dll"/Options:GacOnAdd、RegasmOnInstall/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
   |パラメーター|値|  
   |---------------|-----------|  
   |**/ApplicationName**|アセンブリを追加する BizTalk アプリケーションの名前。 アプリケーション名が指定されなかった場合、グループの既定の BizTalk アプリケーションが使用されます。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
   |**/型**|**System.BizTalk:Assembly** (この値小文字は区別されません)。|  
   |**/上書き**|既存のアセンブリを更新するためのオプション。 指定しなかった場合、追加するアセンブリと同じ完全名のアセンブリが既にアプリケーションに存在した場合、AddResource 操作は失敗します。 完全名には、アセンブリ ファイルの名前、バージョン、カルチャ、および公開キー トークンが含まれます。 アプリケーションのアイテムの Luid を表示するにを使用して、 [ListApp コマンド](../core/listapp-command.md)します。|  
   |**/ソース**|アセンブリ ファイルの完全パス (ファイル名を含む)。 パスにスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
   |**/変換先**|アプリケーションを .msi ファイルからインストールしたときにアセンブリ ファイルがコピーされる場所 (完全パス)。 指定しなかった場合、インストール中、アセンブリ ファイルはローカル ファイル システムにコピーされません。 パスにスペースが含まれる場合は、パスを二重引用符 (") で囲む必要があります。 RegasmOnInstall または RegsvcsOnInstall オプションを指定した場合は、Destination も指定する必要があります。 **注:** パスは %btad_installdir% 環境変数を使用できます。 この環境変数は、アプリケーションのインストール フォルダーの値を、アプリケーションのインストール時に受け取ります。 このように、コピー先を指定する際には、アプリケーションのインストール フォルダーのパスを知る必要はありません。 例: %BTAD_InstallDir%\Assemblies\Orchestrations.dll|  
   |**/オプション**|-   **GacOnAdd**: AddResource 操作中に、ローカル コンピューターのグローバル アセンブリ キャッシュ (GAC) にアセンブリをインストールします。<br />-   **GacOnInstall**: アプリケーションが .msi ファイルからインストールされている場合は、アセンブリを GAC にインストールします。<br />-   **GacOnImport**: アプリケーションの .msi ファイルをインポートすると、アセンブリを GAC にインストールします。<br />-   **RegasmOnInstall**: アプリケーションが .msi ファイルからインストールされている場合、マネージ COM アセンブリを Windows レジストリに追加します。 このオプションを指定した場合は、Destination も指定する必要があります。<br />-   **RegsvcsOnInstall**: アプリケーションが .msi ファイルからインストールされている場合、マネージ COM + アセンブリを Windows レジストリに追加します。 このオプションを指定した場合は、Destination も指定する必要があります。<br /><br /> 複数のオプションを入力する場合は、コンマで区切って入力します。|  
   |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
   |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [.NET アセンブリ、証明書、およびその他のリソースを管理します。](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource コマンド: .NET アセンブリ](../core/addresource-command-net-assembly.md)   
 [BizTalk アプリケーションの作成と変更](../core/creating-and-modifying-biztalk-applications.md)