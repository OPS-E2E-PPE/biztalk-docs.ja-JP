---
title: .NET アセンブリをアプリケーションに追加する方法 |Microsoft ドキュメント
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b455dfb8f84580e3a8a4f5b6e2322c4f4e1d1b7
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-add-a-net-assembly-to-an-application"></a>.NET アセンブリをアプリケーションに追加する方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、BizTalk アセンブリではない .NET アセンブリを BizTalk アプリケーションに追加する方法について説明します。 .NET アセンブリをアプリケーションに追加する際には、次の重要事項を念頭に置いてください。  
  
-   アプリケーションに既に存在するアセンブリを上書きする場合は、[上書き] オプションを指定します。 [上書き] オプションは、両方のアセンブリが同じ LUID を持つ場合にのみ必要です。 このオプションを指定せず、追加するアセンブリと同じ LUID を持つアセンブリがアプリケーション内に既に存在する場合、追加操作は失敗します。 使用してアプリケーション内のアイテムの Luid を表示することができます、 [ListApp コマンド](../core/listapp-command.md)です。  
  
-   .NET アセンブリを追加すると、1 つまたは複数のアセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールするための次のオプションを選択できます。  
  
    -   **グローバル アセンブリ キャッシュに追加のリソース (gacutil) を追加します。** このオプションを選択すると、アセンブリがアプリケーションに追加されるときに、このトピックで説明する手順を実行した結果として、アセンブリはローカル コンピューターの GAC にインストールされます。  
  
    -   **MSI ファイル インポート (gacutil) のグローバル アセンブリ キャッシュに追加します。** このオプションを選択すると、アプリケーションが .msi ファイルにエクスポートされ、.msi ファイルが BizTalk グループにインポートされた場合、アセンブリはインポート処理の一部として、ローカル コンピューターの GAC にインストールされます。 ポリシーおよびポリシーが依存するアセンブリがアプリケーションに含まれている場合は、このオプションをオンにします。 ポリシーが含まれているアプリケーションをインポートする場合、そのポリシーが依存するアセンブリが GAC に存在している必要があります。したがって、このオプションをオンにする必要があります。  
  
    -   **MSI ファイルのインストール (gacutil) のグローバル アセンブリ キャッシュに追加します。** このオプションを選択すると、アプリケーションが .msi ファイルにエクスポートされ、アプリケーションが .msi ファイルからコンピューターにインストールされた場合、アセンブリはインポート処理の一部として、ローカル コンピューターの GAC にインストールされます。  
  
    -   **COM コンポーネント (regasm) に表示されるようにします。** このオプションをオンにすると、アプリケーションを .msi ファイルにエクスポートし、その .msi ファイルからアプリケーションをコンピューターにインストールした場合、マネージ COM アセンブリが、インストール処理の一部として、ローカル コンピューターの Windows レジストリに追加されます。 このオプションを指定する場合は、[エクスポート先] でファイルの場所も指定する必要があります。  
  
    -   **登録サービスのコンポーネント (regsvcs)。** このオプションをオンにすると、アプリケーションを .msi ファイルにエクスポートし、その .msi ファイルからアプリケーションをコンピューターにインストールした場合、マネージ COM+ アセンブリが、インストール処理の一部として、ローカル コンピューターの Windows レジストリに追加されます。 このオプションを指定する場合は、[エクスポート先] でファイルの場所も指定する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="to-add-a-net-assembly-to-an-application"></a>.NET アセンブリをアプリケーションに追加するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1.  をクリックして **開始**, 、 をクリックして **すべてのプログラム**, 、 をクリックして [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], 、 をクリックし、 **BizTalk Server 管理コンソール**します。  
  
2.  コンソール ツリーで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、BizTalk グループを展開し、**アプリケーション**、し、.NET アセンブリを追加するアプリケーションを展開します。  
  
3.  右クリックし、 **リソース** フォルダーを指す **追加**, 、 をクリックし、 **リソース**します。  
  
4.  クリックして **追加**, 、アセンブリをクリックして、クリックして、 **開く**します。  
  
5.  **ファイルの種類** ドロップダウン リストで、 **System.BizTalk:Assembly**します。  
  
6.  **オプション**, 、このアセンブリの展開オプションを選択します。  
  
7.  **宛先**, 、ファイルをファイル名を含む .msi ファイルからアプリケーションのインストール時にコピーされる場所の完全パスを入力します。 このパスを指定しないと、インストールでローカル ファイル システムにファイルがコピーされません。 アプリケーションのインストール フォルダーにファイルをコピーする場合、%BTAD_InstallDir% 環境変数をパスで使用できます。この環境変数は、アプリケーションのインストール フォルダーの値を、アプリケーションのインストール時に受け取ります。 このように、コピー先を指定する際には、アプリケーションのインストール フォルダーのパスを知る必要はありません。  
  
     例: **%BTADInstall_Dir%\Assemblies\Orchestrations.dll**  
  
8.  クリックして、 **の依存関係** タブし、このアセンブリが依存するアイテムを表示します。  
  
9. このアセンブリが依存するアイテムがこのアプリケーションに存在しない場合は、それを追加する **アプリケーションに追加**, を成果物を参照してクリックして **開く**します。  
  
10. 完了したら、 **[OK]**をクリックします。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用してください。  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、 をクリックし、 **ok**します。  
  
2.  コマンド プロンプトで次のコマンドを入力します。このとき、下の表を参考にして適切な値に置き換えます。  
  
     **BTSTask AddResource** [**/ApplicationName:***value*] **/Type:System.BizTalk:Assembly** [**/Overwrite**] **/Source:***value* [**/Destination:***value*] [**/Options:GacOnAdd***&#124;***GacOnInstall***&#124;***GacOnImport**&#124;**RegasmOnInstall**&#124;**RegsvcsOnInstall**] [**/Server:***value*] [**/Database:***value*]  
  
     例:  
  
     **BTSTask AddResource/ApplicationName:MyApplication/Type:System.BizTalk:Assembly/overwrite/Source:"C:\Source Assemblies\MyAssembly.dll"/Destination:"%BTAD_InstallDir%\New Assemblies\MyAssembly.dll"/Options:GacOnAdd、RegasmOnInstall/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |**/Applicationname**|アセンブリを追加する BizTalk アプリケーションの名前。 アプリケーション名が指定されなかった場合、グループの既定の BizTalk アプリケーションが使用されます。 名前にスペースが含まれる場合は、二重引用符 (") で囲む必要があります。|  
    |**/型**|**System.BizTalk:Assembly** (この値は区別されません)。|  
    |**/Overwrite します。**|既存のアセンブリを更新するためのオプション。 指定しなかった場合、追加するアセンブリと同じ完全名のアセンブリが既にアプリケーションに存在した場合、AddResource 操作は失敗します。 完全名には、アセンブリ ファイルの名前、バージョン、カルチャ、および公開キー トークンが含まれます。 使用してアプリケーション内のアイテムの Luid を表示することができます、 [ListApp コマンド](../core/listapp-command.md)です。|  
    |**/ソース**|アセンブリ ファイルの完全パス (ファイル名を含む)。 パスにスペースが含まれる場合は、二重引用符 (") で囲む必要があります。|  
    |**/Destination**|アプリケーションを .msi ファイルからインストールしたときにアセンブリ ファイルがコピーされる場所 (完全パス)。 指定しなかった場合、インストール中、アセンブリ ファイルはローカル ファイル システムにコピーされません。 パスにスペースが含まれる場合は、パスを二重引用符 (") で囲む必要があります。 RegasmOnInstall または RegsvcsOnInstall オプションを指定した場合は、Destination も指定する必要があります。 **注:**  %btad_installdir% 環境変数をパスに使用することができます。 この環境変数は、アプリケーションのインストール フォルダーの値を、アプリケーションのインストール時に受け取ります。 このように、コピー先を指定する際には、アプリケーションのインストール フォルダーのパスを知る必要はありません。 例: %BTAD_InstallDir%\Assemblies\Orchestrations.dll|  
    |**メニューの オプション**|-   **GacOnAdd**: AddResource 操作中に、ローカル コンピューター上のグローバル アセンブリ キャッシュ (GAC) にアセンブリをインストールします。<br />-   **GacOnInstall**: アプリケーションを .msi ファイルからインストールすると、アセンブリを GAC にインストールします。<br />-   **GacOnImport**: アプリケーションの .msi ファイルをインポートすると、アセンブリを GAC にインストールします。<br />-   **RegasmOnInstall**: アプリケーションを .msi ファイルからインストールすると、Windows レジストリに、マネージ COM アセンブリを追加します。 このオプションを指定した場合は、Destination も指定する必要があります。<br />-   **RegsvcsOnInstall**: .msi ファイルから、アプリケーションがインストールされているときに、マネージ COM + アセンブリを Windows レジストリに追加します。 このオプションを指定した場合は、Destination も指定する必要があります。<br /><br /> 複数のオプションを入力する場合は、コンマで区切って入力します。|  
    |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
    |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [.NET アセンブリ、証明書、およびその他のリソースの管理](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource コマンド: .NET アセンブリ](../core/addresource-command-net-assembly.md)   
 [BizTalk アプリケーションの作成と変更](../core/creating-and-modifying-biztalk-applications.md)