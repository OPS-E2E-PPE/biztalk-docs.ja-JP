---
title: アプリケーションに COM コンポーネントを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], COM components
- managing [resources], COM components
- applications, COM components
- COM components, applications
ms.assetid: fdda1a9d-96af-41fe-9d94-ee1fbd80a7c9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0860fcd21f6a83dd6ce952976e04c5680613673b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387351"
---
# <a name="how-to-add-a-com-component-to-an-application"></a>アプリケーションに COM コンポーネントを追加する方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンドラインを使用して BizTalk アプリケーションに COM コンポーネントを追加する方法について説明します。  
  
 COM コンポーネントをアプリケーションに追加すると、次の重要な点に注意してください。  
  
-   アプリケーションに既に存在する COM コンポーネントを上書きする場合は、上書きオプションを指定します。 上書きオプションが両方のアイテムがある同じローカル一意識別子 (LUID) 場合にのみ必要です。 指定されていない場合、COM コンポーネントが追加されるものと同じ LUID を持つアプリケーションに既に存在します、追加操作は失敗します。 アプリケーションのアイテムの Luid を表示するにを使用して、 [ListApp コマンド](../core/listapp-command.md)します。  
  
-   BizTalk Server では、それらが存在する、コンポーネントが依存する任意のアイテムが存在することを確認する必要がありますのでことを確認する COM コンポーネントの依存関係をチェックしません。  
  
-   64 ビット アンマネージ COM または COM + コンポーネントを追加する 32 ビット コンピューターで COM または COM + コンポーネントを含むアプリケーションをインストールしようとした場合は、コンポーネントはインストールされません。 64 ビット コンピューターにのみインストールされます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
## <a name="to-add-a-com-component-to-an-application"></a>アプリケーションに COM コンポーネントを追加するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1. クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで BizTalk Server 管理コンソールを展開し、BizTalk グループを展開、アプリケーションを展開し、COM コンポーネントを追加するアプリケーションを展開します。  
  
3. 右クリックし、**リソース**フォルダーをポイントして**追加**、 をクリックし、**リソース**します。  
  
4. クリックして**追加**COM コンポーネントを選択し、クリックして**オープン**します。  
  
5. **ファイルの種類**ドロップダウン リストでは、をクリックして**System.BizTalk:Com**します。  
  
6. **オプション**、オンまたはオフ、 **(regsvr32) 転送先にファイルを登録**に従って、アプリケーションが Windows レジストリに追加するコンポーネントを希望するかどうかのチェック ボックスインストールされています。  
  
7. **先**、COM コンポーネントが、ファイル名を含む .msi ファイルから、アプリケーションのインストール時にコピーする場所の完全なパスを入力します。 このパスを指定しないと、インストールでローカル ファイル システムにファイルがコピーされません。 選択した場合は、このパスが必要です、 **(regsvr32) 転送先にファイルを登録**前の手順でチェック ボックス。  
  
    例: **%BTAD_InstallDir%\MyComponent.dll**  
  
8. 完了したら、 **[OK]** をクリックします。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1. 次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。  
  
2. 次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
    **BTSTask AddResource** [**/applicationname は:**<em>値</em>] **/Type:System.BizTalk:Com** **[/overwrite]** **/Source:**<em>値</em>[**/Destination:**<em>値</em>] [**/Options:Regsvr32OnInstall**[**/Server:**<em>値</em>] [**/database:**<em>値</em>]  
  
    例:  
  
    **BTSTask AddResource applicationname: myapplication/Type:System.BizTalk:Com/overwrite/Source:"C:\Source Components\COM.dll"/Destination:"C:\New Components\COM.dll"/Options:Regsvr32OnInstall/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
   |パラメーター|値|  
   |---------------|-----------|  
   |**/ApplicationName**|COM コンポーネントを追加する BizTalk アプリケーションの名前。 アプリケーション名が指定されなかった場合、グループの既定の BizTalk アプリケーションが使用されます。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
   |**/Type**|**System.BizTalk:Com** (この値小文字は区別されません)。|  
   |**/Overwrite**|既存の COM コンポーネントを更新するオプション。 指定しない場合とを追加する COM コンポーネント、AddResource 操作は失敗と同じ LUID を持つアプリケーションで COM コンポーネントが既に存在します。 アプリケーションのアイテムの Luid を表示するにを使用して、 [ListApp コマンド](../core/listapp-command.md)します。|  
   |**/ソース**|ファイル名を含む、COM コンポーネントの .dll ファイルの完全パス。 パスにスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
   |**/変換先**|COM コンポーネントの .dll ファイルが .msi ファイルから、アプリケーションのインストール時にコピーする場所の完全パス。 インストール時に、ローカル ファイル システムにファイルがコピーされませんが、指定されない場合そのため、インストール中に、Windows レジストリにコンポーネントを追加できません。 パスにスペースが含まれている場合は、二重引用符 (") で囲む必要があります。 Regsvr32OnInstallOption を指定する場合は、Destination も指定する必要があります。|  
   |**/オプション**|**Regsvr32OnInstall します。** .Msi ファイルから、アプリケーションがインストールされているときに、Windows レジストリに COM コンポーネントを追加するを指定します。 このオプションを指定した場合は、Destination も指定する必要があります。|  
   |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
   |**/Database**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [.NET アセンブリ、証明書、およびその他のリソースを管理します。](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource コマンド:COM コンポーネント](../core/addresource-command-com-component.md)   
 [BizTalk アプリケーションの作成と変更](../core/creating-and-modifying-biztalk-applications.md)