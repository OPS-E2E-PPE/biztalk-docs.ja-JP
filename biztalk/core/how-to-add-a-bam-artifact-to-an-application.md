---
title: アプリケーションに BAM アイテムを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, definition files [BAM]
- BAM, applications
- managing [applications], definition files [BAM]
- definition files [BAM], managing
ms.assetid: 86f19030-e510-4527-ba74-10498c361c00
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 244ac82a2d6ec11307852e06b7f042fc550121e8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387395"
---
# <a name="how-to-add-a-bam-artifact-to-an-application"></a>アプリケーションに BAM アイテムを追加する方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンドラインを使用して BizTalk アプリケーションに BAM アイテムを追加する方法を説明します。 BAM 定義ファイルを追加する BAM 定義をデプロイしません。 BAM 定義は、アプリケーションの .msi ファイルがインポートされるときにデプロイされます。  
  
 アプリケーションに既に存在する BAM アイテムを上書きする場合は、上書きオプションを指定します。 既存の BAM アイテムを追加する 1 つとして同じファイル名である場合にのみ、上書きオプションが必要です。 指定しない場合、追加操作は失敗、BAM アイテムが追加される 1 つとして同じファイル名を使用してアプリケーションに既に存在します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
## <a name="to-add-a-bam-artifact-to-an-application"></a>アプリケーションに BAM アイテムを追加するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1. クリックして**開始**、 をクリックして**Al プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]は、BizTalk グループを展開し、アプリケーションを展開し、BAM アイテム ファイルを追加するアプリケーションを展開します。  
  
3. 右クリックし、**リソース**フォルダーをポイントして**追加**、 をクリックし、**リソース**します。  
  
4. クリックして**追加**、BAM アイテムのファイルを選択し、クリックして**オープン**します。  
  
5. **ファイルの種類**ドロップダウン リストで、 **System.BizTalk:BAM**します。  
  
6. **先**、成果物ファイルのファイル名を含む .msi ファイルから、アプリケーションがインストールされているときにコピーする先の場所の完全なパスを入力します。 このパスを指定しない場合は、ファイルがインストール中に、ローカル ファイル システムにコピーされませんが、アプリケーションの .msi ファイルがインポートされるときにデプロイされます。  
  
    例:**C:\My Applications\MyBAMfile.xml**  
  
7. 完了したら、 **[OK]** をクリックします。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1. 次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。  
  
2. 次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
    **BTSTask AddResource** [**/applicationname は:**<em>値</em>] **/Type:System.BizTalk:Bam** **[/overwrite]** **/Source:**<em>値</em>[**/Destination:**<em>値</em>] [**/Server:** <em>値</em>] [**/database:**<em>値</em>]  
  
    例:  
  
    **BTSTask AddResource applicationname: myapplication/Type:System.BizTalk:Bam/overwrite/Source:"C:\Source BAMfiles\MyBAMfile.xml"/Destination:"%BTADInstallDir%\BAMfiles\MyBAMfile.xml"/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
   |パラメーター|値|  
   |---------------|-----------|  
   |**/ApplicationName**|BAM アイテムを追加する BizTalk アプリケーションの名前。 アプリケーション名が指定されなかった場合、グループの既定の BizTalk アプリケーションが使用されます。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
   |**/Type**|**System.BizTalk:Bam** (この値小文字は区別されません)。|  
   |**/Overwrite**|既存の BAM アイテムを上書きするオプション。 指定されていない場合、追加する BAM アイテム、AddResource 操作は失敗として同じファイル名を持つアプリケーションで BAM アイテムが既に存在します。|  
   |**/ソース**|ファイル名を含む、BAM アイテム ファイルの完全パス。 パスにスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
   |**/変換先**|BAM アイテム ファイルが .msi ファイルから、アプリケーションのインストール時にコピーする場所の完全パス。 指定しなかった場合、インストール中、このファイルはローカル ファイル システムにコピーされません。 パスにスペースが含まれている場合は、二重引用符 (") で囲む必要があります。 パスに、環境変数 %btadinstalldir% を使用して、アプリケーションのインストール フォルダーを指定することができます。|  
   |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
   |**/Database**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [.NET アセンブリ、証明書、およびその他のリソースを管理します。](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource コマンド:BAM アイテム](../core/addresource-command-bam-artifact.md)   
 [作成して、BizTalk アプリケーションの変更](../core/creating-and-modifying-biztalk-applications.md)   
 [BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)