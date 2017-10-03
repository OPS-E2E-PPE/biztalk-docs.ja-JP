---
title: "前または処理後のスクリプトをアプリケーションに追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [applications], adding scripts
- managing [scripts], applications
- applications, scripts
- managing [scripts], adding
- scripts, adding to applications
- scripts
ms.assetid: 729cb236-b9cf-468a-8b98-a24d86e60d3c
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d0646bc9e896e7b4e4d9264efba7c9bb5f0eb66
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-pre--or-post-processing-script-to-an-application"></a>処理前または処理後のスクリプトをアプリケーションに追加する方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、処理前または処理後のスクリプトをアプリケーションに追加する方法について説明します。 アプリケーションに追加されたスクリプトは、アプリケーションの .msi ファイルに格納され、アプリケーションのインポート、インストール、またはアンインストール時に実行されます。  
  
 スクリプトを追加する際には、処理前のスクリプト (アプリケーションのインポートやインストールの前に実行) か処理後のスクリプト (インポートやインストール完了後に実行) かを指定する必要があります。 前処理および後処理のスクリプトは、インストール時に実行されたに逆の順序で、アンインストールにも実行します。 アンインストール後に処理前のスクリプトを実行し、アンインストールの前に処理後のスクリプトを実行します。  
  
 スクリプトはアプリケーションから削除することもできます。 手順については、次を参照してください。[前を削除する方法または処理後のスクリプトをアプリケーションから](../core/how-to-remove-a-pre-or-post-processing-script-from-an-application.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="to-add-a-script-to-an-application"></a>アプリケーションにスクリプトを追加するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  BizTalk グループ、[アプリケーション] の順に展開し、スクリプトに追加するアプリケーションのフォルダーを右クリックします。  
  
3.  指す**追加**、し、次のいずれかの操作を行います。  
  
    -   をクリックして**処理前のスクリプト**スクリプト アプリケーションのインポートの前に実行するか、インストールが開始される場合、またはアンインストールの後にします。  
  
    -   をクリックして**処理後のスクリプト**場合は、スクリプトをアプリケーションのインポートや、インストール後、またはアンインストールの前に実行します。  
  
4.  をクリックして**追加**し、追加するスクリプト ファイルを参照します。  
  
5.  スクリプト ファイルを選択し、クリックして**開く**です。  
  
6.  アプリケーションに既に存在するスクリプト ファイルを上書きする場合、**すべて上書き**チェック ボックスをオンします。 上書きされるスクリプト ファイルは、追加するファイルと同じ名前である必要があります。 同じ名前のファイルがない場合は、新しいスクリプト ファイルが追加され、アプリケーションの既存のスクリプト ファイルは変更されません。  
  
7.  クリックして、**ファイルの種類**ドロップダウン リストをクリック、ファイルの種類 – か**System.BizTalk:PreprocessingScript**または**System.BizTalk:PostprocessingScript**です。  
  
8.  必要に応じて、**先の場所**型、スクリプトのパスがファイルをアプリケーションがインストールされているときにコピーして、をクリックして**OK**です。 既定のパスでは、スクリプトはアプリケーションのインストール フォルダー (%BTAD_InstallDir%) にインストールされます。  
  
> [!NOTE]
>  このパスを指定しないと、スクリプトはインストール時にローカル ファイル システムにコピーされません。 このスクリプトをアプリケーションのアンインストール時に実行する必要がある場合は、必ずこのパスを指定してください。指定しないと、スクリプトがローカル ファイル システムに格納されないため、アンインストール中に実行できません。  
  
 スクリプト ファイルが追加されて、アプリケーションのリソース フォルダーに表示されます。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。  
  
2.  次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
     **BTSTask AddResource** [**/applicationname は:***値*] **/Type:System.BizTalk:PreProcessingScript**&#124;**System.BizTalk:PostProcessingScript** [**/overwrite**] **/source:***値*[**/Destination:** *値*] [**/Server:***値*] [**/database:***値*] [**/Property:Args ="***引数リスト***"**]  
  
     例:  
  
     **BTSTask AddResource applicationname: myapplication/Type:System.BizTalk:PreProcessingScript/overwrite/Source:"C:\Source Scripts\MyScript.vbs"/Destination:"C:\New Scripts\MyScript.vbs"/Server:MyDatabaseServer/Database:BizTalkMgmtDb/Property:Args =「[引数 1] 引数 2」**  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |**/ApplicationName**|スクリプトを追加する BizTalk アプリケーションの名前。 アプリケーション名が指定されなかった場合、既定の BizTalk アプリケーションが使用されます。 名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
    |**/型**|**System.BizTalk:PreProcessingScript**または**System.BizTalk:PostProcessingScript**を追加するスクリプトの種類に応じて、します。 使用して**System.BizTalk:PreProcessingScript**場合は、スクリプトをアプリケーションのインポートまたはインストールする前に、またはアンインストールの後に実行します。 使用して**System.BizTalk:PostProcessingScript**場合は、スクリプトをアプリケーションのインポートや、インストール後、またはアンインストールの前に実行します。|  
    |**/上書き**|既存のスクリプトを更新します。 指定しなかった場合、追加するスクリプト ファイルと同じ名前のスクリプト ファイルが既にアプリケーションに存在すると、追加操作は失敗します。|  
    |**/ソース**|スクリプト ファイルの完全パス (ファイル名を含む)。 パスには、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
    |**/対象**|アプリケーションを MSI ファイルからインストールしたときにスクリプト ファイルがコピーされる場所 (完全パス)。 指定しなかった場合、インストール中、このファイルはローカル ファイル システムにコピーされません。 パスには、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
    |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
    |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
    |**/Property:Args =**|0 個以上の引数。 ここで指定した引数はスクリプトが呼び出された時にスクリプトに渡されます。|  
  
## <a name="see-also"></a>参照  
 [前処理および後処理のスクリプトを管理します。](../core/managing-pre-and-post-processing-scripts.md)   
 [AddResource コマンド: 前処理スクリプト](../core/addresource-command-preprocessing-script.md)   
 [AddResource コマンド: 処理後のスクリプト](../core/addresource-command-postprocessing-script.md)