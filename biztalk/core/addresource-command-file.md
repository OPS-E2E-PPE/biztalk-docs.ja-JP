---
title: "AddResource コマンド: ファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9635e43-af26-48d3-af0e-df245a8955e7
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92ed0b99c942adbb63fd7ca3bd2e29cc1ba040c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="addresource-command-file"></a>AddResource コマンド: ファイル
使用する BizTalk アプリケーションにファイルを追加するには**AddResource**コマンドを指定**System.BizTalk:File**型パラメーターです。 このコマンドを実行すると、該当するファイルが BizTalk 管理データベースに追加されます。 このファイルは、BizTalk 管理コンソール (追加先アプリケーションのリソース フォルダー) にも表示されます。 さらに、ファイルが使用すると表示されている、 [ListApp コマンド](../core/listapp-command.md)です。  
  
## <a name="usage"></a>使用方法  
 **BTSTask AddResource** [**/applicationname は:***値*] **/Type:System.BizTalk:File** [**/overwrite**] **/Source:***値*[**/Destination:***値*] [**/Server:** *値*] [**/database:***値*]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|値|  
|---------------|--------------|-----------|  
|**/ApplicationName** (または**/A**、「解説」を参照してください)|不可|ファイルを追加する BizTalk アプリケーションの名前。 パスには、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。 アプリケーション名が指定されなかった場合、既定の BizTalk アプリケーションが使用されます。|  
|**/入力**(または**/T**、「解説」を参照してください)|はい|**System.BizTalk:File** (この値小文字は区別されません)。|  
|**/上書き**(または**/O**、「解説」を参照してください)|不可|既存のファイルを更新するためのオプション。 指定しなかった場合、追加するファイルと同じ名前のファイルが既にアプリケーションに存在した場合、AddResource 操作は失敗します。|  
|**/ソース**(または**/So**、「解説」を参照してください)|はい|ファイルの完全パス (ファイル名を含む)。 パスには、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
|**/送信先**(または**De**、「解説」を参照してください)|不可|アプリケーションを .msi ファイルからインストールしたときにファイルがコピーされる場所 (完全パス)。 パスには、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。 指定しなかった場合、インストール中、このファイルはローカル ファイル システムにコピーされません。|  
|**/サーバー** (または**/Se**、「解説」を参照してください)|不可|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
|**/データベース**(または**/Da**、「解説」を参照してください)|不可|BizTalk 管理データベースの名前。 指定しないと、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="sample"></a>サンプル  
 **BTSTask AddResource applicationname: myapplication/Type: System.BizTalk:File/overwrite/Source:"C:\Source Files\File.txt"/Destination:"C:\New Files\File.txt"/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>解説  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [AddResource コマンド](../core/addresource-command.md)   
 [.NET アセンブリをアプリケーションに追加する方法](../core/how-to-add-a-net-assembly-to-an-application.md)