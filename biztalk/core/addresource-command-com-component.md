---
title: AddResource コマンド:COM コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 86a4f2fc-bbbe-4b4a-8008-2c79b3ebb6a1
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0aabd3968c416b97b7a8f9dc89548313d97156b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360684"
---
# <a name="addresource-command-com-component"></a>AddResource コマンド:COM コンポーネント
使用する BizTalk アプリケーションには、アンマネージ COM コンポーネントを追加するには**AddResource**コマンドを指定**System.BizTalk:Com**型パラメーター。 このコマンドを実行すると、BizTalk 管理データベースに COM コンポーネントが追加されます。 COM コンポーネントは、BizTalk 管理コンソールで、追加したアプリケーションのリソース フォルダーにも表示されます。 使用するとさらに、コンポーネントが一覧表示、 [ListApp コマンド](../core/listapp-command.md)します。  
  
> [!NOTE]
>  64 ビット アンマネージ COM または COM + コンポーネントを追加する 32 ビット コンピューターで COM または COM + コンポーネントを含むアプリケーションをインストールしようとした場合は、コンポーネントはインストールされません。 64 ビット コンピューターにのみインストールされます。  
  
## <a name="usage"></a>使用方法  
 **BTSTask AddResource** [**/applicationname は:**<em>値</em>] **/Type:System.BizTalk:Com** **[/overwrite]** **/Source:**<em>値</em>[**/Destination:**<em>値</em>] [**/Options:Regsvr32OnInstall**[**/Server:**<em>値</em>] [**/database:**<em>値</em>]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|値|  
|---------------|--------------|-----------|  
|**/ApplicationName** (または **/A**、「解説」を参照してください)|いいえ|COM コンポーネントを追加する BizTalk アプリケーションの名前。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。 アプリケーション名が指定されなかった場合、グループの既定の BizTalk アプリケーションが使用されます。|  
|**/入力**(または **/T**、「解説」を参照してください)|はい|**System.BizTalk:Com** (この値小文字は区別されません)。|  
|**/上書き**(または **/Ov**、「解説」を参照してください)|いいえ|既存の COM コンポーネントを更新するオプション。 指定されていない場合、追加される COM コンポーネント、AddResource 操作は失敗として同じファイル名を持つアプリケーションで COM コンポーネントが既に存在します。|  
|**/Source** (または **/So**、「解説」を参照してください)|はい|ファイル名を含む、COM コンポーネントの .dll ファイルの完全パス。 パスにスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
|**/変換先**(または **/De**、「解説」を参照してください)|いいえ|COM コンポーネントの .dll ファイルが .msi ファイルから、アプリケーションのインストール時にコピーする場所の完全パス。 インストール時に、ローカル ファイル システムにファイルがコピーされませんが、指定されない場合そのため、インストール中に、Windows レジストリにコンポーネントを追加できません。 パスにスペースが含まれている場合は、二重引用符 (") で囲む必要があります。 Regsvr32OnInstallOption を指定する場合は、Destination も指定する必要があります。|  
|**/オプション**(または **/Op**、「解説」を参照してください)|いいえ|**Regsvr32OnInstall します。** .Msi ファイルから、アプリケーションがインストールされているときに、Windows レジストリに COM コンポーネントを追加するを指定します。 このオプションを指定した場合は、Destination も指定する必要があります。|  
|**/サーバー** (または **/Se**、「解説」を参照してください)|いいえ|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
|**/データベース**(または **/Da**、「解説」を参照してください)|いいえ|BizTalk 管理データベースの名前。 指定されていない場合は、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="sample"></a>サンプル  
 **BTSTask AddResource applicationname: myapplication/Type:System.BizTalk:Com  /Overwrite /Source:"C:\Source Components\COM.dll" /Destination:"C:\New Components\COM.dll" /Options:Regsvr32OnInstall /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>コメント  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [AddResource コマンド](../core/addresource-command.md)   
 [.NET アセンブリをアプリケーションに追加する方法](../core/how-to-add-a-net-assembly-to-an-application.md)