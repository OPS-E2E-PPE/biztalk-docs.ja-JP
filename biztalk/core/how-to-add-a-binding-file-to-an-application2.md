---
title: "バインド ファイルを Application2 に追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [applications], binding files
- applications, binding files
- binding files, applications
ms.assetid: 1543ee5f-9ae4-4683-b6fe-ee84028c381d
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a1c7f0a73f811a6b339428e62a93916d9301edf
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-add-a-binding-file-to-an-application"></a>アプリケーションにバインド ファイルを追加する方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、BizTalk アプリケーションにバインド ファイルを追加する方法について説明します。 」の説明に従って、アプリケーションまたはアセンブリの展開を簡単にためにバインドすることができます[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)です。  
  
 」の説明に従って、アセンブリ、アプリケーション、またはグループの BizTalk アプリケーションから .xml ファイルにバインドをエクスポートすることができます[バインドのエクスポート](../core/exporting-bindings6.md)、しを使用して、手順のいずれかのこのトピックで、バインド ファイルをアプリケーションに追加します。  
  
 この操作を実行すると、バインド ファイルが BizTalk 管理データベースに追加されて、BizTalk Server 管理コンソール (アプリケーションのリソース フォルダー) に表示されます。 バインド ファイルのインポートとは異なり、バインド ファイルを追加しても、そのバインドが直ちに適用されることはありません。 代わりに、アプリケーションが他の BizTalk グループにインポートされるときにバインドが適用されます。  
  
> [!IMPORTANT]
>  セキュリティ上の理由により、BizTalk Server では、バインドのエクスポート時にバインドのパスワードがファイルから削除されます。 バインドをインポートした後で、送信ポートと受信場所のパスワードを再構成する必要があります。 BizTalk Server 管理コンソールの [トランスポートのプロパティ] ダイアログ ボックスで、送信ポートと受信場所のパスワードをそれぞれ構成します。 手順については、次を参照してください。[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)です。 関連項目[を作成する方法、受信場所](../core/how-to-create-a-receive-location.md)です。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] で生成されたバインド ファイルを使用する場合は、ホストの信頼レベルがバインド ファイルに保存されることに注意してください。 バインドのインポートまたはアプリケーションのインポート中にバインドが適用されると、アイテムは、ホスト名にのみ基づいてホストにバインドされます。 アイテムが正しいホストにバインドされているか、および信頼レベルが適切であるか確認する必要があります。  
  
 バインド ファイルをアプリケーションに追加する場合、追加先の展開環境を表す任意の文字列 (Test や Production など) を使用して展開環境の値を指定できます。 この値には任意の文字列を使用できます。 これで、アプリケーションをインポートするときに、そのターゲット環境に対して指定された値を提供して適用するバインド ファイルを選択できます。 これを実行すると、バインド ファイルからバインドが適用されます。 ファイル内のバインドと同じ名前を持つアプリケーション内の既存のバインドは、自動的に上書きされます。  
  
 アプリケーションのインポート時、バインドは次の順序で適用されます。 インポート プロセスでバインドが適用されるとき、同じ名前を持つ適用済みのバインドは、新しいバインドで上書きされます。 つまり、同じ名前のバインドを適用すると、常に、最新のバインドが有効になります。  
  
1.  BizTalk Server によって生成されたアプリケーション バインドのうち、バインド ファイルでアプリケーションに明示的に追加されたバインドではなく、ユーザーがアプリケーション .msi ファイルへのエクスポート対象として明示的に選択したバインド。  
  
2.  明示的に追加されたバインド ファイルのうち、対象の展開環境が指定されていないもの。 この一連のバインド内での適用順序は特に決まっていません。  
  
3.  明示的に追加されたバインドのうち、対象の (アプリケーションのインポート用に選択された展開環境と一致する) 展開環境が関連付けられているもの。 この一連のバインド内での適用順序は特に決まっていません。  
  
 アプリケーションをインポートして、バインドの適用の詳細については、次を参照してください。[を BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="to-add-a-binding-file-to-an-application"></a>アプリケーションにバインド ファイルを追加するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、BizTalk Server 管理コンソールと、バインド ファイルを追加するアプリケーションを含む BizTalk グループを展開します。  
  
3.  [アプリケーション] を展開し、バインド フィルを追加するアプリケーションを右クリックします。  
  
4.  をポイント**追加**、クリックして**リソース**です。  
  
5.  をクリックして**追加**、をクリックし、追加のファイルを選択して**開く**です。  
  
6.  同じファイル名を持つこのアプリケーションの既存のバインド ファイルを上書きするには、次のように選択します。、**すべて上書き**チェック ボックスをオンします。 同じ名前の別のファイルが存在し、このチェック ボックスをオンにしない場合、追加の処理は失敗します。  
  
7.  **ファイルの種類**ドロップダウン リストで、 **System.BizTalk:BizTalkBinding**です。  
  
8.  **ターゲット環境**、テストなど、適用する をクリックしてこのファイルにバインドする対象の展開環境を表す文字列の入力**OK**です。  
  
    > [!IMPORTANT]
    >  このフィールドを空のままにすると、アプリケーションのインポート時にこのファイルのバインドは常に適用されます。  
  
     バインド ファイルが追加され、アプリケーションのリソース フォルダーに表示されます。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。  
  
2.  次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
     **BTSTask AddResource** [**/applicationname は:"***値***"**] **/Type:System.BizTalk:BizTalkBinding** **[/Overwrite]** **/source:***値***/Property:TargetEnvironment ="***値* **"** [**/Server:***値*] [**/database:***値*]  
  
     例:  
  
     **BTSTask AddResource/applicationname は:"My Application"/Type:System.BizTalk:BizTalkBinding/Source:"C:\Binding Files\MyBinding.xml"/Property:TargetEnvironment"Production"/Server:MyDatabaseServer/Database:BizTalkMgmtDb を =**  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |**/ApplicationName**|バインド ファイルを追加する BizTalk アプリケーションの名前。 アプリケーション名が指定されなかった場合、既定の BizTalk アプリケーションが使用されます。 名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
    |**/型**|**System.BizTalk:BizTalkBinding** (この値小文字は区別されません)。|  
    |**/上書き**|既存のバインド ファイルを更新するためのオプション。 しない場合は、指定、およびバインド ファイルを追加するファイルと同じファイル名を持つアプリケーションに既に存在、AddResource 操作は失敗します。|  
    |**/ソース**|バインド ファイルの完全パス (ファイル名を含む)。 パスには、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
    |**/Property:TargetEnvironment =**|対象の展開環境を指定する文字列。 "Production" など、任意の文字列を使用できます。 例: **/Property:TargetEnvironment"Production"を =**<br /><br /> 値を指定しない場合\<既定\>が自動的に適用します。 値は、大文字小文字を区別します。 値にスペースが含まれる場合は、二重引用符 (") で囲む必要があります。 環境値の最大長は 128 文字です。|  
    |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
    |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [.NET アセンブリ、証明書、およびその他のリソースの管理](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource コマンド: BizTalk バインド](../core/addresource-command-biztalk-binding.md)   
 [BizTalk アプリケーションの作成と変更](../core/creating-and-modifying-biztalk-applications.md)