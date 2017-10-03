---
title: "チュートリアル: 基本的な BizTalk アプリケーションの配置 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, tutorials
- tutorials, deploying
- tutorials, applications
- applications, tutorials
ms.assetid: 21b67153-0f8c-406a-a224-fc792b16192f
caps.latest.revision: "69"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5db86f672cd17965ec76877cc3867594bf82b40d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-deploying-a-basic-biztalk-application"></a>チュートリアル: 基本的な BizTalk アプリケーションの配置
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、BizTalk ビジネス ソリューションの管理と展開を簡略化する機能が備わっています。 オーケストレーション、スキーマ、マップ、パイプライン、.NET アセンブリなど、ビジネス ソリューションのさまざまなアイテムを格納する BizTalk アプリケーション コンテナーが取り入れられました。 ことができます管理、変更、展開、および 1 つの単位としてアプリケーションにすべての項目をインストールします。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション展開タスクの自動化に役立つウィザードも含まれています。 背景情報について、次を参照してください。[アプリケーションの展開と管理機能](../core/application-deployment-and-management-features.md)と[アプリケーションの展開と管理ツール](../core/application-deployment-and-management-tools.md)です。  
  
 ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の展開機能の使用手順としくみについて説明します。 ここで説明する展開プロセスには、企業ごとのアプリケーション展開の管理方法が反映されているとは限りません。  
  
 ここでは、単純な BizTalk アプリケーションを作成し、開発環境からテスト環境に、さらにはステージング環境および実稼働環境に展開します。 このチュートリアルを完了すると、次のタスクを実行できるようになります。  
  
-   開発用コンピューター上の [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] から [展開] コマンドを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のローカル インスタンスに BizTalk アセンブリを展開する。 これにより、アセンブリが含まれた BizTalk アプリケーションが作成されます。 BizTalk アセンブリには、オーケストレーション、パイプライン、スキーマ、マップなど、BizTalk ソリューションで使用するリソース情報が含まれます。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、追加、作成、構成、およびすべての項目を削除 (と呼ばれる*成果物*) を送信など、完全に機能するビジネス ソリューションを作成し、受信ポート、ポリシー、アセンブリ、必要に応じて、スクリプト作成します。  
  
-   エクスポート ウィザード、インポート ウィザード、およびインストール ウィザードを使用して、BizTalk アプリケーションをテスト コンピューターに展開し、機能とシステムのテストを行えるようにする。  
  
-   エクスポート ウィザード、インポート ウィザード、およびインストール ウィザードを使用して、アプリケーションをステージング サーバーに展開し、最終的な構成と実稼働サーバーへの展開を行えるようにする。  
  
## <a name="prerequisites"></a>前提条件  
 このチュートリアルのテスト環境を設定するには、次の 2 つの方法があります。  
  
-   このチュートリアルの複数のタスクを、単一のコンピューター上で実行できます。  
  
-   開発、テスト、ステージング、実稼働の各用途にそれぞれ異なるコンピューターを設定すると、実際の展開により忠実なシミュレーションを行えます。 ただし、このチュートリアルのいずれのタスクも、実稼働環境で実行しないでください。  
  
 このチュートリアルの手順を実行するには、使用するテスト環境が次の前提条件を満たしている必要があります。  
  
-   BizTalk アセンブリの展開元となる開発用コンピューターに、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] がインストールされている。  
  
-   このチュートリアルで説明するアプリケーション展開プロセスで使用される各コンピューター (開発用コンピューターを含む) に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がインストールされている。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の各インスタンスが個別にインストールされている。つまり、それぞれに独自の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースとグループを持つ。  
  
 上記の要件に加えて、BizTalk アセンブリを格納する [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ソリューションまたはプロジェクトを使用できる必要があります。 既存のソリューションまたはプロジェクトがない場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK に含まれている ErrorHandling サンプル ソリューションをこの目的に使用できます。 このサンプルの使用方法は後で説明します。  
  
 また、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループと、このチュートリアルのタスクを実行するコンピューターのローカル管理者グループとに属するユーザー アカウントが必要です。  
  
 インストールと構成の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[は新規、インストール、構成、およびアップグレード](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)です。
  
##  <a name="BKMK_Assumptions"></a>前提条件  
 ここでは、次のことを前提とします。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に関する基礎知識がある。 [BizTalk Server の概要](../core/getting-started-with-biztalk-server.md)が役立ちます。
  
-   テスト環境において、使用する BizTalk アセンブリがアプリケーションに展開されたことがない。 展開されている場合は、展開先の BizTalk アプリケーションを展開解除してください。 手順については、次を参照してください。 [BizTalk アプリケーションを展開解除](../core/undeploying-biztalk-applications.md)です。  
  
-   いずれのアプリケーション リソースも、他のアプリケーションと共有されない。  
  
##  <a name="BKMK_Audience"></a>対象ユーザー  
 このチュートリアルの対象読者は次のとおりです。  
  
-   **BizTalk アプリケーションの開発者。** 開発者は、プロジェクト プロパティで設定する方法を学ぶことができます[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]から BizTalk アセンブリを展開および[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk アプリケーションにします。 開発者は、アイテムをアプリケーションに追加してから、アプリケーションを .msi ファイルにエクスポートする方法も学ぶことができます。 開発者のアプリケーション展開タスクに関する背景情報を参照してください。 [BizTalk アプリケーション展開の開発タスク](../core/development-tasks-for-biztalk-application-deployment.md)です。  
  
-   **BizTalk アプリケーション テスター。** テスト担当者は、.msi ファイルにインポートする方法を学習できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk アプリケーションとして登録する、テスト コンピューターで実行されています。 テスターは、アプリケーションをテスト コンピューターにインストールし、インストールを確認する方法も学ぶことができます。 アプリケーション展開作業のテストに関する背景情報については、次を参照してください。 [BizTalk アプリケーション展開のテスト タスク](../core/testing-tasks-for-biztalk-application-deployment.md)です。  
  
-   **BizTalk Server IT 管理者です。** ステージング サーバーおよび実稼働サーバーへの BizTalk アプリケーションの展開を担当する IT 管理者は、このタスクに必要な基本手順を学ぶことができます。 IT 管理者のアプリケーション展開タスクに関する背景情報を参照してください[BizTalk アプリケーション展開のステージング作業](../core/staging-tasks-for-biztalk-application-deployment.md)と[運用展開のタスクを BizTalk アプリケーション](../core/production-tasks-for-biztalk-application-deployment.md)。.  
  
##  <a name="BKMK_Overview"></a>このチュートリアルの概要  
 ここでは、ラボ環境で BizTalk アプリケーションを展開し、このテクノロジを実稼働環境に展開した場合にどのように機能するかを評価します。 ここで使用する単純なシナリオ (1 つの .msi ファイルを 1 台のコンピュータ上に BizTalk アプリケーションとして展開する) によって、アプリケーション展開に関する基本的な作業を理解することができます。  
  
> [!NOTE]
>  ここでは、オーケストレーションのバインドやポートの構成など、アプリケーションが機能するために必要なアプリケーション構成については説明しません。 このチュートリアルは、新しいアプリケーション展開機能の紹介のみを目的としています。  
  
 ここで説明する手順には、次のタスクが含まれます。  
  
1.  **必要なアクセス許可を構成します。** チュートリアルの開始前に、各タスクを実行するために適切なアクセス許可があることを確認する必要があります。  
  
2.  **Visual Studio から BizTalk アセンブリを展開します。** この手順は、アプリケーション開発者が実行します。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] から BizTalk アセンブリを展開すると、自動的にアセンブリがビルドされ、そのコンテンツが BizTalk アプリケーションに展開されます。 アプリケーションがまだ存在しない場合、アセンブリを展開するとアプリケーションの作成も行われます。 アプリケーションのアイテムが登録され、そのデータが BizTalk 管理データベースに格納されます。 さらに、既定では、ローカル コンピューターのグローバル アセンブリ キャッシュ (GAC) にアセンブリがインストールされます。 アプリケーションが作成されたら、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、そのアイテムを表示したり管理したりできます。 管理コンソールでは、各アプリケーションが個別のフォルダーに格納され、アプリケーションのすべてのアイテムへの参照がサブフォルダーに格納されます。  
  
3.  **アプリケーションを構成します。** この手順は、アプリケーションが正常に機能するために必要なアイテムを追加、作成、および構成するため、アプリケーション開発者または IT 管理者が実行できます。 管理コンソールからは、送信ポート、受信ポート、スクリプト、追加アセンブリなどのアイテムを、簡単に追加、作成、構成、および削除できます。 アプリケーションに必要なアイテムが含まれ、適切に構成されたことを確認したら、.msi ファイルにエクスポートします (次の説明を参照)。  
  
4.  **.Msi ファイルにアプリケーションをエクスポートしています。** この手順は、別の環境に BizTalk アプリケーションを展開するために使用できる .msi ファイルを生成するため、開発者、テスター、または IT 管理者が実行できます。 たとえば、開発者がエクスポートした .msi ファイルを、テスターが使用して、テスト サーバーにアプリケーションを展開できます。 テストの完了後、テスト済みの .msi ファイルを IT 管理者が使用して、ステージング サーバーまたは実稼働サーバーにアプリケーションを展開できます (次の説明を参照)。 このチュートリアルでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールから利用できるエクスポート ウィザードを使用して、アプリケーションを .msi ファイルにエクスポートする方法を説明しています。  
  
5.  **アプリケーションをインストールする .msi ファイルからインポートしています。** この手順は、ステージング サーバーまたは実稼働サーバーに BizTalk アプリケーションを展開するため、テスターまたは IT 管理者が実行できます。 たとえばテスターは、開発者によって提供された .msi ファイルから、テスト コンピューター上の BizTalk グループにアプリケーションをインポートできます。その後、.msi ファイルからアプリケーションをインストールしてテストできます。 同様に IT 管理者は、テスターによって提供された .msi ファイルから、ステージング サーバーまたは実稼働サーバーにアプリケーションを展開できます。 このチュートリアルでは、インポート ウィザードを使用して、.msi ファイルを BizTalk グループのアプリケーションにインポートする方法を説明しています。 手順 2. と同様、アプリケーションのアイテムが登録され、そのデータが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースに格納されます。 このチュートリアルでは、インストール ウィザードを使用するか .msi ファイルをダブルクリックすることにより、アプリケーションを現在のサーバー上にインストールする方法も説明しています。 これにより、現在のサーバーでアプリケーションを実行できます。  
  
##  <a name="BKMK_Step-by-step"></a>BizTalk アプリケーションの展開のステップバイ ステップ ガイド  
 このセクションでは、開発からテスト、ステージング、実稼働までのすべてのフェーズを通じ、BizTalk アプリケーションを展開する手順について説明します。 既に説明したとおり、これらの手順すべてを同一のコンピューター上で実行することも、使用する環境により忠実なシミュレーションを行うために、複数のコンピューターを使用することもできます。  
  
#### <a name="1-configure-permissions"></a>1.アクセス許可の構成  
 最初の手順では、このチュートリアルのタスクを実行するために適切なアクセス許可があることを確認します。 参照してください[を展開して、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最小限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)です。
  
#### <a name="2-deploy-the-biztalk-assemblies"></a>2.BizTalk アセンブリの展開  
 開発用コンピューター上の Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] からこの手順を実行して、BizTalk アセンブリを BizTalk アプリケーションに展開します。  
  
 このステップを開始する前に、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で使用できる BizTalk ソリューションを用意する必要があります。 独自のソリューションまたはプロジェクトを作成することも、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] に含まれている ErrorHandling サンプルを設定することもできます。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に ErrorHandling サンプル ソリューションを設定するには、次の操作を行います。  
  
###### <a name="to-set-up-the-errorhandling-solution"></a>ErrorHandling ソリューションを設定するには  
  
1.  開発用コンピューターで、次のディレクトリに移動します。  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Messaging\ErrorHandling\ErrorHandler  
  
2.  ダブルクリックして**ErrorHandler.btproj**です。  
  
     ErrorHandler ソリューションが [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で開かれます。 このソリューションは、2 つのプロジェクトで構成されています: ErrorHandler および PipelinesAndSchemas です。  
  
     ![Visual Studio プロジェクトをソリューションに](../core/media/errorhandlingprojects.gif "ErrorHandlingProjects")  
  
 次に、ソリューション内の各プロジェクトについて、プロパティを設定する必要があります。 ErrorHandling サンプル ソリューションには、2 つのプロジェクト プロパティを設定する必要がありますにはが含まれています: ErrorHandler および PipeLinesAndSchemas です。 開発用コンピューターの環境に合わせて、プロパティを構成します。 たとえば、指定する SQL サーバーのインスタンスは、開発用コンピューター上で実行されており、ローカルの BizTalk 管理データベースをホストしている必要があります。  
  
###### <a name="to-configure-project-properties"></a>プロジェクトのプロパティを構成するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーをクリックして、プロパティを構成するプロジェクトを右クリックして**プロパティ**です。  
  
2.  クリックして、**展開**プロジェクト デザイナーのタブです。  
  
     ![Visual Studio 2005 での展開のプロパティ シート](../core/media/deploymentproperties.gif "DeploymentProperties")  
  
3.  次の表に示すようにプロジェクトのプロパティを構成し、をクリックして**OK**です。  
  
    |プロパティ|値|説明|  
    |--------------|-----------|-----------------|  
    |Application Name|\<Name>|このプロジェクトのアセンブリの展開先となる、BizTalk アプリケーションの名前。 アプリケーションが既に存在する場合、プロジェクトを展開すると、アセンブリがアプリケーションに追加されます。 アプリケーションが存在しない場合は、アプリケーションが新しく作成されます。 このフィールドを空白にした場合、アセンブリは、現在のグループの既定の BizTalk アプリケーションに展開されます。既定では "BizTalk Application 1" です。 スペースが含まれる名前は、二重引用符 (") で囲む必要があります。|  
    |構成データベース|\<BizTalk 管理データベース名 >|グループの BizTalk 管理データベースの名前。既定では BizTalkMgmtDb です。|  
    |[サーバー]|\<サーバー名 >|ローカル コンピューターで BizTalk 管理データベースをホストする SQL Server インスタンスの名前。 単一のコンピューターにインストールする場合、通常はローカル コンピューターの名前です。 **注:** BizTalk プロジェクトを別のコンピューターに移動する場合は、アセンブリを配置することができます前に、新しいコンピューター名を反映するようにサーバー プロパティを変更する必要があります。|  
    |再配置します。|True または False|これを True に設定すると (既定)、バージョン番号を変更せずに BizTalk アセンブリを再展開できます。|  
    |[グローバル アセンブリ キャッシュにインストール]|True または False|これを True に設定すると (既定)、アセンブリの展開時に、ローカル コンピューター上のグローバル アセンブリ キャッシュ (GAC) にアセンブリがインストールされます。|  
    |ホスト インスタンスを再起動します。|True または False|これを True に設定すると、アセンブリの再展開時に、ローカル コンピューター上で実行中のすべてのホスト インスタンスが自動的に再起動されます。 False に設定した場合 (既定)、アセンブリの再展開時に、ホスト インスタンスを手動で再起動する必要があります。 **注:**ソリューション レベルからアセンブリを再デプロイする場合は、ホスト インスタンスが再起動されますがこのオプションを True に設定するプロジェクトごとにします。 結果として、再起動が 2 回以上行われる可能性があります。 ソリューション レベルからの再展開を計画する場合は、ソリューション内のただ 1 つのプロジェクトに対してこのプロパティを True に設定することで、ホスト インスタンスが複数回再起動することを防ぐことができます。 その場合は、ソリューション内で再展開される最後のプロジェクトに設定する必要があります。 また、再展開を実行するときにホスト インスタンスが停止された場合は、起動されません。|  
    |単体テストを有効にする|True または False|プロジェクトの単体テストを有効にするかどうかを指定します。|  
  
4.  ソリューションの各プロジェクトごとに、手順 1. ～ 3. を繰り返します。  
  
 展開プロセスでは、アセンブリが厳密に署名されている必要があります。 アセンブリに厳密な署名を行うには、厳密な名前のアセンブリ キー ファイルをプロジェクトに関連付けます。 この処理をまだ行っていない場合は、次の手順に従って、厳密な名前のアセンブリ キー ファイルを生成します。  
  
###### <a name="to-create-a-strong-name-assembly-key-file"></a>厳密な名前のアセンブリー キー ファイルを作成するには  
  
1.  開始**Visual Studio コマンド プロンプト**です。  
  
2.  コマンド プロンプトで、キー ファイルを格納するフォルダーから次のコマンドを入力し、Enter キーを押します。  
  
     **sn-k***file_name* **.snk**   
  
     例: **sn-k ErrorHandling.snk**  
  
     確認メッセージを**キーのペアに書き込まれる\<**  *file_name***> .snk** `,`コマンド ラインで表示されます。  
  
 次に、ソリューション内の各プロジェクトにキー ファイルを関連付ける必要があります。  
  
###### <a name="to-associate-your-projects-with-the-key-file"></a>プロジェクトにキー ファイルを関連付けるには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーで、プロジェクトを右クリックし、をクリックして**プロパティ**です。  
  
2.  クリックして、**署名**プロジェクト デザイナーのタブです。  
  
3.  右側のウィンドウで確認、**アセンブリに署名**ボックス。  
  
4.  下にあるドロップダウン ボックスをクリックして**厳密な名前キー ファイルを選択して**をクリックして **\<[参照...] >**、キー ファイルを参照します。  
  
5.  キー ファイルをクリックし、をクリックして**開く**です。  
  
6.  ソリューションの各プロジェクトについて、手順 1. ～ 5. を繰り返します。  
  
 次の手順では、ソリューションのすべてのアセンブリのビルドと展開を、一度に行うことができます。  
  
###### <a name="to-deploy-the-assemblies-in-a-solution"></a>ソリューションのアセンブリを展開するには  
  
-   [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーは、ソリューションを右クリックし、をクリックして**ソリューションの配置**です。  
  
     ページの左下隅に、ビルドおよび展開プロセスの状態が表示されます。 ErrorHandling サンプル ソリューションを使用した場合、出力ウィンドウに複数の警告メッセージが表示されます。 このチュートリアルでは、これらを無視してかまいません。 展開が完了すると、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 出力ウィンドウに "展開: 2 正常終了、0 失敗、0 スキップ" と表示されます。  
  
 BizTalk アセンブリを展開すると、BizTalk 管理データベース内の指定した BizTalk アプリケーションの一部として登録されます。 すべての項目を持つデータベースも設定または*成果物*アセンブリに含まれています。 展開前にアプリケーションがまだ存在していなかった場合、新しいアプリケーションの作成も行われます。 これで、開発用コンピューターの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールから、BizTalk アプリケーションとそのアイテムを表示できます。  
  
###### <a name="to-view-the-biztalk-application-and-its-artifacts"></a>BizTalk アプリケーションとそのアイテムを表示するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、順に展開**アプリケーション**です。  
  
3.  アセンブリを展開したアプリケーションのフォルダーを展開します。  
  
4.  アプリケーション フォルダーの下にあるフォルダーをクリックし、コンテンツを表示します。 個々のフォルダーに、展開元のアセンブリに含まれていたアイテムが表示されます。 ErrorHandling サンプル BizTalk ソリューションを展開した場合、[オーケストレーション]、[スキーマ]、[リソース] の各フォルダーにアイテムが表示されます。 アイテムを右クリックし、をクリックすることができます**プロパティ**その構成設定を表示します。  
  
5.  展開して、**リソース**フォルダーは、アセンブリの 1 つを右クリックし、をクリックして**変更**です。  
  
6.  **オプション**ボックスで、アセンブリが構成されている展開オプションを確認します。  
  
7.  **先**アプリケーションがインストールされている場合に、アセンブリ ファイルがコピーされる場所へのパスに注意してください。 既定では、アセンブリの追加元です。  
  
> [!NOTE]
>  右クリックし、アプリケーションが表示されない場合**BizTalk グループ** をクリック**更新**です。  
  
 アセンブリの展開の詳細については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)です。  
  
#### <a name="3-configure-the-application"></a>3.アプリケーションの構成  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールからアイテムの作成、追加、および構成を行うことにより、アプリケーションを構成できます。  
  
 アプリケーションが機能するためには、適切に構成されている必要があります。 たとえば、オーケストレーションをホストにバインドし、送信ポートと受信場所を構成する必要があります。 ErrorHandling サンプル ソリューションを展開した場合、送信ポート、受信ポート、受信場所がアプリケーションに指定されていません。 これは、オーケストレーションがメッセージを送受信できないことを意味します。 アプリケーションの構成手順については、このチュートリアルでは説明しません。 しかし、これを行う場合、最も簡単なのは [アプリケーションの構成] ダイアログ ボックスを使用する方法です。このダイアログ ボックスを表示するには、アプリケーションを右クリックして [構成] をクリックします。 詳細については、次を参照してください。[アプリケーションを構成する方法](../core/how-to-configure-an-application.md)です。 この方法に加えて、オーケストレーションを構成したり、送信ポート、送信ポート グループ、受信ポート、および受信場所を、個別に作成、構成、および削除したりできます。 詳細については、該当するトピックを参照してください。[成果物の管理](../core/managing-artifacts.md)です。  
  
 処理前のスクリプトや Readme ファイルなど、アプリケーションのアイテムに追加するまたは、成果物を削除することも可能性があります。 次の手順を使用して、この機能を試すことができます  (ErrorHandling サンプルには追加可能なアイテムが含まれていませんが、使用する環境内の既存の項目を追加することにより、この機能をテストできます)。  
  
> [!NOTE]
>  処理前のスクリプトや処理後のスクリプトを使用すると、アプリケーションのインポート、インストール、またはアンインストールの前や後に、アクションを実行できます。 たとえば、処理前のスクリプトを使用して、アンインストール後に GAC からアセンブリをアンインストールできます。 詳細については、次を参照してください。[前処理および後処理のスクリプトをアプリケーションの展開のカスタマイズを使用して](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)です。  
  
###### <a name="to-add-an-artifact-to-an-application"></a>アプリケーションにアイテムを追加するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを開きます。 をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、順に展開**アプリケーション**です。  
  
3.  次の種類のアイテムを追加するに ErrorHandling アプリケーション フォルダーを右クリックし、をクリックして**追加**です。 BizTalk アセンブリを追加すると、それに含まれているアイテムも、アプリケーション内の適切なフォルダーに追加されます。  
  
    -   BizTalk アセンブリ  
  
    -   処理前のスクリプト  
  
    -   処理後のスクリプト  
  
    -   リソース (BizTalk アセンブリ、.NET アセンブリ、処理前のスクリプト、処理後のスクリプト、ファイル、証明書、COM コンポーネント、 BAM アイテム、バインド ファイル、仮想ディレクトリ)  
  
    -   ポリシー  
  
 アプリケーションからアイテムを削除することもできます。  
  
###### <a name="to-remove-an-artifact-from-an-application"></a>アプリケーションからアイテムを削除するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを開きます。 をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、順に展開**アプリケーション**です。  
  
3.  成果物を含むフォルダーを展開し、アイテムを右クリックしてをクリックして**削除**です。  
  
 アプリケーションの構成の詳細については、次を参照してください。[を変更する BizTalk アプリケーションの作成と](../core/creating-and-modifying-biztalk-applications.md)です。  
  
#### <a name="4-export-the-application"></a>4.アプリケーションのエクスポート  
 BizTalk アプリケーションを作成し、必要に応じて変更した後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで MSI ファイルのエクスポート ウィザードを使用して、アプリケーションをエクスポートできます。 これによって生成される .msi ファイルを、後で別の BizTalk グループにインポートすると、アプリケーションを新しいグループ内に再作成できます。 また、特定のサーバー上でアプリケーションを実行するには、この .msi ファイルからアプリケーションをローカルにインストールする必要があります。  
  
###### <a name="to-export-the-application"></a>アプリケーションをエクスポートするには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを開きます。 をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、順に展開**アプリケーション**です。  
  
3.  BizTalk アプリケーションを右クリックし、**エクスポート**、クリックして**MSI ファイル**です。  
  
4.  **MSI ファイルのエクスポート ウィザードへようこそ** ページで、をクリックして**次**です。  
  
5.  **リソースの選択**.msi ファイルにエクスポートし、をクリックするリソースの選択 ページで、**次**です。 このチュートリアルでは、既定値をそのまま使用してかまいません。  
  
6.  メッセージが表示されたら、[、 **IIS ホストの指定**] ページで、をクリックし、含める仮想ディレクトリをホストするコンピューターのサーバー名を入力**次**です。 サーバーの指定が要求されるのは、仮想ディレクトリがアプリケーションに追加されたりインポートされたときに、仮想ディレクトリが BizTalk 管理データベースに追加されていなかった場合のみです。  
  
    > [!NOTE]
    >  ErrorHandling サンプル ソリューションには、仮想ディレクトリが含まれていません。  
  
7.  **の依存関係** ページで、アプリケーションの依存関係を確認してをクリックして**次**です。  
  
8.  **先**] ページの [**送信先アプリケーション名**アプリケーション名を入力します。  
  
9. **を生成する MSI ファイル**.msi ファイルの完全なパスを入力して、をクリックして**エクスポート**です。 例: C:\MSI\Errorhandling.msi  
  
    > [!NOTE]
    >  .msi ファイルはセキュリティで保護されたフォルダーに保存することをお勧めします。  
  
10. **概要**ページで、この操作のログ ファイルの場所をメモしてをクリックし、**完了**です。  
  
 ファイル システムで、指定した場所に .msi ファイルが作成されたことを確認してください。  
  
> [!NOTE]
>  セキュリティ上の理由により、パスワードは、アプリケーションのエクスポート中にアプリケーションのバインドから削除されます。 .Msi ファイルからアプリケーションをインストールした後は、アプリケーションが機能するためにパスワードを再構成する必要があります。 ただし、パスワードはアプリケーションに追加したバインド ファイルからは削除されません。  
  
 アプリケーションとアイテムのエクスポートの詳細については、次を参照してください。[を BizTalk アプリケーションをエクスポートする方法](../core/how-to-export-a-biztalk-application.md)です。  
  
#### <a name="5-import-and-install-the-application"></a>5.アプリケーションのインポートおよびインストール  
 次の手順では、生成した .msi ファイルからアプリケーションを BizTalk グループにインポートし、アプリケーションをローカル コンピューターにインストールします。 この操作には、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、MSI のインポート ウィザードとインストール ウィザードを使用できます。  
  
> [!NOTE]
>  アプリケーションを実行するグループ内の各コンピューターに、アプリケーションをインストールする必要があります。 .msi ファイルをダブルクリックすると、追加のコンピューターにインストールできます。  
  
 開発環境からテスト環境へ、テスト環境からステージング環境へ、ステージング環境から実稼働環境への移行時など、BizTalk グループ間でアプリケーションを移行するたびに、この手順の作業を繰り返すことができます。  
  
 このチュートリアルに 1 台のコンピューターのみを使用している場合、この時点で、BizTalk グループからアプリケーションを削除してください。 また、グローバル アセンブリ キャッシュ (GAC) からアセンブリも削除してください。 これにより、アプリケーションのインポート時に、アプリケーションが正しく再作成されたことを確認できるようになります。 チュートリアルに複数のコンピューターを使用している場合、この作業を実行する必要はありません。  
  
###### <a name="to-delete-the-application-from-the-biztalk-group"></a>BizTalk グループからアプリケーションを削除するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを開きます。 をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  アプリケーションを右クリックし、をクリックして**削除**です。  
  
###### <a name="to-delete-assemblies-from-the-gac"></a>GAC からアセンブリを削除するには  
  
1.  ファイル システムで、%systemdrive%\Windows\assembly に移動します。  
  
2.  各アセンブリ ファイルが生成されたソリューションを右クリックし、をクリックして**アンインストール**、順にクリック**はい**ことを確認します。 たとえば、ErrorHandling プロジェクトに関連付けられているアセンブリ ファイルは、ErrorHandling.ErrorHandler および ErrorHandling.PipelinesAndSchemas です。  
  
     ![GAC からアセンブリを削除する](../core/media/deleteassembly.gif "DeleteAssembly")  
  
 これで、BizTalk グループにアプリケーションをインポートする準備ができました。 別のコンピューター上で実行されている BizTalk グループにアプリケーションをインポートする場合、そのコンピューターから .msi ファイルにアクセスできる必要があります。  
  
> [!CAUTION]
>  どのアプリケーションをインストールする場合でも、必ず信頼できるソースから入手した .msi ファイルを使用してください。 悪意のあるユーザーによって、システムまたはネットワークに悪影響を及ぼすコードが .msi ファイルに挿入されている可能性があります。 詳細については、次を参照してください。[セキュリティと Windows インストーラー](../core/security-and-windows-installer.md)です。  
  
###### <a name="to-import-and-install-the-application"></a>アプリケーションをインポートおよびインストールするには  
  
1.  次の手順で、アプリケーションのインポート先となる [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インスタンスに対し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを開きます。 をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、順に展開**BizTalk グループ**です。  
  
3.  右クリック**アプリケーション**、 をポイント**インポート**、クリックして**MSI ファイル**です。  
  
4.  **のインポート ウィザードへようこそ**] ページの [**インポートする MSI ファイル**.msi ファイルの完全なパスを入力して、をクリックして**次**です。 例: C:\msi\MyApplication.msi  
  
5.  **アプリケーション設定**] ページの [**への参照を追加できるアプリケーション**、参照を追加し、をクリックするアプリケーションを選択して**次**です。 ErrorHandling サンプル ソリューションを使用している場合、既定値をそのまま使用してかまいません。  
  
     ![アプリケーションへの参照を追加](../core/media/appreferences.gif "AppReferences")  
  
6.  **アプリケーションのターゲット環境設定**いることを確認 ページで、 **\<既定 >**が選択されているし、をクリックして**次へ**です。  
  
7.  **インポートの概要**ページで概要情報が正しいことを確認してをクリックして**インポート**です。  
  
8.  MSI のインポート ウィザードの最終画面で、次のように選択します。 **、ローカル コンピューターにアプリケーションをインストールするアプリケーション インストール ウィザードを実行して**、順にクリック**完了**です。  
  
     ![インポート ウィザードからインストールを開始](../core/media/startinstallation.gif "StartInstallation")  
  
9. **インストール フォルダーの選択**] ページの [**フォルダー**BizTalk アプリケーションのインストール パスを入力して、をクリックして**次**です。  
  
10. をクリックして**次**インストールを続行する次の 3 つのページです。  
  
     Windows インストーラーによって、アプリケーションがローカル コンピューターにインストールされます。  
  
11. **インストールの完了**] ページで [**閉じる**です。  
  
 アプリケーションのインポートの詳細については、次を参照してください。[を BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)です。 アプリケーションのインストールの詳細については、次を参照してください。[を BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)です。  
  
 次に、アプリケーションがインポートおよびインストールされたことを確認します。そのためには、次の各項目について検証します。  
  
-   管理コンソールのアプリケーションのフォルダーに、アプリケーションとそのアイテムすべてが存在する。  
  
-   GAC にアプリケーション アセンブリが存在する。  
  
-   アプリケーションのインストール時に指定したパスに、アプリケーションに関連付けられたファイルが存在する。  
  
-   [プログラムの追加と削除] コントロール パネルにアプリケーションが表示される。  
  
-   右クリックし、をクリックして、アプリケーションを起動できますようになりました場合は、アプリケーションが、関数は、このような送信を指定することによって、受信ポートを構成、**開始**です。 ただし ErrorHandling サンプル アプリケーションは、既定では、機能するよう設定されません。手動で構成した場合を除いて、これを開始することはできません。  
  
-   BizTalk グループとローカル コンピューターからアプリケーションを完全に削除するには、指示に従います[BizTalk アプリケーションを展開解除](../core/undeploying-biztalk-applications.md)です。  
  
## <a name="see-also"></a>参照  
[BizTalk アプリケーションの展開と管理を理解します。](../core/understanding-biztalk-application-deployment-and-management.md)