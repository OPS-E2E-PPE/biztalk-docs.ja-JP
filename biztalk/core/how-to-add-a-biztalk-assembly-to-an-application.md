---
title: BizTalk アセンブリをアプリケーションに追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], adding assemblies
- assemblies, applications
- managing [assemblies], adding to applications
- applications, assemblies
- managing [assemblies], applications
ms.assetid: 1525a0f6-cb0f-43bf-a851-40c06ab2135e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9165415ec736c7cf9f4716e8fb183395602a687d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009347"
---
# <a name="how-to-add-a-biztalk-assembly-to-an-application"></a>BizTalk アセンブリをアプリケーションに追加する方法
ここでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、BizTalk アセンブリをアプリケーションに追加する方法について説明します。  
  
 BizTalk アセンブリをアプリケーションに追加する際には、次の重要事項を念頭に置いてください。  
  
-   アセンブリを追加して、アプリケーション内に既に存在する同じローカル一意識別子 (LUID) でアセンブリを上書きする場合は、[上書き] オプションを指定します。 指定しないと、追加するアセンブリと同じ LUID のアセンブリがアプリケーション内に既に存在する場合、操作は失敗します。 LUID には、アセンブリ ファイル名、バージョン、カルチャ、および公開キー トークンが含まれます。 使用してアプリケーション内のアイテムの Luid を表示することができます、 [ListApp コマンド](../core/listapp-command.md)です。  
  
-   また、追加するアセンブリが、そのアプリケーションには含まれない他のアイテムに依存している場合、追加操作は失敗します。  
  
-   BizTalk アセンブリを追加する場合、アセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールするための次のオプションを 1 つ以上指定できます。  
  
    -   **グローバル アセンブリ キャッシュに追加のリソース (gacutil) を追加します。** このオプションを選択すると、アセンブリがアプリケーションに追加されるときに、このトピックで説明する手順を実行した結果として、アセンブリはローカル コンピューターの GAC にインストールされます。  
  
    -   **MSI ファイル インポート (します gacutil) のグローバル アセンブリ キャッシュに追加します。** このオプションを選択すると、アプリケーションが .msi ファイルにエクスポートされ、.msi ファイルが BizTalk グループにインポートされた場合、アセンブリはインポート処理の一部として、ローカル コンピューターの GAC にインストールされます。  
  
    -   **MSI ファイル インストール (します gacutil) のグローバル アセンブリ キャッシュに追加します。** このオプションを選択すると、アプリケーションが .msi ファイルにエクスポートされ、アプリケーションが .msi ファイルからコンピューターにインストールされた場合、アセンブリはインポート処理の一部として、ローカル コンピューターの GAC にインストールされます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="to-add-a-biztalk-assembly-to-an-application"></a>BizTalk アセンブリをアプリケーションに追加するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、BizTalk Server 管理コンソールと BizTalk アセンブリを追加するアプリケーションを含む BizTalk グループを展開します。  
  
3.  [アプリケーション]、BizTalk アセンブリを追加するアプリケーションの順に展開します。  
  
4.  右クリック**リソース**、 をポイント**追加** をクリックし、 **BizTalk アセンブリ**です。  
  
5.  をクリックして**追加**BizTalk アセンブリ ファイルを選択して、をクリックして**開く**です。  
  
6.  **先**、アセンブリ ファイルのファイル名を含む、.msi ファイルから、アプリケーションがインストールされているときにコピーする先の場所の完全なパスを入力します。 指定しなかった場合、インストール中、アセンブリ ファイルはローカル ファイル システムにコピーされません。  
  
7.  **オプション**、GAC に BizTalk アセンブリをインストールするためのオプションを指定し、クリックして**OK**です。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。  
  
2.  次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
     **BTSTask AddResource** [**/applicationname は:***値*] **/Type:System.BizTalk:BizTalkAssembly** **[/Overwrite]** **/Source:***値*[**/Destination:***値*] [**/Options:GacOnAdd**&#124;です。**Gaconinstall です**&#124;**GacOnImport**] [**/Server:***値*] [**/database:***値*]  
  
     例:  
  
     **BTSTask AddResource applicationname: myapplication/Type:System.BizTalk:BizTalkAssembly/overwrite/Source:"C:\BizTalk Assemblies\MyOrchestration.dll"/Destination:"C:\New BizTalk Assemblies\ MyOrchestration.dll"/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |**/ApplicationName**|BizTalk アセンブリを追加する BizTalk アプリケーションの名前。 アプリケーション名が指定されなかった場合、既定の BizTalk アプリケーションが使用されます。 名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
    |**/型**|**System.BizTalk:BizTalkAssembly**|  
    |**/上書き**|既存のアセンブリを更新するためのオプション。 指定しないと、追加するアセンブリと同じ LUID のアセンブリが既にアプリケーションに存在した場合、AddResource 操作は失敗します。 使用してアプリケーション内のアイテムの Luid を表示することができます、 [ListApp コマンド](../core/listapp-command.md)です。 他のアプリケーションが、上書きされようとしているアセンブリに依存している場合、このパラメーターを指定したとしても AddResource 操作は失敗します。|  
    |**/ソース**|アセンブリ ファイルの完全パス (ファイル名を含む)。 パスには、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
    |**/対象**|アプリケーションを .msi ファイルからインストールしたときにアセンブリ ファイルがコピーされる場所 (完全パス)。 指定しなかった場合、インストール中、アセンブリ ファイルはローカル ファイル システムにコピーされません。 パスには、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
    |**/[オプション]**|-   **GacOnAdd**: AddResource 操作中に、アセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールするローカル コンピューターを指定します。<br />-   **Gaconinstall です**: アプリケーションを .msi ファイルからインストールすると、GAC にアセンブリをインストールするように指定します。<br />-   **GacOnImport**: アプリケーションの .msi ファイルをインポートするときに、GAC にアセンブリをインストールするように指定します。<br /><br /> 複数のオプションを入力する場合は、コンマで区切って入力します。|  
    |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
    |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [BizTalk アセンブリの管理](../core/managing-biztalk-assemblies.md)   
 [AddResource コマンド: BizTalk アセンブリ](../core/addresource-command-biztalk-assembly.md)