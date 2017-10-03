---
title: "AddResource コマンド: BizTalk バインド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69c732d3-82c8-4615-b68f-ed29b54ebbf3
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e19e1961293002e8b4169a6fee55708cf3217d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="addresource-command-biztalk-binding"></a>AddResource コマンド: BizTalk バインド
使用する BizTalk アプリケーションにバインド ファイルを追加するには**AddResource**コマンドを指定**System.BizTalk:BizTalkBinding**の**型**パラメーター。 バインド ファイルを追加するときに、展開環境を指定できます。 後でアプリケーションをインポートするときに、この展開環境を選択して、バインドを適用できます。 バインド ファイルはいくつでも BizTalk アプリケーションに追加できます。また、バインド ファイルは、各種の展開環境に合わせてカスタマイズできます。 複数のバインド ファイルを追加するには、追加する各ファイルについて、このコマンドを実行します。  
  
 アセンブリ、アプリケーション、またはグループをエクスポートしたバインド ファイルを追加するには、」の説明に従って[ExportBindings コマンド](../core/exportbindings-command.md)、し、AddResource コマンドを使用して、バインド ファイルをアプリケーションに追加します。  
  
 このコマンドを実行すると、バインド ファイルが BizTalk 管理データベースに追加され、このファイルがアプリケーションの Resources フォルダーに表示されます。 さらに、ファイルが使用すると表示されている、 [ListApp コマンド](../core/listapp-command.md)です。 バインド ファイルをインポートするとは異なり、バインド ファイルの追加はすぐに変更されません既存のバインド。 アプリケーションが他の BizTalk グループにインポートされて初めて、バインドが適用されます。  
  
 バインド ファイルを追加するときに、オプションの /Property パラメーター ("TargetEnvironment") を使用して、バインド ファイルの展開環境を指定できます。 このパラメーターの値に、バインド ファイルの適用先の展開環境を表す任意の文字列 (Test や Production など) を指定できます。 値、/Property パラメーターの値を指定しない場合**\<既定 >**自動的に指定すると、アプリケーションがインポートされるたびに、このバインド ファイルが適用されます。  
  
 このようにして明示的に追加したバインド ファイルが、インポートするアプリケーションに含まれる場合、/Property パラメーターの値を指定することにより、適用するバインド ファイルを選択できます。 バインドは、アプリケーションのインポート時に適用されます。  
  
 インポート プロセスでバインドが適用されるとき、同じ名前を持つ適用済みのバインドは、新しいバインドで上書きされます。 つまり、同じ名前のバインドを適用すると、常に、最新のバインドが有効になります。 複数のバインド ファイルを使用する場合は注意が必要です。 重複するエントリが存在する場合、適用された最新のバインドが有効になります。 アプリケーションをインポートするときに、バインディングは、次の順序で適用されます。  
  
1.  BizTalk Server によって生成されたアプリケーション バインドのうち、バインド ファイルでアプリケーションに明示的に追加されたバインドではなく、ユーザーがアプリケーション .msi ファイルへのエクスポート対象として明示的に選択したバインド。  
  
2.  明示的に追加されたバインド ファイルのうち、対象の展開環境が指定されていないもの。 この一連のバインド内での適用順序は特に決まっていません。  
  
3.  明示的に追加されたバインドのうち、対象の (アプリケーションのインポート用に選択された展開環境と一致する) 展開環境が関連付けられているもの。 この一連のバインド内での適用順序は特に決まっていません。  
  
 詳細については、次を参照してください。[を BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)です。 バインド ファイルの使用に関する背景情報については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)です。  
  
## <a name="usage"></a>使用方法  
 **BTSTask AddResource** [**/applicationname は:"***値***"**] **/Type:System.BizTalk:BizTalkBinding/Property:TargetEnvironment ="***値***"** [**/overwrite**] **/source:***値*[**/Server:***値*] [**/database:***値*]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|値|  
|---------------|--------------|-----------|  
|**/ApplicationName** (または**/A**、「解説」を参照してください)|不可|バインド ファイルを追加する BizTalk アプリケーションの名前。 名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。 アプリケーション名が指定されなかった場合、既定の BizTalk アプリケーションが使用されます。|  
|**/入力**(または**/T**、「解説」を参照してください)|はい|**System.BizTalk:BizTalkBinding** (この値小文字は区別されません)。|  
|**/ソース**(または**/So**、「解説」を参照してください)|はい|バインド ファイルの完全パス (ファイル名を含む)。 パスには、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
|**/Property:TargetEnvironment =** (または**/P:TargetEnvironment =**、「解説」を参照してください)|不可|対象の展開環境を指定する文字列。 "Production" など、任意の文字列を使用できます。 例: **/Property:TargetEnvironment"Production"を =**<br /><br /> 値を指定しない場合**\<既定 >**が自動的に適用します。 値は、大文字小文字を区別します。 値にスペースが含まれる場合は、二重引用符 (") で囲む必要があります。 環境値の最大長は 128 文字です。|  
|**/上書き**(または**/Ov**、「解説」を参照してください)|不可|既存のバインド ファイルを更新するためのオプション。 指定しなかった場合、追加するバインド ファイルと同じ名前のバインド ファイルが既にアプリケーションに存在した場合、AddResource 操作は失敗します。|  
|**/サーバー** (または**/Se**、「解説」を参照してください)|不可|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
|**/データベース**(または**/Da**、「解説」を参照してください)|不可|BizTalk 管理データベースの名前。 指定しないと、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="sample"></a>サンプル  
 **BTSTask AddResource applicationname: myapplication/Type:System.BizTalk:BizTalkBinding/Property:TargetEnvironment = テスト/Source:"C:\Binding Files\MyBinding.xml"/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>解説  
 プロパティ名の大文字と小文字は区別されます。 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [AddResource コマンド](../core/addresource-command.md)   
 [バインド ファイルをアプリケーションに追加する方法](../core/how-to-add-a-binding-file-to-an-application2.md)