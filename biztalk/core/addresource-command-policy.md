---
title: 'AddResource コマンド: ポリシー |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f5effcbe-bf53-4741-8d5e-227620d4d84d
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43b90d74a177d11b478aff3302aa31306188cbcd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993659"
---
# <a name="addresource-command-policy"></a>AddResource コマンド: ポリシー
使用するポリシーを BizTalk アプリケーションを追加する、 **AddResource**コマンドを指定**System.BizTalk:Rules**型パラメーター。 このコマンドを実行すると、該当するポリシーが BizTalk 管理データベースに追加されます。 ポリシーは、BizTalk Server 管理コンソール (追加先アプリケーションのポリシー フォルダー) にも表示されます。 さらにのポリシーを使用する場合に表示される、 [ListApp コマンド](../core/listapp-command.md)します。  
  
 このコマンドが正常に機能するためには、ルール エンジン データベースにポリシーが存在していることが必要です。 ルール エンジン データベースにポリシーをインポートする方法の詳細については、[ポリシーをインポートする方法](../core/how-to-import-a-policy.md)を参照してください。 AddResource コマンドを使ってポリシーを追加した場合、ポリシーで使用されているボキャブラリもすべて自動的に追加されます。  
  
## <a name="usage"></a>使用方法  
 **BTSTask AddResource** [**/applicationname は:**<em>値</em>] **/Type:System.BizTalk:Rules** **[/overwrite]** **/Name:**<em>値</em>**/Version:**<em>値</em>[**/Server:**<em>値</em>] [**/Database:**<em>値</em>]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|値|  
|---------------|--------------|-----------|  
|**/ApplicationName** (または **/A**、「解説」を参照してください)|いいえ|ポリシーを追加する BizTalk アプリケーションの名前。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。 アプリケーション名が指定されなかった場合、グループの既定の BizTalk アプリケーションが使用されます。|  
|**/入力**(または **/T**、「解説」を参照してください)|はい|**System.BizTalk:Rules** (この値小文字は区別されません)。|  
|**/上書き**(または **/O**、「解説」を参照してください)|いいえ|既存のポリシーを更新するためのオプション。 指定しなかった場合、追加するポリシーと同じ名前のポリシーが既にアプリケーションに存在した場合、AddResource 操作は失敗します。|  
|**/名前**(または **/N**、「解説」を参照してください)|はい|ポリシーの名前。|  
|**/Version** (または **/V**、「解説」を参照してください)|はい|ポリシーのバージョン番号 (ピリオド区切りの数値形式)。<br /><br /> 例: 1.0|  
|**/サーバー** (または **/S**、「解説」を参照してください)|いいえ|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
|**/データベース**(または **/D**、「解説」を参照してください)|いいえ|BizTalk 管理データベースの名前。 指定されていない場合は、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="sample"></a>サンプル  
 **BTSTask AddResource applicationname: myapplication/Type: System.BizTalk:Rules/overwrite/Name:MyPolicy/Version:1.0/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>コメント  
 MyPolicy が展開されている場合は、上記のコマンドから次のメッセージが返されます。  
  
 エラー: は、リソースの追加に失敗しました。  
  
 1 リソースの検証に失敗しました。  
  
 ルール ポリシー "MyPolicy" のバージョン 1.0 は既に実稼働状態にあるため、上書きできません。  
  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [AddResource コマンド](../core/addresource-command.md)   
 [アプリケーションにポリシーを追加する方法](../core/how-to-add-a-policy-to-an-application.md)