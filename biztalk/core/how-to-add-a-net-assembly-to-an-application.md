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
ms.openlocfilehash: 861ffca5f4ec8e7205656fb6b701f51f9952a499
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387249"
---
# <a name="how-to-add-a-net-assembly-to-an-application"></a>.NET アセンブリをアプリケーションに追加する方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンドラインを使用して BizTalk アプリケーションに BizTalk アセンブリではない .NET アセンブリを追加する方法を説明します。 .NET アセンブリをアプリケーションに追加する、次の重要な点に注意してください。  
  
-   アプリケーションに既に存在するアセンブリを上書きする場合は、上書きオプションを指定します。 上書きオプションは、両方のアセンブリが同じ LUID がある場合にのみ必要があります。 指定しない場合、アセンブリとして追加するアセンブリと同じ LUID を持つアプリケーションに既に存在、追加操作は失敗します。 アプリケーションのアイテムの Luid を表示するにを使用して、 [ListApp コマンド](../core/listapp-command.md)します。  
  
-   .NET アセンブリを追加すると、1 つ以上のアセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールするために、次のオプションを指定できます。  
  
    -   **グローバル アセンブリ キャッシュへの追加に (gacutil) のリソースを追加します。** このオプションを選択すると、アセンブリは、このトピックの手順を使用した結果として、アプリケーションにアセンブリが追加されたときに、ローカル コンピューターの GAC にインストールされます。  
  
    -   **MSI ファイルのインポート (gacutil) のグローバル アセンブリ キャッシュに追加します。** アプリケーションが .msi ファイルにエクスポートされ、.msi ファイルが BizTalk グループにインポートする場合に、このオプションを選択すると、インポート プロセスの一環として、ローカル コンピューターの GAC にアセンブリがインストールされています。 アプリケーションは、ポリシーとポリシーが依存しているアセンブリが含まれる場合は、このオプションを選択します。 ポリシーを含むアプリケーションをインポートするときに、ポリシーが依存するすべてのアセンブリが GAC に存在するある必要があります、ため、このようにする必要があります。  
  
    -   **MSI ファイル インストール (gacutil)、グローバル アセンブリ キャッシュに追加します。** アプリケーションが .msi ファイルにエクスポートし、アプリケーションが .msi ファイルからコンピューターにインストールされている場合、このオプションを選択すると、アセンブリはインストール プロセスの一環として、ローカル コンピューターの GAC にインストールされています。  
  
    -   **COM コンポーネント (regasm) に表示されるようにします。** アプリケーションが .msi ファイルにエクスポートし、アプリケーションが .msi ファイルからコンピューターにインストールされている場合、このオプションを選択すると、マネージ COM アセンブリは、インストール プロセスの一環として、ローカル コンピューター上の Windows レジストリに追加されます。 このオプションを指定する場合は、先にもファイルの場所を指定する必要があります。  
  
    -   **コンポーネント (regsvcs) を登録サービスを提供します。** アプリケーションが .msi ファイルにエクスポートし、アプリケーションが .msi ファイルからコンピューターにインストールされている場合、このオプションを選択すると、マネージ COM + アセンブリがインストール プロセスの一環として、ローカル コンピューター上の Windows レジストリに追加されます。 このオプションを指定する場合は、先にもファイルの場所を指定する必要があります。  
  
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
  
7. **先**ファイル名を含む .msi ファイルから、アプリケーションのインストール時にコピーするファイルのある場所の完全なパスを入力します。 このパスを指定しないと、インストールでローカル ファイル システムにファイルがコピーされません。 アプリケーションのインストール フォルダーにファイルをコピーするには、パスが、アプリケーションがインストールされている場合は、アプリケーションのインストール フォルダーの値をとります %btad_installdir% 環境変数を使用することができます。 これにより、アップグレード先の場所を指定すると、アプリケーションのインストール フォルダーのパスを把握する必要はありません。  
  
    例: **%BTADInstall_Dir%\Assemblies\Orchestrations.dll**  
  
8. をクリックして、**依存関係**タブし、このアセンブリが依存するアイテムを表示します。  
  
9. このアセンブリが依存するアイテムがこのアプリケーションに存在しないと、それを追加する場合**アプリケーションに追加**、成果物を参照し、クリックして**オープン**。  
  
10. 完了したら、 **[OK]** をクリックします。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1. 次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。  
  
2. 次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
    **BTSTask AddResource** [ **/applicationname は:** <em>値</em>] **/Type:System.BizTalk:Assembly** **[/overwrite]** **/Source:** <em>値</em>[ **/Destination:** <em>値</em>] [ **/Options:GacOnAdd**<em>&#124;</em> **GacOnInstall**<em>&#124;</em>**GacOnImport**&#124;**RegasmOnInstall** &#124; **RegsvcsOnInstall**] [ **/Server:** <em>値</em>] [ **/database:** <em>値</em>]  
  
    例:  
  
    **BTSTask AddResource applicationname: myapplication/Type:System.BizTalk:Assembly/overwrite/Source:"C:\Source Assemblies\MyAssembly.dll"/Destination:"%BTAD_InstallDir%\New Assemblies\MyAssembly.dll"/Options:GacOnAdd、RegasmOnInstall/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
   |パラメーター|値|  
   |---------------|-----------|  
   |**/ApplicationName**|アセンブリを追加する BizTalk アプリケーションの名前。 アプリケーション名が指定されなかった場合、グループの既定の BizTalk アプリケーションが使用されます。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
   |**/Type**|**System.BizTalk:Assembly** (この値小文字は区別されません)。|  
   |**/Overwrite**|既存のアセンブリを更新するためのオプション。 指定しなかった場合、追加するアセンブリと同じ完全名のアセンブリが既にアプリケーションに存在した場合、AddResource 操作は失敗します。 完全な名前には、アセンブリ ファイル名、バージョン、カルチャ、および公開キー トークンが含まれています。 アプリケーションのアイテムの Luid を表示するにを使用して、 [ListApp コマンド](../core/listapp-command.md)します。|  
   |**/ソース**|アセンブリ ファイルの完全パス (ファイル名を含む)。 パスにスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
   |**/変換先**|アプリケーションを .msi ファイルからインストールしたときにアセンブリ ファイルがコピーされる場所 (完全パス)。 指定しなかった場合、インストール中、アセンブリ ファイルはローカル ファイル システムにコピーされません。 パスにスペースがある場合は、二重引用符 (") で囲む必要があります。 RegasmOnInstall または RegsvcsOnInstall オプションを指定した場合は、Destination も指定する必要があります。 **注:** パスには、%btad_installdir% 環境変数を使用できます。 アプリケーションがインストールされている場合、アプリケーションのインストール フォルダーの値がかかります。 これにより、アップグレード先の場所を指定すると、アプリケーションのインストール フォルダーのパスを把握する必要はありません。 例: %BTAD_InstallDir%\Assemblies\Orchestrations.dll|  
   |**/オプション**|-   **GacOnAdd**:AddResource 操作中に、ローカル コンピューターのグローバル アセンブリ キャッシュ (GAC) にアセンブリをインストールします。<br />-   **GacOnInstall**:.Msi ファイルから、アプリケーションがインストールされている場合は、アセンブリを GAC にインストールします。<br />-   **GacOnImport**:アプリケーションの .msi ファイルをインポートすると、アセンブリを GAC にインストールします。<br />-   **RegasmOnInstall**:.Msi ファイルから、アプリケーションがインストールされている場合、マネージ COM アセンブリを Windows レジストリに追加します。 このオプションを指定した場合は、Destination も指定する必要があります。<br />-   **RegsvcsOnInstall**: アプリケーションが .msi ファイルからインストールされている場合、マネージ COM + アセンブリを Windows レジストリに追加します。 このオプションを指定した場合は、Destination も指定する必要があります。<br /><br /> 複数のオプションを入力する場合は、コンマで区切って入力します。|  
   |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
   |**/Database**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [.NET アセンブリ、証明書、およびその他のリソースを管理します。](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource コマンド: .NET アセンブリ](../core/addresource-command-net-assembly.md)   
 [BizTalk アプリケーションの作成と変更](../core/creating-and-modifying-biztalk-applications.md)