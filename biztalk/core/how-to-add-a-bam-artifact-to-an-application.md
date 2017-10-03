---
title: "アプリケーションに BAM アイテムを追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications, definition files [BAM]
- BAM, applications
- managing [applications], definition files [BAM]
- definition files [BAM], managing
ms.assetid: 86f19030-e510-4527-ba74-10498c361c00
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44b4a55141b2e5cfbc527dd386c9f1cbdd464dc9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-bam-artifact-to-an-application"></a>BAM アイテムをアプリケーションに追加する方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、BizTalk アプリケーションに BAM アイテムを追加する方法について説明します。 BAM 定義ファイルを追加しても、その BAM 定義が展開されるわけではありません。 BAM 定義は、アプリケーションの .msi ファイルがインポートされたときに展開されます。  
  
 アプリケーションに既に存在する BAM アイテムを上書きする場合は、上書きオプションを指定します。 既存の BAM アイテムを追加するものと同じファイル名である場合にのみ、上書きオプションが必要です。 指定しない場合、BAM アイテムが追加されるものと同じファイル名をアプリケーションに既に存在は、追加操作は失敗します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="to-add-a-bam-artifact-to-an-application"></a>アプリケーションに BAM アイテムを追加するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1.  をクリックして**開始**、 をクリックして**Al プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、BizTalk グループ、[アプリケーション]、BAM アイテム ファイルを追加するアプリケーションの順に展開します。  
  
3.  右クリックし、**リソース**フォルダーを指す**追加**、順にクリック**リソース**です。  
  
4.  をクリックして**追加**の BAM アイテム ファイルを選択し、クリックして**開く**です。  
  
5.  **ファイルの種類**ドロップダウン リストで、 **System.BizTalk:BAM**です。  
  
6.  **先**、成果物ファイルのファイル名を含む、.msi ファイルから、アプリケーションがインストールされているときにコピーする先の場所の完全なパスを入力します。 パスを指定しなかった場合、インストール時にローカル ファイル システムにファイルがコピーされませんが、アプリケーションの .msi ファイルをインポートすると展開されます。  
  
     例: **C:\My Applications\MyBAMfile.xml**  
  
7.  完了したら、 **[OK]**をクリックします。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。  
  
2.  次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
     **BTSTask AddResource** [**/applicationname は:***値*] **/Type:System.BizTalk:Bam** [**/overwrite**] **/Source:***値*[**/Destination:***値*] [**/Server:** *値*] [**/database:***値*]  
  
     例:  
  
     **BTSTask AddResource applicationname: myapplication/Type:System.BizTalk:Bam/overwrite/Source:"C:\Source BAMfiles\MyBAMfile.xml"/Destination:"%BTADInstallDir%\BAMfiles\MyBAMfile.xml"/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |**/ApplicationName**|BAM アイテムを追加する BizTalk アプリケーションの名前。 アプリケーション名が指定されなかった場合、グループの既定の BizTalk アプリケーションが使用されます。 名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
    |**/型**|**System.BizTalk:Bam** (この値小文字は区別されません)。|  
    |**/上書き**|既存の BAM アイテムを上書きするためのオプション。 指定しなかった場合、追加する BAM アイテムと同じファイル名の BAM アイテムが既にアプリケーションに存在すると、AddResource 操作が失敗します。|  
    |**/ソース**|BAM アイテム ファイルの完全パス (ファイル名を含む)。 パスには、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
    |**/対象**|アプリケーションを .msi ファイルからインストールしたときに BAM アイテム ファイルがコピーされる場所 (完全パス)。 指定しなかった場合、インストール中、このファイルはローカル ファイル システムにコピーされません。 パスには、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。 アプリケーションのインストール フォルダーを指定するには、パスで環境変数 %BTADInstallDir% を使用します。|  
    |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
    |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [.NET アセンブリ、証明書、およびその他のリソースの管理](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource コマンド: BAM アイテム](../core/addresource-command-bam-artifact.md)   
 [作成して、BizTalk アプリケーションの変更](../core/creating-and-modifying-biztalk-applications.md)   
 [BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)