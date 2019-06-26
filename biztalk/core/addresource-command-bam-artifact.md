---
title: AddResource コマンド:BAM アイテム |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a9de7a82-9b06-4d50-9678-73140e80d0af
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc71e95bf1b78f6598c584031e0ab5dc10aaa614
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360720"
---
# <a name="addresource-command-bam-artifact"></a>AddResource コマンド:BAM アイテム
使用する BAM アイテムを BizTalk アプリケーションを追加する、 **AddResource**コマンドを指定**System.BizTalk:Bam**型パラメーター。 このコマンドを実行すると、BizTalk 管理データベースに BAM アイテム ファイルが追加されます。 BAM アイテムは、BizTalk Server 管理コンソールで、追加したアプリケーションのリソース フォルダーにも表示されます。 ファイルがさらに、使用すると表示、 [ListApp コマンド](../core/listapp-command.md)します。  
  
 AddResource コマンドを使用して BAM 定義を追加する BAM 定義をデプロイしません。 BAM 定義を含む .msi ファイルをインポート ウィザードを使用して、アプリケーションにインポートすると、ただし、BAM 定義は、ローカル コンピューターにデプロイされます。  
  
## <a name="usage"></a>使用方法  
 **BTSTask AddResource** [**/applicationname は:**<em>値</em>] **/Type:System.BizTalk:Bam**[**/overwrite**] **/Source:**<em>値</em>[**/Destination:**<em>値</em>] [**/Server:** <em>値</em>] [**/database:**<em>値</em>]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|値|  
|---------------|--------------|-----------|  
|**/ApplicationName** (または **/A**、「解説」を参照してください)|いいえ|BAM アイテムを追加する BizTalk アプリケーションの名前。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。 アプリケーション名が指定されなかった場合、グループの既定の BizTalk アプリケーションが使用されます。|  
|**/入力**(または **/T**、「解説」を参照してください)|はい|**System.BizTalk:Bam** (この値小文字は区別されません)。|  
|**/上書き**(または **/O**、「解説」を参照してください)|いいえ|既存の BAM アイテムを更新するオプション。 指定しない場合、追加する BAM アイテム、AddResource 操作は失敗と同じ名前を持つアプリケーションで成果物が既に存在します。|  
|**/Source** (または **/So**、「解説」を参照してください)|はい|ファイル名を含む、BAM アイテム ファイルの完全パス。 パスにスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
|**/変換先**(または**De**、「解説」を参照してください)|いいえ|BAM アイテム ファイルが .msi ファイルから、アプリケーションのインストール時にコピーする場所の完全パス。 指定しなかった場合、インストール中、このファイルはローカル ファイル システムにコピーされません。 パスにスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
|**/サーバー** (または **/Se**、「解説」を参照してください)|いいえ|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
|**/データベース**(または **/Da**、「解説」を参照してください)|いいえ|BizTalk 管理データベースの名前。 指定されていない場合は、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="sample"></a>サンプル  
 **BTSTask AddResource applicationname: myapplication/Type:System.BizTalk:Bam   /Overwrite /Source:"C:\Source BAMfiles\MyBAMfile.xml" /Destination:"C:\New BAMfiles\MyBAMfile.xml" /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>コメント  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [AddResource コマンド](../core/addresource-command.md)   
 [アプリケーションに BAM アイテムを追加する方法](../core/how-to-add-a-bam-artifact-to-an-application.md)