---
title: 'AddResource コマンド: .NET アセンブリ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef6ec298-35fe-4845-9549-685993d2c659
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67f20e259611d312429c3bd909a85a3162f1dd64
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="addresource-command-net-assembly"></a>AddResource コマンド: .NET アセンブリ
使用する (マネージ COM コンポーネントまたは COM + コンポーネントを含む) を .NET アセンブリを BizTalk アプリケーションを追加する、 **AddResource** コマンドを指定 **System.BizTalk:Assembly** 、型パラメーターです。 このコマンドを実行すると、該当するアセンブリが BizTalk 管理データベースに追加されます。 このアセンブリは、BizTalk 管理コンソール (追加先アプリケーションの Resources フォルダー) にも表示されます。 さらに、アセンブリが使用すると表示されている、 [ListApp コマンド](../core/listapp-command.md)です。  
  
 アプリケーションに同じ完全名の既存のアセンブリが存在する場合は、Overwrite パラメーターを指定できます。 完全名は、名前、公開キー トークン、カルチャ、およびバージョンから成ります。 この場合、既存のアセンブリは上書きされます。 依存関係に関する詳細については、次を参照してください。[の依存関係とアプリケーションの配置](../core/dependencies-and-application-deployment.md)です。  
  
## <a name="usage"></a>使用方法  
 **BTSTask AddResource** [**/ApplicationName:***value*] **/Type:System.BizTalk:Assembly**[**/Overwrite**] **/Source:***value* [**/Destination:***value*] [**/Options:GacOnAdd***&#124;***GacOnInstall***&#124;***GacOnImport**&#124;**RegasmOnInstall**&#124;**RegsvcsOnInstall**] [**/Server:***value*] [**/Database:***value*]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|値|  
|---------------|--------------|-----------|  
|**/Applicationname** (または **/A**, 、「解説」を参照してください)|いいえ|アセンブリを追加する BizTalk アプリケーションの名前。 名前にスペースが含まれる場合は、二重引用符 (") で囲む必要があります。 アプリケーション名が指定されなかった場合、グループの既定の BizTalk アプリケーションが使用されます。|  
|**/Type** (または **/T**, 、「解説」を参照してください)|はい|**System.BizTalk:Assembly** (この値は区別されません)。|  
|**/Overwrite** (または **/Ov**, 、「解説」を参照してください)|いいえ|既存のアセンブリを更新するためのオプション。 指定しなかった場合、追加するアセンブリと同じ完全名のアセンブリが既にアプリケーションに存在した場合、AddResource 操作は失敗します。 完全名には、アセンブリ名、バージョン、カルチャ、および公開キー トークンが含まれます。 この情報は、BizTalk Server 管理コンソール (アプリケーションのリソース フォルダーの "名前" フィールド) に表示されます。|  
|**/Source** (または **/So**, 、「解説」を参照してください)|はい|アセンブリ ファイルの完全パス (ファイル名を含む)。 パスにスペースが含まれる場合は、二重引用符 (") で囲む必要があります。|  
|**/Destination** (または **/De**, 、「解説」を参照してください)|いいえ|アプリケーションを .msi ファイルからインストールしたときにアセンブリ ファイルがコピーされる場所 (完全パス)。 指定しなかった場合、インストール中、アセンブリ ファイルはローカル ファイル システムにコピーされません。 パスにスペースが含まれる場合は、二重引用符 (") で囲む必要があります。 RegasmOnInstall または RegsvcsOnInstall オプションを指定した場合は、Destination も指定する必要があります。 **注:**  %btad_installdir% 環境変数を使用してアプリケーションのインストール フォルダーを指定することができます。 これにより、一貫性のある別の保存先のコンピューター上のアプリケーションのファイルの場所が作成されます。 例:"%btad_installdir%\myassemblies\orchestrations.dll"|  
|**/Options** (または **/Op**, 、「解説」を参照してください)|いいえ|-   **GacOnAdd**: AddResource 操作中に、ローカル コンピューター上のグローバル アセンブリ キャッシュ (GAC) にアセンブリをインストールします。<br />-   **GacOnInstall**: アプリケーションを .msi ファイルからインストールすると、アセンブリを GAC にインストールします。<br />-   **GacOnImport**: アプリケーションの .msi ファイルをインポートすると、アセンブリを GAC にインストールします。<br />-   **RegasmOnInstall**: アプリケーションを .msi ファイルからインストールすると、Windows レジストリに、マネージ COM アセンブリを追加します。 このオプションを指定した場合は、Destination も指定する必要があります。<br />-   **RegsvcsOnInstall**: .msi ファイルから、アプリケーションがインストールされているときに、マネージ COM + アセンブリを Windows レジストリに追加します。 このオプションを指定した場合は、Destination も指定する必要があります。<br /><br /> 複数のオプションを入力する場合は、コンマで区切って入力します。 コンマと値の間にスペースは挿入しません。|  
|**/サーバー** (または **/Se**, 、「解説」を参照してください)|いいえ|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
|**/Database** (または **/Da**, 、「解説」を参照してください)|いいえ|BizTalk 管理データベースの名前。 指定しないと、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="sample"></a>サンプル  
 **BTSTask AddResource/ApplicationName:MyApplication/Type: System.BizTalk:Assembly/overwrite/Source:"%BTAD_InstallDir%\Source Assemblies\MyAssembly.dll"/Destination:"%BTAD_InstallDir%\New Assemblies\MyAssembly.dll"/Options:GacOnAdd、RegasmOnInstall/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>解説  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [AddResource コマンド](../core/addresource-command.md)   
 [.NET アセンブリをアプリケーションに追加する方法](../core/how-to-add-a-net-assembly-to-an-application.md)