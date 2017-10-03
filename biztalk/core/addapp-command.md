---
title: "AddApp コマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 445784f1-505b-4259-a3f4-6f0d61578b1c
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a6b91faa406181db3e4195bf57baeb086a0b69e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="addapp-command"></a>AddApp コマンド
BizTalk 管理データベースに新しい BizTalk アプリケーションを作成します。 作成したアプリケーションは、BizTalk Server 管理コンソールの [アプリケーション] ノードに表示されます。 ことができますにアイテムを追加、アプリケーション、AddResource コマンドを使用して」の説明に従って[AddResource コマンド](../core/addresource-command.md)です。  
  
## <a name="usage"></a>使用方法  
 **BTSTask AddApp/applicationname は:** *値*[**/Description:***値*] [**/既定**] [**/サーバー:***値*] [**/database:***値*]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|値|  
|---------------|--------------|-----------|  
|**/ApplicationName** (または**/A**、「解説」を参照してください)|はい|追加する BizTalk アプリケーションの名前。 アプリケーション名には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
|**/既定**(または**/Def**、「解説」を参照してください)|不可|指定した場合、BizTalk グループの既定のアプリケーションになります。|  
|**/説明**(または**/Des**、「解説」を参照してください)|不可|アプリケーションの説明です。 二重引用符 (") で囲む必要があります。|  
|**/サーバー** (または**/S**、「解説」を参照してください)|不可|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
|**/データベース**(または**/Da**、「解説」を参照してください)|不可|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="sample"></a>サンプル  
 **AddApp applicationname: myapplication/Description:"My BizTalk application"**  
  
## <a name="remarks"></a>解説  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)   
 [アプリケーションを作成する方法](../core/how-to-create-an-application.md)