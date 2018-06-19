---
title: アプリケーションに COM コンポーネントを追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], COM components
- managing [resources], COM components
- applications, COM components
- COM components, applications
ms.assetid: fdda1a9d-96af-41fe-9d94-ee1fbd80a7c9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc2fe522d024059ce672124d48e458c869de9406
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007283"
---
# <a name="how-to-add-a-com-component-to-an-application"></a>COM コンポーネントをアプリケーションに追加する方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して BizTalk アプリケーションに COM コンポーネントを追加する方法について説明します。  
  
 COM コンポーネントをアプリケーションに追加する際には、次の重要事項を念頭に置いてください。  
  
-   アプリケーションに既に存在する COM コンポーネントを上書きする場合は、[上書き] オプションを指定します。 上書きオプションは、両方のアイテムが同じローカル一意識別子 (LUID) を持つ場合にのみ必要です。 このオプションを指定しない場合、追加する COM コンポーネントと同じ LUID を持つ COM コンポーネントがアプリケーション内に既に存在すると、追加操作は失敗します。 使用してアプリケーション内のアイテムの Luid を表示することができます、 [ListApp コマンド](../core/listapp-command.md)です。  
  
-   BizTalk Server では、COM コンポーネントの依存関係のチェックやそれが存在するかどうかの確認は行われないので、コンポーネントが依存するアイテムが存在することの確認はユーザーが行う必要があります。  
  
-   64 ビットのアンマネージ COM/COM+ コンポーネントを追加し、その COM/COM+ コンポーネントを含むアプリケーションを 32 ビット コンピューターにインストールしようとしても、コンポーネントはインストールされません。 64 ビット コンピューターにしかインストールできません。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="to-add-a-com-component-to-an-application"></a>COM コンポーネントをアプリケーションに追加するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、BizTalk Server 管理コンソールを展開し、BizTalk グループを展開、アプリケーションを展開し、COM コンポーネントを追加するアプリケーションの順に展開します。  
  
3.  右クリックし、**リソース**フォルダーを指す**追加**、順にクリック**リソース**です。  
  
4.  をクリックして**追加**COM コンポーネントを選択し、クリックして**開く**です。  
  
5.  **ファイルの種類**ドロップダウン リストをクリックして**System.BizTalk:Com**です。  
  
6.  **オプション**、オンまたはオフ、 **(regsvr32) 転送先にファイルを登録して**アプリケーションが Windows レジストリに追加するコンポーネントを希望するかどうかに従って チェック ボックスインストールされています。  
  
7.  **先**、COM コンポーネントが、ファイル名を含む .msi ファイルから、アプリケーションがインストールされているときにコピーされる場所の完全なパスを入力します。 このパスを指定しないと、インストールでローカル ファイル システムにファイルがコピーされません。 選択した場合、このパスは必要な**先 (regsvr32) でファイルを登録**前の手順でチェック ボックスをオンします。  
  
     例: **%BTAD_InstallDir%\MyComponent.dll**  
  
8.  完了したら、 **[OK]** をクリックします。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。  
  
2.  次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
     **BTSTask AddResource** [**/applicationname は:***値*] **/Type:System.BizTalk:Com** **[/overwrite]** **/Source:***値*[**/Destination:***値*] [**/Options:Regsvr32OnInstall**[**/Server:***値*] [**/database:***値*]  
  
     例:  
  
     **BTSTask AddResource applicationname: myapplication/Type:System.BizTalk:Com/overwrite/Source:"C:\Source Components\COM.dll"/Destination:"C:\New Components\COM.dll"/Options:Regsvr32OnInstall/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |**/ApplicationName**|COM コンポーネントを追加する BizTalk アプリケーションの名前。 アプリケーション名が指定されなかった場合、グループの既定の BizTalk アプリケーションが使用されます。 名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
    |**/型**|**System.BizTalk:Com** (この値小文字は区別されません)。|  
    |**/上書き**|既存の COM コンポーネントを更新するためのオプション。 指定しなかった場合、追加する COM コンポーネントと同じ LUID の COM コンポーネントが既にアプリケーションに存在すると、AddResource 操作は失敗します。 使用してアプリケーション内のアイテムの Luid を表示することができます、 [ListApp コマンド](../core/listapp-command.md)です。|  
    |**/ソース**|COM コンポーネントの .dll ファイルの完全パス (ファイル名を含む)。 パスには、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
    |**/対象**|アプリケーションを .msi ファイルからインストールしたときに COM コンポーネントの .dll ファイルがコピーされる場所 (完全パス)。 指定しなかった場合、インストール中、ファイルはローカル ファイル システムにコピーされません。つまり、インストール中にコンポーネントを Windows レジストリに追加することはできなくなります。 パスには、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。 Regsvr32OnInstallOption を指定した場合は、Destination も指定する必要があります。|  
    |**/[オプション]**|**Regsvr32OnInstall です。** 指定した場合、アプリケーションを .msi ファイルからインストールしたときに、COM コンポーネントが Windows レジストリに追加されます。 このオプションを指定した場合は、Destination も指定する必要があります。|  
    |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
    |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [.NET アセンブリ、証明書、およびその他のリソースの管理](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource コマンド: COM コンポーネント](../core/addresource-command-com-component.md)   
 [BizTalk アプリケーションの作成と変更](../core/creating-and-modifying-biztalk-applications.md)