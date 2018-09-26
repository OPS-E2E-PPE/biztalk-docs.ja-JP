---
title: ポリシーをインポートする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, requirements
- importing, policies
- policies, importing
- managing [policies], importing
ms.assetid: 92f6ef18-279f-416d-b13e-8b9642539d27
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c70038d23dc43a865a5fe30d80543f0d1a47149a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000299"
---
# <a name="how-to-import-a-policy"></a>ポリシーをインポートする方法
このトピックでは、BizTalk Server 管理コンソールを使用して BizTalk グループにポリシーをインポートする方法と、BTSTask コマンド ライン ツールを使用してポリシーを BizTalk アプリケーションにインポートする方法について説明します。  
  
 」の説明に従って、ビジネス ルール作成ツールを使用してポリシーを作成することができます[ビジネス ルール作成ツールを使用して作成するビジネス ルール](../core/creating-business-rules-using-the-business-rule-composer.md)、しを直接インポートするか、」の説明に従って、別の BizTalk グループからポリシーをエクスポートすることができます[ポリシーをエクスポートする方法](../core/how-to-export-a-policy.md)し、それをインポートします。  
  
 ポリシーをインポートすると、BizTalk グループのルール エンジン データベースに登録されます。 インポートしたポリシーは、BizTalk Server 管理コンソールに表示できます。 ポリシーをインポートする BizTalk Server 管理コンソールを使用する場合に表示されます、\<すべての成果物\>BizTalk グループのノード。 発行する」の説明に従って、BizTalk アプリケーションに追加できるようにし、[ポリシーを公開する方法](../core/how-to-publish-a-policy.md)します。 BTSTask コマンド ライン ツールを使用してポリシーをインポートしている場合、ポリシーは自動的に公開され、インポート先のアプリケーションのポリシー フォルダーに表示されます。  
  
 ポリシーをインポートする際には、次の点に注意してください。  
  
- インポートしたポリシーで既存のポリシーを上書きするオプションを指定した場合でも、グループのルール エンジン データベースに既に存在し、展開されているポリシーはインポートできません。 この場合、インポート操作に失敗します。  
  
- 別の BizTalk グループからのエクスポート時にポリシーが展開状態であっても、インポート時には展開解除状態になります。  
  
- BTSTask にはポリシーをインポートする専用のコマンドはありませんが、BTSTask の ExportApp コマンドを使用して、他のアプリケーション アイテムは含まずにアプリケーション内の目的のポリシーだけを選択的にエクスポートすることができます。 それから ImportApp コマンドを使用して、その .msi ファイルを別の BizTalk グループ内のアプリケーションにインポートできます。 この方法については、このトピックで説明します。 この方法では、ポリシーは BizTalk グループ内に自動的にインポートおよび公開されて、指定されたアプリケーションに追加されます。  
  
  ポリシーの使用方法の詳細については、次を参照してください。[ポリシーの管理](../core/managing-policies.md)します。 アプリケーションにポリシーを追加する方法のベスト プラクティスは、次を参照してください。 [BizTalk アプリケーションの展開のベスト プラクティス](../core/best-practices-for-deploying-a-biztalk-application.md)します。  
  
> [!NOTE]
>  ソリューション開発者がポリシーを作成し、それらをインポート、グループのルール エンジン データベース、ルール エンジン展開ウィザードを使用して」の説明に従って[とボキャブラリを展開およびポリシーの展開を解除する方法](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するための前提条件は、次のとおりです。  
  
-   BizTalk Server 管理者グループに属するアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
-   ビジネス ルール エンジンがインストールされている必要があります。 詳細については、次を参照してください。 [BizTalk Server 2013 および 2013 R2 のインストールの概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)します。  
  
-   BizTalk Server 管理コンソールを使用してポリシーをインポートする場合は、インポートするポリシーを含む使用可能な .xml ファイルが必要です。 」の説明に従って、別の BizTalk グループまたはアプリケーションからポリシーをエクスポートすることによってこのような .xml ファイルを生成できます[ポリシーをエクスポートする方法](../core/how-to-export-a-policy.md)、または」の説明に従って、ビジネス ルール作成ツールを使用して[インポートおよびエクスポートする方法ポリシーとボキャブラリ](../core/how-to-import-and-export-policies-and-vocabularies.md)します。  
  
-   BTSTask を使用してポリシーをインポートする場合は、インポートするポリシーを含む .msi ファイルが必要です。 手順については、次を参照してください。[ポリシーをエクスポートする方法](../core/how-to-export-a-policy.md)します。  
  
## <a name="to-import-a-policy"></a>ポリシーをインポートするには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、ポリシーをインポートするために展開する BizTalk グループを展開**アプリケーション**、順に展開**\<すべての成果物\>**.  
  
3. 右クリックして**ポリシー**、 をクリックし、**インポート**します。  
  
4. [参照] をクリックして、ポリシーを含む .xml ファイルに**オープン**します。  
  
    ポリシーがグループにインポートされに表示されます、**ポリシー**フォルダーの**\<すべての成果物\>** します。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1. 次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。  
  
2. 次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
    **BTSTask の ImportApp/Package:** *値*[**/applicationname は:**<em>値</em>] **[/overwrite]** [**/サーバー:**<em>値</em>] [**/database:**<em>値</em>]  
  
    例:  
  
    **BTSTask ImportApp/Package:"C:\MSI \myapplication.msi"/Environment:Test applicationname: myapplication/overwrite**  
  
   |パラメーター|値|  
   |---------------|-----------|  
   |**/パッケージ**|インポートするポリシーを含む .msi ファイルの完全パス。 パスにスペースが含まれている場合は、引用符 (") で囲む必要があります。|  
   |**/ApplicationName**|ポリシーをインポートする BizTalk アプリケーションの名前。 アプリケーション名を指定すると、指定しない場合、.msi ファイルのエクスポートを使用する場合。 指定したアプリケーションが存在しない場合は、それが作成されます。 スペースが含まれるアプリケーションの名前は、二重引用符 (") で囲む必要があります。|  
   |**/上書き**|アプリケーション内のポリシーを、.msi ファイル内の名前とバージョン番号が同じアイテムで上書きするオプション。 このオプションを省略した場合、.msi ファイル内のポリシーと同じ名前とバージョン番号を持つポリシーがアプリケーション内に 1 つ以上存在すると、インポートは失敗します。 使用して、アプリケーションでポリシーの名前とバージョン番号を表示することができます、 [ListApp コマンド](../core/listapp-command.md)します。|  
   |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
   |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーション、バインド、およびポリシーのインポート](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [BizTalk アプリケーション、バインド、およびポリシーのエクスポート](../core/exporting-biztalk-applications-bindings-and-policies.md)   
 [ポリシーの管理](../core/managing-policies.md)