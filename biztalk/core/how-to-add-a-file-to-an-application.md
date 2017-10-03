---
title: "アプリケーションにファイルを追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [applications], adding files
- files, adding to applications
- managing [resources], adding files
ms.assetid: 6665b946-113a-4026-a0a3-6b67ede4b689
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4493eafe2bba4e1203a230180024e0e5a8a2ce08
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-file-to-an-application"></a>アプリケーションにファイルを追加する方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、BizTalk アプリケーションにファイルを追加する方法について説明します。 アプリケーションをインストールすると、アプリケーションに追加するファイルはインストール フォルダーにコピーされます。 ファイルをアプリケーションの .msi ファイルにエクスポートして、アプリケーションと共にさまざまな環境に移動することもできます。  
  
> [!NOTE]
>  Readme ファイルを追加する方法の詳細については、次を参照してください。 [Readme ファイルにリンクする方法](../core/how-to-link-to-a-readme-file.md)です。  
  
 アプリケーションに既に存在するファイルを上書きするには、[上書き] オプションを指定します。 [上書き] オプションは、両方のファイルが同じ名前の場合にのみ機能します。 このオプションを指定しなかった場合、追加するファイルと同じ名前のファイルが既にアプリケーションに存在すると、追加操作は失敗します。  
  
> [!NOTE]
>  他の種類のアイテムとは異なり、BizTalk グループ内の複数のファイルに同じ名前を指定できます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="to-add-a-file-to-an-application"></a>アプリケーションにファイルを追加するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、ファイルを追加するアプリケーションが含まれる BizTalk グループの順に展開します。  
  
3.  [アプリケーション] を展開し、ファイルを追加するアプリケーションを展開します。  
  
4.  右クリックし、**リソース**フォルダーを指す**追加**、順にクリック**リソース**です。  
  
5.  をクリックして**追加**、ファイルを選択し、をクリックして、**開く**です。  
  
6.  **ファイルの種類**ドロップダウン リストで、 **System.BizTalk:File**です。  
  
7.  **先**ファイルをファイル名を含む、.msi ファイルから、アプリケーションがインストールされているときにコピーする場所の完全なパスを入力します。 既定値は、アプリケーションのインストール フォルダー、%BTAD_InstallDir% です。 このパスを指定しないと、インストールでローカル ファイル システムにファイルがコピーされません。  
  
8.  完了したら、 **[OK]**をクリックします。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。  
  
2.  次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
     **BTSTask AddResource** [**/applicationname は:***値*] **/Type:System.BizTalk:File** [**/overwrite**] **/Source:***値*[**/Destination:***値*] [**/Server:** *値*] [**/database:***値*]  
  
     例:  
  
     **BTSTask AddResource applicationname: myapplication/Type:System.BizTalk:File/overwrite/Source:"C:\Source Files\File.txt"/Destination:"C:\New Files\File.txt"/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |**/ApplicationName**|ファイルを追加する BizTalk アプリケーションの名前。 アプリケーション名が指定されなかった場合、既定の BizTalk アプリケーションが使用されます。 名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
    |**/型**|**System.BizTalk:File** (この値小文字は区別されません)。|  
    |**/上書き**|既存のファイルを更新するためのオプション。 指定しなかった場合、追加するファイルと同じ名前のファイルが既にアプリケーションに存在した場合、AddResource 操作は失敗します。|  
    |**/ソース**|ファイルの完全パス (ファイル名を含む)。 パスには、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
    |**/対象**|アプリケーションを .msi ファイルからインストールしたときにファイルがコピーされる場所 (完全パス)。 パスには、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。 指定しなかった場合、インストール中、このファイルはローカル ファイル システムにコピーされません。|  
    |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
    |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [.NET アセンブリ、証明書、およびその他のリソースの管理](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource コマンド: ファイル](../core/addresource-command-file.md)   
 [作成して、BizTalk アプリケーションの変更](../core/creating-and-modifying-biztalk-applications.md)