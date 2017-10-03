---
title: "AddResource コマンド: 前処理スクリプト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b4f66e5-1f40-4bc3-82a8-c27a0e435797
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5255bfa0bfe73941b69d8e6b95f2230a9dfbd85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="addresource-command-preprocessing-script"></a>AddResource コマンド: 前処理スクリプト
使用する BizTalk アプリケーションに処理前のスクリプトを追加するには**AddResource**コマンドを指定**System.BizTalk:PreProcessingScript**型パラメーターです。 このコマンドを実行すると、該当するスクリプト ファイルが BizTalk 管理データベースに追加されます。 スクリプト ファイルは、BizTalk 管理コンソール (追加先アプリケーションのリソース フォルダー) にも表示されます。 さらに、ファイルが使用すると表示されている、 [ListApp コマンド](../core/listapp-command.md)です。  
  
 処理前のスクリプトは、アプリケーションのインポート前、インストール前、またはアンインストール後に、.msi ファイルから実行されます。 BTSTask を使用して」の説明に従って、アプリケーションのインポートや、インストール後、または、アンインストールの前に実行する処理後のスクリプトを追加する[AddResource コマンド: 処理後のスクリプト](../core/addresource-command-postprocessing-script.md)です。 前処理および後処理スクリプトに関する詳細については、次を参照してください。[前処理および後処理のスクリプトをアプリケーションの展開のカスタマイズを使用して](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)です。  
  
## <a name="usage"></a>使用方法  
 **BTSTask AddResource** [**/applicationname は:***値*] **/Type:System.BizTalk:PreProcessingScript**[**/Overwrite**]**/Source:***値*[**/Destination:***値*] [**/Server:** *値*] [**/database:***値*] [**/Property:Args ="***引数リスト***"**]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|値|  
|---------------|--------------|-----------|  
|**/ApplicationName** (または**/A**、「解説」を参照してください)|不可|スクリプトを追加する BizTalk アプリケーションの名前。 名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。 アプリケーション名が指定されなかった場合、グループの既定の BizTalk アプリケーションが使用されます。|  
|**/入力**(または**/T**、「解説」を参照してください)|はい|**System.BizTalk:PreProcessingScript** (この値小文字は区別されません)。|  
|**/上書き**(または**/O**、「解説」を参照してください)|不可|既存のスクリプトを更新するためのオプション。 指定しなかった場合、追加するスクリプト ファイルと同じ名前のスクリプト ファイルが既にアプリケーションに存在した場合、追加操作は失敗します。|  
|**/ソース**(または**/So**、「解説」を参照してください)|はい|スクリプト ファイルの完全パス (ファイル名を含む)。 パスにスペースがある場合は、二重引用符 (") で囲む必要があります。|  
|**/送信先**(または**/De**、「解説」を参照してください)|不可|アプリケーションを .msi ファイルからインストールしたときにスクリプト ファイルがコピーされる場所 (完全パス)。 指定しなかった場合、インストール中、このファイルはローカル ファイル システムにコピーされません。 このスクリプトがアプリケーションのアンインストール時に実行される場合、Destination を指定する必要があります。Destination を指定しなければ、スクリプトはローカル ファイル システムには格納されないので、アンインストール中に実行することはできなくなります。 パスにスペースがある場合は、二重引用符 (") で囲む必要があります。|  
|**/サーバー** (または**/Se**、「解説」を参照してください)|不可|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
|**/データベース**(または**/Da**、「解説」を参照してください)|不可|BizTalk 管理データベースの名前。 指定しないと、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
|**/プロパティ**(または**/P**、「解説」を参照してください)|不可|スクリプトの呼び出し時に、引数として渡されるゼロ個以上のリソース プロパティ。|  
  
## <a name="sample"></a>サンプル  
 **BTSTask AddResource applicationname: myapplication/Type: System.BizTalk:PreProcessingScript/overwrite/Source:"C:\Source Scripts\MyScript.vbs"/Destination:"C:\New Scripts\MyScript.vbs"/Server:MyDatabaseServer/Database:BizTalkMgmtDb/Property:Args =「[引数 1] 引数 2」**  
  
## <a name="remarks"></a>解説  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
 スクリプト ファイルの次の拡張機能がサポートされている: .com、.exe、.bat、.cmd、.vbs、.vbe、.js、.jse、.wsf、.wsh です。  
  
## <a name="see-also"></a>参照  
 [AddResource コマンド](../core/addresource-command.md)   
 [前または処理後のスクリプトをアプリケーションに追加する方法](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)