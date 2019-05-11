---
title: 処理前または処理後のスクリプトをアプリケーションに追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], adding scripts
- managing [scripts], applications
- applications, scripts
- managing [scripts], adding
- scripts, adding to applications
- scripts
ms.assetid: 729cb236-b9cf-468a-8b98-a24d86e60d3c
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a10595d019b57bdab7a1afe5936df99147ec822
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343695"
---
# <a name="how-to-add-a-pre--or-post-processing-script-to-an-application"></a>処理前または処理後のスクリプトをアプリケーションに追加する方法
このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、処理前または処理後のスクリプトをアプリケーションに追加する方法について説明します。 アプリケーションに追加されたスクリプトは、アプリケーションの .msi ファイルに格納され、アプリケーションのインポート、インストール、またはアンインストール時に実行されます。  
  
 スクリプトを追加する際には、処理前のスクリプト (アプリケーションのインポートやインストールの前に実行) か処理後のスクリプト (インポートやインストール完了後に実行) かを指定する必要があります。 前処理および後処理のスクリプトは、アンインストール、インストール時の実行には、逆の順序でも実行します。 アンインストール後に処理前のスクリプトを実行し、アンインストールの前に処理後のスクリプトを実行します。  
  
 スクリプトはアプリケーションから削除することもできます。 手順については、次を参照してください。[より前に削除する方法または処理後のスクリプトをアプリケーションから](../core/how-to-remove-a-pre-or-post-processing-script-from-an-application.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
## <a name="to-add-a-script-to-an-application"></a>アプリケーションにスクリプトを追加するには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. BizTalk グループ、[アプリケーション] の順に展開し、スクリプトに追加するアプリケーションのフォルダーを右クリックします。  
  
3. をポイント**追加**次のいずれかを実行します。  
  
   -   クリックして**処理前のスクリプト**アプリケーションのインポート前に実行するスクリプトまたはインストールが開始される場合、またはアンインストール後にします。  
  
   -   クリックして**処理後のスクリプト**スクリプトをアプリケーションのインポートまたはインストールした後、またはアンインストールの前に実行するかどうか。  
  
4. クリックして**追加**を追加するスクリプト ファイルを参照します。  
  
5. スクリプト ファイルを選択し、クリックして**オープン**します。  
  
6. アプリケーションに既に存在するスクリプト ファイルを上書きする場合、**すべて上書き**チェック ボックスをオンします。 上書きされるスクリプト ファイルは、追加するファイルと同じ名前である必要があります。 同じ名前のファイルがない場合は、新しいスクリプト ファイルが追加され、アプリケーションの既存のスクリプト ファイルは変更されません。  
  
7. をクリックして、**ファイルの種類**し、ドロップダウン リストのファイルの種類か**System.BizTalk:PreprocessingScript**または**System.BizTalk:PostprocessingScript**します。  
  
8. 必要に応じて、**先の場所**型、スクリプトのパスがファイルをコピーして、アプリケーションがインストールされているときに、クリックして**OK**します。 既定のパスでは、スクリプトはアプリケーションのインストール フォルダー (%BTAD_InstallDir%) にインストールされます。  
  
> [!NOTE]
>  このパスを指定しないと、スクリプトはインストール時にローカル ファイル システムにコピーされません。 このスクリプトをアプリケーションのアンインストール時に実行する必要がある場合は、必ずこのパスを指定してください。指定しないと、スクリプトがローカル ファイル システムに格納されないため、アンインストール中に実行できません。  
  
 スクリプト ファイルが追加されて、アプリケーションのリソース フォルダーに表示されます。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1. 次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。  
  
2. 次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
    **BTSTask AddResource** [**/applicationname は:**<em>値</em>] **/Type:System.BizTalk:PreProcessingScript** &#124; **System.BizTalk:PostProcessingScript** **[/overwrite]** **/source:**<em>値</em>[**/Destination:** <em>値</em>] [**/Server:**<em>値</em>] [**/database:**<em>値</em>] [**/Property:Args ="**<em>引数リスト</em>**"**]  
  
    例:  
  
    **BTSTask AddResource applicationname: myapplication/Type:System.BizTalk:PreProcessingScript/overwrite/Source:"C:\Source Scripts\MyScript.vbs"/Destination:"C:\New Scripts\MyScript.vbs"/Server:MyDatabaseServer/Database:BizTalkMgmtDb/Property:Args =「[引数 1] [引数 2]」**  
  
   |パラメーター|値|  
   |---------------|-----------|  
   |**/ApplicationName**|スクリプトを追加する BizTalk アプリケーションの名前。 アプリケーション名が指定されなかった場合、既定の BizTalk アプリケーションが使用されます。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
   |**/Type**|**System.BizTalk:PreProcessingScript**または**System.BizTalk:PostProcessingScript**、追加するスクリプトの種類によって異なります。 使用**System.BizTalk:PreProcessingScript**スクリプトをアプリケーションのインポートまたはインストールする前に、またはアンインストールの後に実行するかどうか。 使用**System.BizTalk:PostProcessingScript**スクリプトをアプリケーションのインポートまたはインストールした後、またはアンインストールの前に実行するかどうか。|  
   |**/Overwrite**|既存のスクリプトを更新します。 指定しなかった場合、追加するスクリプト ファイルと同じ名前のスクリプト ファイルが既にアプリケーションに存在すると、追加操作は失敗します。|  
   |**/ソース**|スクリプト ファイルの完全パス (ファイル名を含む)。 パスにスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
   |**/変換先**|アプリケーションを MSI ファイルからインストールしたときにスクリプト ファイルがコピーされる場所 (完全パス)。 指定しなかった場合、インストール中、このファイルはローカル ファイル システムにコピーされません。 パスにスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
   |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
   |**/Database**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
   |**/Property:Args=**|0 個以上の引数。 ここで指定した引数はスクリプトが呼び出された時にスクリプトに渡されます。|  
  
## <a name="see-also"></a>参照  
 [前処理および後処理のスクリプトを管理します。](../core/managing-pre-and-post-processing-scripts.md)   
 [AddResource コマンド:処理前のスクリプト](../core/addresource-command-preprocessing-script.md)   
 [AddResource コマンド:処理後のスクリプト](../core/addresource-command-postprocessing-script.md)