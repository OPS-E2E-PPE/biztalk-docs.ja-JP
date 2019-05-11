---
title: BizTalk アセンブリをアプリケーションに追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], adding assemblies
- assemblies, applications
- managing [assemblies], adding to applications
- applications, assemblies
- managing [assemblies], applications
ms.assetid: 1525a0f6-cb0f-43bf-a851-40c06ab2135e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3abf79f4c205e336704a40dc885a3645aa354591
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387410"
---
# <a name="how-to-add-a-biztalk-assembly-to-an-application"></a>BizTalk アセンブリをアプリケーションに追加する方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンドラインを使用して、BizTalk アセンブリをアプリケーションに追加する方法について説明します。  
  
 BizTalk アセンブリをアプリケーションに追加すると、次の重要な点に注意してください。  
  
-   アセンブリを追加して、アプリケーションに既に存在する同じローカル一意識別子 (LUID) でアセンブリを上書きする場合は、上書きオプションを指定します。 指定しない場合と同じ LUID を持つアセンブリ、操作は失敗、アプリケーションに既に追加されているアセンブリが存在します。 LUID には、アセンブリ ファイル名、バージョン、カルチャ、および公開キー トークンが含まれています。 アプリケーションのアイテムの Luid を表示するにを使用して、 [ListApp コマンド](../core/listapp-command.md)します。  
  
-   アプリケーションが含まれていない別のアイテムに依存しているアセンブリを追加して、追加操作は失敗します。  
  
-   BizTalk アセンブリを追加する場合は、1 つ以上のアセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールするために、次のオプションを指定できます。  
  
    -   **グローバル アセンブリ キャッシュへの追加に (gacutil) のリソースを追加します。** このオプションを選択すると、アセンブリは、このトピックの手順を使用した結果として、アプリケーションにアセンブリが追加されたときに、ローカル コンピューターの GAC にインストールされます。  
  
    -   **MSI ファイルのインポート (gacutil) のグローバル アセンブリ キャッシュに追加します。** アプリケーションが .msi ファイルにエクスポートされ、.msi ファイルが BizTalk グループにインポートする場合に、このオプションを選択すると、インポート プロセスの一環として、ローカル コンピューターの GAC にアセンブリがインストールされています。  
  
    -   **MSI ファイル インストール (gacutil)、グローバル アセンブリ キャッシュに追加します。** アプリケーションが .msi ファイルにエクスポートし、アプリケーションが .msi ファイルからコンピューターにインストールされている場合、このオプションを選択すると、アセンブリはインストール プロセスの一環として、ローカル コンピューターの GAC にインストールされています。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
## <a name="to-add-a-biztalk-assembly-to-an-application"></a>BizTalk アセンブリをアプリケーションに追加するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk Server 管理コンソールと BizTalk アセンブリを追加するアプリケーションを含む BizTalk グループを展開します。  
  
3. アプリケーションと BizTalk アセンブリを追加するアプリケーションを展開します。  
  
4. 右クリック**リソース**、 をポイント**追加** をクリックし、 **BizTalk アセンブリ**します。  
  
5. クリックして**追加**、BizTalk アセンブリ ファイルを選択し、クリックして**オープン**します。  
  
6. **先**、アセンブリ ファイルのファイル名を含む .msi ファイルから、アプリケーションがインストールされているときにコピーする先の場所の完全なパスを入力します。 指定しなかった場合、インストール中、アセンブリ ファイルはローカル ファイル システムにコピーされません。  
  
7. **オプション**、BizTalk アセンブリを GAC にインストールするためのオプションを指定し、クリックして**OK**します。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1. 次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。  
  
2. 次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
    **BTSTask AddResource** [**/applicationname は:**<em>値</em>] **/Type:System.BizTalk:BizTalkAssembly** **[/Overwrite]** **/Source:**<em>値</em>[**/Destination:**<em>値</em>] [**/Options:GacOnAdd** &#124; **GacOnInstall**&#124;**GacOnImport**] [**/Server:**<em>値</em>] [**/データベース:**<em>値</em>]  
  
    例:  
  
    **BTSTask AddResource applicationname: myapplication/Type:System.BizTalk:BizTalkAssembly/overwrite/Source:"C:\BizTalk Assemblies\MyOrchestration.dll"/Destination:"C:\New BizTalk Assemblies\ MyOrchestration.dll"/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
   |パラメーター|値|  
   |---------------|-----------|  
   |**/ApplicationName**|BizTalk アセンブリを追加する BizTalk アプリケーションの名前。 アプリケーション名が指定されなかった場合、既定の BizTalk アプリケーションが使用されます。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
   |**/Type**|**System.BizTalk:BizTalkAssembly**|  
   |**/Overwrite**|既存のアセンブリを更新するためのオプション。 指定しない場合、アセンブリが既にを追加するには、アセンブリ、AddResource 操作は失敗と同じ LUID を持つアプリケーションに存在します。 アプリケーションのアイテムの Luid を表示するにを使用して、 [ListApp コマンド](../core/listapp-command.md)します。 他のアプリケーションが、上書きされようとしているアセンブリに依存している場合、このパラメーターを指定したとしても AddResource 操作は失敗します。|  
   |**/ソース**|アセンブリ ファイルの完全パス (ファイル名を含む)。 パスにスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
   |**/変換先**|アプリケーションを .msi ファイルからインストールしたときにアセンブリ ファイルがコピーされる場所 (完全パス)。 指定しなかった場合、インストール中、アセンブリ ファイルはローカル ファイル システムにコピーされません。 パスにスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
   |**/オプション**|-   **GacOnAdd**:AddResource 操作中に、アセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールするローカル コンピューターで指定します。<br />-   **GacOnInstall**:指定すると、アプリケーションが .msi ファイルからインストールされている場合は、アセンブリを GAC にインストールします。<br />-   **GacOnImport**:指定すると、アプリケーションの .msi ファイルをインポートすると、アセンブリを GAC にインストールします。<br /><br /> 複数のオプションを入力する場合は、コンマで区切って入力します。|  
   |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
   |**/Database**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [BizTalk アセンブリの管理](../core/managing-biztalk-assemblies.md)   
 [AddResource コマンド:BizTalk アセンブリ](../core/addresource-command-biztalk-assembly.md)