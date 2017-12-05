---
title: "ポリシーをインポートする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, requirements
- importing, policies
- policies, importing
- managing [policies], importing
ms.assetid: 92f6ef18-279f-416d-b13e-8b9642539d27
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac21ad1348dbc934c81d87f3c477977eeecd2ccf
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-import-a-policy"></a>ポリシーをインポートする方法
このトピックでは、BizTalk Server 管理コンソールを使用して BizTalk グループにポリシーをインポートする方法と、BTSTask コマンド ライン ツールを使用してポリシーを BizTalk アプリケーションにインポートする方法について説明します。  
  
 」の説明に従って、ビジネス ルール作成ツールを使用してポリシーを作成することができます[ビジネス ルール作成ツールを使用して作成するビジネス ルール](../core/creating-business-rules-using-the-business-rule-composer.md)、しを直接インポートするか、」の説明に従って、別の BizTalk グループからポリシーをエクスポートすることができます[ポリシーをエクスポートする方法](../core/how-to-export-a-policy.md)し、それをインポートします。  
  
 ポリシーをインポートすると、BizTalk グループのルール エンジン データベースに登録されます。 インポートしたポリシーは、BizTalk Server 管理コンソールに表示できます。 BizTalk Server 管理コンソールを使用してポリシーをインポートする場合に表示されます、\<すべての成果物\>BizTalk グループのノードです。 発行する」の説明に従って、BizTalk アプリケーションに追加できるようにし、[ポリシーを公開する方法](../core/how-to-publish-a-policy.md)です。 BTSTask コマンド ライン ツールを使用してポリシーをインポートしている場合、ポリシーは自動的に公開され、インポート先のアプリケーションのポリシー フォルダーに表示されます。  
  
 ポリシーをインポートする際には、次の点に注意してください。  
  
-   インポートしたポリシーで既存のポリシーを上書きするオプションを指定した場合でも、グループのルール エンジン データベースに既に存在し、展開されているポリシーはインポートできません。 この場合、インポート操作に失敗します。  
  
-   別の BizTalk グループからのエクスポート時にポリシーが展開状態であっても、インポート時には展開解除状態になります。  
  
-   BTSTask にはポリシーをインポートする専用のコマンドはありませんが、BTSTask の ExportApp コマンドを使用して、他のアプリケーション アイテムは含まずにアプリケーション内の目的のポリシーだけを選択的にエクスポートすることができます。 それから ImportApp コマンドを使用して、その .msi ファイルを別の BizTalk グループ内のアプリケーションにインポートできます。 この方法については、このトピックで説明します。 この方法では、ポリシーは BizTalk グループ内に自動的にインポートおよび公開されて、指定されたアプリケーションに追加されます。  
  
 ポリシーの扱いの詳細については、次を参照してください。[ポリシーの管理](../core/managing-policies.md)です。 ポリシーをアプリケーションに追加する方法のベスト プラクティスについては、次を参照してください。 [BizTalk アプリケーションを配置するためのベスト プラクティス](../core/best-practices-for-deploying-a-biztalk-application.md)です。  
  
> [!NOTE]
>  ソリューション開発者がポリシーを作成し、それらをインポート、グループのルール エンジン データベース、ルール エンジン展開ウィザードを使用して」の説明に従って[展開と展開解除ポリシーとボキャブラリを方法](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するための前提条件は、次のとおりです。  
  
-   BizTalk Server 管理者グループに属するアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
-   ビジネス ルール エンジンがインストールされている必要があります。 詳細については、次を参照してください。 [BizTalk Server 2013 および 2013 R2 のインストールの概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)です。  
  
-   BizTalk Server 管理コンソールを使用してポリシーをインポートする場合は、インポートするポリシーを含む使用可能な .xml ファイルが必要です。 」の説明に従って、別の BizTalk グループまたはアプリケーションからポリシーをエクスポートすることによってこのような .xml ファイルを生成することができます[ポリシーをエクスポートする方法](../core/how-to-export-a-policy.md)、または」の説明に従って、ビジネス ルール作成ツールを使用して[インポートおよびエクスポートする方法ポリシーとボキャブラリ](../core/how-to-import-and-export-policies-and-vocabularies.md)です。  
  
-   BTSTask を使用してポリシーをインポートする場合は、インポートするポリシーを含む .msi ファイルが必要です。 手順については、次を参照してください。[ポリシーをエクスポートする方法](../core/how-to-export-a-policy.md)です。  
  
## <a name="to-import-a-policy"></a>ポリシーをインポートするには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、ポリシーのインポートは、展開する BizTalk グループを展開**アプリケーション**、順に展開**\<すべての成果物\>**.  
  
3.  右クリック**ポリシー**、クリックして**インポート**です。  
  
4.  [参照] をクリックして、ポリシーを含む .xml ファイルに**開く**です。  
  
     ポリシーがグループにインポートしに表示、**ポリシー**のフォルダー **\<すべての成果物\>**です。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。  
  
2.  次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
     **BTSTask ImportApp/:** *値*[**/applicationname は:***値*] **[/overwrite]** [**/Server:***値*] [**/database:***値*]  
  
     例:  
  
     **BTSTask ImportApp/:"C:\MSI files \myapplication.msi"/Environment:Test applicationname: myapplication/overwrite**  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |**/パッケージ**|インポートするポリシーを含む .msi ファイルの完全パス。 パスには、スペースが含まれている場合は、引用符 (") で囲む必要があります。|  
    |**/ApplicationName**|ポリシーをインポートする BizTalk アプリケーションの名前。 アプリケーション名を指定すると、指定しない場合、.msi ファイルのエクスポートを使用する場合。 指定したアプリケーションが存在しない場合は作成されます。 スペースを含むアプリケーション名は、二重引用符 (") で囲む必要があります。|  
    |**/上書き**|アプリケーション内のポリシーを、.msi ファイル内の名前とバージョン番号が同じアイテムで上書きするオプション。 このオプションを省略した場合、.msi ファイル内のポリシーと同じ名前とバージョン番号を持つポリシーがアプリケーション内に 1 つ以上存在すると、インポートは失敗します。 使用して、アプリケーションで、ポリシーの名前とバージョン番号を表示することができます、 [ListApp コマンド](../core/listapp-command.md)です。|  
    |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
    |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**です。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーション、バインド、およびポリシーをインポートします。](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [BizTalk アプリケーション、バインド、およびポリシーをエクスポートします。](../core/exporting-biztalk-applications-bindings-and-policies.md)   
 [ポリシーの管理](../core/managing-policies.md)