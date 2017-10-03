---
title: "AddResource コマンド: BizTalk アセンブリ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c18607b5-d929-48c9-9fa3-f728a7a80d04
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94cf353abb1e601a14c9e2f081fa2946f1e3ed24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="addresource-command-biztalk-assembly"></a>AddResource コマンド: BizTalk アセンブリ
使用する BizTalk アプリケーションに BizTalk アセンブリを追加するには**AddResource**コマンドを指定**System.BizTalk:BizTalkAssembly**型パラメーターです。 このコマンドを実行すると、該当するアセンブリが BizTalk 管理データベースに追加されます。 アセンブリは、BizTalk Server 管理コンソール (追加先アプリケーションのリソース フォルダー) にも表示されます。 また、アセンブリに含まれているアイテムが個々のフォルダーに表示されます。 使用するときにさらに、アイテムが一覧表示、 [ListApp コマンド](../core/listapp-command.md)です。  
  
 このコマンドを使用する場合は、次の点に注意する必要があります。  
  
-   アプリケーションに同じ完全名の既存のアセンブリが存在する場合は、Overwrite パラメーターを指定する必要があります。指定しないと、AddResource 操作は失敗します。 完全名は、名前、公開キー トークン、カルチャ、およびバージョンから成ります。 ただし、他のアプリケーションがこのアセンブリに依存している場合、Overwrite パラメーターを指定したかどうかに関係なく AddResource 操作は失敗します。  
  
-   グループに同じ完全名の既存のアセンブリがあった場合、Overwrite パラメーターを指定したかどうかに関係なく AddResource 操作は失敗します。  
  
-   オーケストレーションを含むアセンブリを上書きする場合、このコマンドを実行する前に、そのオーケストレーションを停止し、参加解除しておく必要があります。 また、オーケストレーションがバインドされている送信ポートを停止および参加解除し、受信場所を無効にする必要があります。  
  
-   また、追加するアセンブリが、そのアプリケーションには含まれない他のアイテムに依存している場合、AddResource 操作は失敗します。  
  
 依存関係に関する詳細については、次を参照してください。[の依存関係とアプリケーションの配置](../core/dependencies-and-application-deployment.md)です。  
  
## <a name="usage"></a>使用方法  
 **BTSTask AddResource** [**/applicationname は:***値*] **/Type:System.BizTalk:BizTalkAssembly** [**/Overwrite**] **/Source:***値*[**/Destination:***値*] [**/Options:GacOnAdd** *&#124;***Gaconinstall です***&#124;***GacOnImport**] [**/Server:***値*] [**/database:***値*]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|値|  
|---------------|--------------|-----------|  
|**/ApplicationName** (または**/A**、「解説」を参照してください)|不可|アセンブリを追加する BizTalk アプリケーションの名前。 名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。 アプリケーション名が指定されなかった場合、既定の BizTalk アプリケーションが使用されます。|  
|**/入力**(または**/T**、「解説」を参照してください)|はい|**System.BizTalk:BizTalkAssembly** (この値小文字は区別されません)。|  
|**/上書き**(または**/Ov**、「解説」を参照してください)|不可|既存のアセンブリを更新するためのオプション。 指定しなかった場合、追加するアセンブリと同じ完全名のアセンブリが既にアプリケーションに存在した場合、AddResource 操作は失敗します。 完全名は、アセンブリのローカル一意識別子 (LUID) に対応しています。 使用してアプリケーション内のアイテムの Luid を表示することができます、 [ListApp コマンド](../core/listapp-command.md)です。 他のアプリケーションが、上書きされようとしているアセンブリに依存している場合、このパラメーターを指定したとしても AddResource 操作は失敗します。|  
|**/ソース**(または**/So**、「解説」を参照してください)|はい|アセンブリ ファイルの完全パス (ファイル名を含む)。 パスには、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
|**/送信先**(または**/De**、「解説」を参照してください)|不可|アプリケーションを .msi ファイルからインストールしたときにアセンブリ ファイルがコピーされる場所 (完全パス)。 指定しなかった場合、インストール中、アセンブリ ファイルはローカル ファイル システムにコピーされません。 パスには、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。 **注:**アプリケーションのインストール フォルダーを指定する、環境変数 %btad_installdir%、BizTalk Server のインストール時に設定すると、これを行うこともできます。 アプリケーション ファイルがインストールされるコンピューターには、さまざまなフォルダー構造が考えられます。環境変数を使用することにより一貫した場所を指定できます。 例:"%btad_installdir%\myfiles\orchestrations.dll"|  
|**/オプション**(または**/Op**、「解説」を参照してください)|不可|-   **GacOnAdd**: AddResource 操作中に、アセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールするローカル コンピューターを指定します。<br />-   **Gaconinstall です**: アプリケーションを .msi ファイルからインストールすると、GAC にアセンブリをインストールするように指定します。<br />-   **GacOnImport**: アプリケーションの .msi ファイルをインポートするときに、GAC にアセンブリをインストールするように指定します。<br /><br /> 複数のオプションを入力する場合は、コンマで区切って入力します。|  
|**/サーバー** (または**/Se**、「解説」を参照してください)|不可|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
|**/データベース**(または**/Da**、「解説」を参照してください)|不可|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="sample"></a>サンプル  
 **BTSTask AddResource applicationname: myapplication/Type:System.BizTalk:BizTalkAssembly/overwrite**  
  
 **/Source:"%BTAD_InstallDir%\Source Assemblies\Orchestrations.dll"/Destination:"%BTAD_InstallDir%\New Assemblies\Orchestrations.dll"/Options:GacOnInstall、GacOnImport/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>解説  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [AddResource コマンド](../core/addresource-command.md)   
 [BizTalk アセンブリをアプリケーションに追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)