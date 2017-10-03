---
title: "証明書の AddResource コマンド: |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e915043-6634-4644-8d69-376d762c7cec
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fc2f1ca82dcd7a91f3572a4db96e9fc75f62839
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="addresource-command-certificate"></a>AddResource コマンド: 証明書
使用する BizTalk アプリケーションにセキュリティ証明書を追加するには**AddResource**コマンドを指定**System.BizTalk:Certificate**型パラメーターです。 このコマンドが適切に機能するためには、ローカル コンピューターの "その他のユーザー" 証明書ストアに証明書が存在している必要があります。  
  
 このコマンドを実行すると、該当する証明書が BizTalk 管理データベースに追加されます。 証明書は、BizTalk Server 管理コンソール (追加先アプリケーションのリソース フォルダー) にも表示されます。 さらに、証明書が使用すると表示されている、 [ListApp コマンド](../core/listapp-command.md)です。  
  
 アプリケーションのインストール時、証明書が、ローカル コンピューターの "その他のユーザー" 証明書ストアにインポートされます。  
  
## <a name="usage"></a>使用方法  
 **BTSTask AddResource** [**/applicationname は:***値*] **/Type:System.BizTalk:Certificate** [**/Overwrite**] **「/Thumbprint」:"***値***"** [**/Server:***値*] [**/Database:***値*]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|値|  
|---------------|--------------|-----------|  
|**/ApplicationName** (または**/A**、「解説」を参照してください)|不可|証明書を追加する BizTalk アプリケーションの名前。 名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。 アプリケーション名が指定されなかった場合、グループの既定の BizTalk アプリケーションが使用されます。|  
|**/入力**(または**/Ty**、「解説」を参照してください)|はい|**System.BizTalk:Certificate** (この値小文字は区別されません)。|  
|**/上書き**(または**/O**、「解説」を参照してください)|不可|既存の証明書を更新するためのオプション。 指定しなかった場合、追加する証明書と同じ拇印 (Thumbprint) プロパティを持つ証明書が既にアプリケーションに存在した場合、追加操作は失敗します。 Thumbprint プロパティは、証明書スナップインで証明書をダブルクリックし、[詳細] タブをクリックして表示できます。詳細については、証明書スナップインのドキュメントで「証明書情報の表示」を参照してください。|  
|**/拇印**(または**/Th**、「解説」を参照してください)|はい|証明書の拇印プロパティ (、*拇印*は、データのダイジェスト)。 この値は、二重引用符 (") で囲む必要があります。|  
|**/サーバー** (または**/S**、「解説」を参照してください)|不可|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
|**/データベース**(または**/D**、「解説」を参照してください)|不可|BizTalk 管理データベースの名前。 指定しないと、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="sample"></a>サンプル  
 **BTSTask AddResource applicationname: myapplication/Type: System.BizTalk:Certificate 上書き「/thumbprint」:"04 a2 8e 32 24 f9 36 b9 42 81 12 71 3a d2 ef db c7 9 c 83 dc"/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>解説  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [AddResource コマンド](../core/addresource-command.md)   
 [アプリケーションに証明書を追加する方法](../core/how-to-add-a-certificate-to-an-application.md)