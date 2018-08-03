---
title: 'AddResource コマンド: 前処理スクリプト |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b4f66e5-1f40-4bc3-82a8-c27a0e435797
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29a19b090a0dbdb0b44cca43c6cf86cf2ea74a7e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990939"
---
# <a name="addresource-command-preprocessing-script"></a>AddResource コマンド: 前処理スクリプト
使用する BizTalk アプリケーションには、処理前のスクリプトを追加するには**AddResource**コマンドを指定**System.BizTalk:PreProcessingScript**型パラメーター。 このコマンドを実行すると、該当するスクリプト ファイルが BizTalk 管理データベースに追加されます。 スクリプト ファイルは、BizTalk 管理コンソール (追加先アプリケーションのリソース フォルダー) にも表示されます。 ファイルがさらに、使用すると表示、 [ListApp コマンド](../core/listapp-command.md)します。  
  
 処理前のスクリプトは、アプリケーションのインポート前、インストール前、またはアンインストール後に、.msi ファイルから実行されます。 」の説明に従って、アプリケーションのインポートまたはインストールした後、または、アンインストールの前に実行する処理後のスクリプトを追加する、BTSTask を使用することもできます。 [AddResource コマンド: 処理後のスクリプト](../core/addresource-command-postprocessing-script.md)します。 前処理と後処理スクリプトの詳細については、次を参照してください。[アプリケーション展開のカスタマイズを前処理および後処理のスクリプトを使用して](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)します。  
  
## <a name="usage"></a>使用方法  
 **BTSTask AddResource** [**/applicationname は:**<em>値</em>] **/Type:System.BizTalk:PreProcessingScript****[/Overwrite]** **/Source:**<em>値</em>[**/Destination:**<em>値</em>] [**/Server:** <em>値</em>] [**/database:**<em>値</em>] [**/Property:Args ="**<em>引数リスト</em>**"**]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|値|  
|---------------|--------------|-----------|  
|**/ApplicationName** (または **/A**、「解説」を参照してください)|いいえ|スクリプトを追加する BizTalk アプリケーションの名前。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。 アプリケーション名が指定されなかった場合、グループの既定の BizTalk アプリケーションが使用されます。|  
|**/入力**(または **/T**、「解説」を参照してください)|はい|**System.BizTalk:PreProcessingScript** (この値小文字は区別されません)。|  
|**/上書き**(または **/O**、「解説」を参照してください)|いいえ|既存のスクリプトを更新するためのオプション。 指定しなかった場合、追加するスクリプト ファイルと同じ名前のスクリプト ファイルが既にアプリケーションに存在した場合、追加操作は失敗します。|  
|**/Source** (または **/So**、「解説」を参照してください)|はい|スクリプト ファイルの完全パス (ファイル名を含む)。 パスにスペースがある場合は、二重引用符 (") で囲む必要があります。|  
|**/変換先**(または **/De**、「解説」を参照してください)|いいえ|アプリケーションを .msi ファイルからインストールしたときにスクリプト ファイルがコピーされる場所 (完全パス)。 指定しなかった場合、インストール中、このファイルはローカル ファイル システムにコピーされません。 このスクリプトがアプリケーションのアンインストール時に実行される場合、Destination を指定する必要があります。Destination を指定しなければ、スクリプトはローカル ファイル システムには格納されないので、アンインストール中に実行することはできなくなります。 パスにスペースがある場合は、二重引用符 (") で囲む必要があります。|  
|**/サーバー** (または **/Se**、「解説」を参照してください)|いいえ|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
|**/データベース**(または **/Da**、「解説」を参照してください)|いいえ|BizTalk 管理データベースの名前。 指定されていない場合は、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
|**/プロパティ**(または **/P**、「解説」を参照してください)|いいえ|スクリプトの呼び出し時に、引数として渡されるゼロ個以上のリソース プロパティ。|  
  
## <a name="sample"></a>サンプル  
 **BTSTask AddResource applicationname: myapplication/Type: System.BizTalk:PreProcessingScript/overwrite/Source:"C:\Source Scripts\MyScript.vbs"/Destination:"C:\New Scripts\MyScript.vbs"/Server:MyDatabaseServer/Database:BizTalkMgmtDb/Property:Args =「[引数 1] [引数 2]」**  
  
## <a name="remarks"></a>コメント  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
 スクリプト ファイルの次の拡張機能がサポートされています: .com、.exe、.bat、.cmd、.vbs、.vbe、.js、.jse、.wsf、.wsh です。  
  
## <a name="see-also"></a>参照  
 [AddResource コマンド](../core/addresource-command.md)   
 [処理前または処理後のスクリプトをアプリケーションに追加する方法](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)