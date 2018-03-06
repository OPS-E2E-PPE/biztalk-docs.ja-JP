---
title: "バインド ファイルをアプリケーションに追加 |Microsoft ドキュメント"
description: "BizTalk Server 管理コンソールを使用してバインド ファイルを追加または BizTalk Server でコマンド プロンプトの使用"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1543ee5f-9ae4-4683-b6fe-ee84028c381d
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f6d2a999be4a12860616bc92f3086b37dbd265f
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
---
# <a name="add-a-binding-file-to-an-application"></a>バインド ファイルをアプリケーションに追加します。

## <a name="overview"></a>概要
バインド ファイルを BizTalk アプリケーションに追加するのには、BizTalk Server 管理コンソールまたはコマンドラインを使用します。 」の説明に従って、アプリケーションまたはアセンブリの展開を簡単にためにバインドすることができます[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)です。  
  
 」の説明に従って、アセンブリ、アプリケーション、またはグループの BizTalk アプリケーションから .xml ファイルにバインドをエクスポートすることができます[バインドのエクスポート](../core/exporting-bindings6.md)、しを使用して、手順のいずれかのこのトピックで、バインド ファイルをアプリケーションに追加します。  
  
 この操作を実行すると、バインド ファイルが BizTalk 管理データベースに追加されて、BizTalk Server 管理コンソール (アプリケーションのリソース フォルダー) に表示されます。 バインド ファイルのインポートとは異なり、バインド ファイルを追加しても、そのバインドが直ちに適用されることはありません。 代わりに、アプリケーションが他の BizTalk グループにインポートされるときにバインドが適用されます。  
  
> [!IMPORTANT]
>  セキュリティ上の理由により、BizTalk Server では、バインドのエクスポート時にバインドのパスワードがファイルから削除されます。 バインドをインポートした後で、送信ポートと受信場所のパスワードを再構成する必要があります。 BizTalk Server 管理コンソールの [トランスポートのプロパティ] ダイアログ ボックスで、送信ポートと受信場所のパスワードをそれぞれ構成します。 参照してください[送信ポートを作成](../core/how-to-create-a-send-port2.md)または[作成、受信場所](../core/how-to-create-a-receive-location.md)です。  
  
> [!NOTE]
>  バインド ファイルを使用する場合は、成果物が適切なホストにバインドされていると、信頼レベルに適していることを確認してください。  
  
 バインド ファイルをアプリケーションに追加する場合、追加先の展開環境を表す任意の文字列 (Test や Production など) を使用して展開環境の値を指定できます。 この値には任意の文字列を使用できます。 これで、アプリケーションをインポートするときに、そのターゲット環境に対して指定された値を提供して適用するバインド ファイルを選択できます。 これを実行すると、バインド ファイルからバインドが適用されます。 ファイル内のバインドと同じ名前を持つアプリケーション内の既存のバインドは、自動的に上書きされます。  
  
 アプリケーションのインポート時、バインドは次の順序で適用されます。 インポート プロセスでバインドが適用されるとき、同じ名前を持つ適用済みのバインドは、新しいバインドで上書きされます。 つまり、同じ名前のバインドを適用すると、常に、最新のバインドが有効になります。  
  
1.  BizTalk Server によって生成されたアプリケーション バインドのうち、バインド ファイルでアプリケーションに明示的に追加されたバインドではなく、ユーザーがアプリケーション .msi ファイルへのエクスポート対象として明示的に選択したバインド。  
  
2.  明示的に追加されたバインド ファイルのうち、対象の展開環境が指定されていないもの。 この一連のバインド内での適用順序は特に決まっていません。  
  
3.  明示的に追加されたバインドのうち、対象の (アプリケーションのインポート用に選択された展開環境と一致する) 展開環境が関連付けられているもの。 この一連のバインド内での適用順序は特に決まっていません。  
  
 アプリケーションをインポートして、バインドの適用の詳細については、次を参照してください。 [BizTalk アプリケーションをインポート](../core/how-to-import-a-biztalk-application.md)です。  
  
## <a name="prerequisites"></a>前提条件  
BizTalk Server 管理者グループのメンバーであるアカウントでサインインします。 [展開して、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)詳細を示します。
  
## <a name="add-a-binding-file-using-biztalk-administration"></a>BizTalk 管理コンソールを使用してバインド ファイルを追加します。  
  
1.  開いている**BizTalk Server 管理コンソール**([スタート] メニューの)。
  
2.  BizTalk Server 管理コンソールを展開し、BizTalk グループを展開し、アプリケーションを展開およびバインド ファイルを追加するアプリケーションを右クリックします。  
  
3.  をポイント **追加**, 、クリックして **リソース**します。  
  
4.  をクリックして **追加**, 、順にクリックし、追加のファイルを選択して **開く**します。  
  
5.  この同じファイル名を持つアプリケーションで既存のバインド ファイルを上書きするには、選択、 **すべて上書き** チェック ボックスをオンします。 同じ名前の別のファイルが存在し、このチェック ボックスをオンにしない場合、追加の処理は失敗します。  
  
6.  **ファイルの種類** ドロップダウン リストで、 **System.BizTalk:BizTalkBinding**します。  
  
7.  **対象となる環境**, 、テストなどを適用する をクリックしてこのファイルにバインドする対象の展開環境を表す文字列を入力 **OK**します。  
  
    > [!IMPORTANT]
    >  このフィールドを空のままにすると、アプリケーションのインポート時にこのファイルのバインドは常に適用されます。  
  
     バインド ファイルが追加され、アプリケーションのリソース フォルダーに表示されます。  
  
## <a name="add-a-binding-file-using-the-command-line"></a>コマンドラインを使用してバインド ファイルを追加します。  
  
1.  コマンド プロンプトを開きます (**開始**メニュー > 入力`cmd`> 選択**コマンド プロンプト**)。  
  
2.  次の表に示すように適切な値を置き換えて、次のコマンドを入力します。  
  
     **BTSTask AddResource** [**/ApplicationName:"***value***"**] **/Type:System.BizTalk:BizTalkBinding** **[/Overwrite]** **/Source:***value***/Property:TargetEnvironment="***value***"** [**/Server:***value*] [**/Database:***value*]  
  
     例:  
  
     **BTSTask AddResource/applicationname:"My Application"/Type:System.BizTalk:BizTalkBinding/Source:"C:\Binding Files\MyBinding.xml"/Property:TargetEnvironment ="Production"/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |**/Applicationname**|バインド ファイルを追加する BizTalk アプリケーションの名前。 アプリケーション名が指定されなかった場合、既定の BizTalk アプリケーションが使用されます。 名前にスペースが含まれる場合は、二重引用符 (") で囲む必要があります。|  
    |**/型**|**System.BizTalk:BizTalkBinding** (この値は区別されません)。|  
    |**/Overwrite します。**|既存のバインド ファイルを更新するためのオプション。 しない場合は、指定、およびバインド ファイルが追加されるファイルと同じファイル名前を持つアプリケーションに既に存在、AddResource 操作は失敗します。|  
    |**/ソース**|バインド ファイルの完全パス (ファイル名を含む)。 パスにスペースが含まれる場合は、二重引用符 (") で囲む必要があります。|  
    |**/Property:TargetEnvironment =**|対象の展開環境を指定する文字列。 "Production" など、任意の文字列を使用できます。 例: **/Property:TargetEnvironment ="Production"**<br /><br /> 値を指定しない場合\<既定\>が自動的に適用します。 値は、大文字小文字を区別します。 値にスペースが含まれる場合は、二重引用符 (") で囲む必要があります。 環境値の最大長は 128 文字です。|  
    |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
    |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [.NET アセンブリ、証明書、およびその他のリソースの管理](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource コマンド: BizTalk バインド](../core/addresource-command-biztalk-binding.md)   
 [BizTalk アプリケーションの作成と変更](../core/creating-and-modifying-biztalk-applications.md)