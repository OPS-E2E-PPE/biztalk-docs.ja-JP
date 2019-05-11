---
title: ExportApp コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6217d0f1-cf39-4520-87c8-8d25b21865af
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93d613f3e32c3dd592fc84bb05121f7256e6faa5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388305"
---
# <a name="exportapp-command"></a>ExportApp コマンド
BizTalk アプリケーションを .msi ファイルにエクスポートします。 同じファイル名とパスを既に持つ .msi ファイルが存在する場合は、既存の .msi ファイルが上書きされます。  
  
 ResourceSpec パラメーターを使用して、.msi ファイルにアプリケーションでアイテムを選択的にエクスポートすることができます。 XML ファイルを編集してエクスポートするアイテムの作成を実行するときに指定する、 **ListApp**で説明されているコマンドを ResourceSpec パラメーターと共に[ListApp コマンド](../core/listapp-command.md)します。 場所を使用する、この XML ファイルの ResourceSpec の値として実行するときに、 **ExportApp**コマンド。 これを行う場合は、指定した XML ファイルに表示されている成果物のみが、.msi ファイルにエクスポートされます。  
  
> [!NOTE]
>  セキュリティ上の理由により、パスワードは、アプリケーションのエクスポート中にアプリケーションのバインドから削除されます。 アプリケーションに追加されたバインド ファイルからは削除されません。 .Msi ファイルからアプリケーションをインストールした後は、アプリケーションが機能するためにパスワードを再構成する必要があります。  
>   
>  さらに、秘密キーは、証明書ファイルから削除されます。  
  
## <a name="usage"></a>使用方法  
 **BTSTask の ExportApp** [**/applicationname は:**<em>値</em>] **/package:**<em>値</em>[**/ResourceSpec:**<em>値</em>] **[/GlobalParties]** [**/Server:**<em>値</em>] [**/database:** <em>値</em>]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|値|  
|---------------|--------------|-----------|  
|**/ApplicationName** (または **/A**、「解説」を参照してください)|いいえ|エクスポートする BizTalk アプリケーションの名前。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。 アプリケーション名が指定されなかった場合、グループの既定の BizTalk アプリケーションが使用されます。|  
|**/パッケージ**(または **/P**、「解説」を参照してください)|はい|.msi ファイルの完全パス。 パスにスペースが含まれている場合は、引用符 (") で囲む必要があります。 例:Package:"C:\My MSI Files\My.msi"|  
|**/ResourceSpec** (または **/R**、「解説」を参照してください)|いいえ|リソース仕様ファイルの完全パス。 パスにスペースが含まれている場合は、引用符 (") で囲む必要があります。 例:ResourceSpec:"C:\My Files\MyResourceSpec.xml"|  
|**/GlobalParties** (または **/G**、「解説」を参照してください)|いいえ|指定した場合、グループのグローバル パーティ情報が .msi ファイルにエクスポートされます。|  
|**/サーバー** (または **/S**、「解説」を参照してください)|いいえ|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
|**/データベース**(または **/D**、「解説」を参照してください)|いいえ|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="sample"></a>サンプル  
 **ExportApp /ApplicationName:MyApplication /Package:C:\MSI\MyApplication.msi**  
  
## <a name="remarks"></a>コメント  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)   
 [BizTalk アプリケーションをエクスポートする方法](../core/how-to-export-a-biztalk-application.md)