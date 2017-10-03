---
title: "Visual Studio から BizTalk アセンブリを再展開する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c4bb627-48de-4874-bb25-af2c513dbc51
caps.latest.revision: "41"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 361d2bccc783e7bfc7aa6cb0cd1f3eab51d8e640
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-redeploy-a-biztalk-assembly-from-visual-studio"></a>Visual Studio から BizTalk アセンブリを再展開する方法
アセンブリの開発プロセスでは、展開、テスト、修正、再展開を繰り返し行うことがしばしば必要になります。 以前のバージョンの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、バージョン番号を変更せずにアセンブリを再展開するには、まず [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でアセンブリに含まれるアイテムの停止、参加解除、バインド解除を手動で行い、次に BizTalk 管理 (構成) データベースからそのアセンブリを削除する必要がありました。 さらに、アセンブリの再展開の後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でアイテムをバインドし、参加させ、開始する必要がありました。  
  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] では、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で再展開オプションを有効にすると、アセンブリを再展開する手順がすべて [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって自動的に実行されます。 プロジェクト レベルからアセンブリを再展開することで (ソリューション エクスプローラーでプロジェクトを右クリックして [配置] をクリックするなどの手順で) 個別のアセンブリを再展開することもできますが、常にソリューション レベルからアセンブリを再展開すること (ソリューションを右クリックして [配置] をクリックするなどの手順で) を強くお勧めします。 これにより、ソリューションのアセンブリが一度に再展開され、依存関係がある場合に関連する手順がすべて処理されます。詳細については、後で説明します。  
  
> [!IMPORTANT]
>  プロジェクト レベルで再展開することが必要になる場合もまれにありますが、一般には、常にソリューション レベルで再展開することをお勧めします。  
  
 アセンブリを再展開する際には、次の重要事項を念頭に置いてください。  
  
-   **新しいアセンブリを GAC にインストールする必要があります。** アセンブリを再展開するときにする必要があります常にインストールする新しいバージョンのアセンブリ、GAC に」の説明に従って[アセンブリを GAC にインストールする方法](../core/how-to-install-an-assembly-in-the-gac.md)です。 このインストールは、再展開の後に行えます。  
  
-   **常に再展開ソリューション レベルで依存関係がある場合。** ソリューションに複数のアセンブリがあり、そのソリューションの 1 つ以上のアセンブリが再展開するアセンブリに依存している場合、ソリューション レベルで目的のアセンブリを再展開する必要があります。 これは、プロジェクト レベルでアセンブリを再展開すると、このアセンブリに依存する、またはこのアセンブリが依存するすべてのアセンブリのアイテムの停止、参加解除、バインド解除、削除が [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって行われるためです。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、アイテムの展開、バインド、参加、開始を行う追加手順は実行されません。 ソリューション全体を再展開すると、依存関係に基づいているソリューションのすべてのアイテムを展開解除して再展開するのに必要な手順が、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって自動的に実行されます。  
  
-   **依存アセンブリを手動で再展開する必要があります。** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では常に依存アセンブリが展開解除されますが、次に示す場合においては、依存先のアセンブリを再展開した後、各依存アセンブリのアイテムを展開し、バインドして、参加させる追加手順の実行が必要です。  
  
    -   プロジェクト レベルでアセンブリを再展開する際に、同じソリューションの別のアセンブリが目的のアセンブリに依存している場合。  
  
    -   ソリューション レベルでアセンブリを再展開する際に、別のソリューションに依存アセンブリが存在する場合。  
  
     たとえば、次の図で、アセンブリ 3 だけを再展開しようとすると、再展開の後、アセンブリ 2 のアイテムの展開、バインド、参加が必要になり、次にアセンブリ 1 のアイテムの展開、バインド、参加が必要になります。  
  
     ![依存関係を持つアセンブリ](../core/media/assemblydependencies.gif "AssemblyDependencies")  
  
     別の方法として、変更されていないコア アセンブリの不要な展開を避ける方法があります。  上の図の例では、アセンブリ 2 およびアセンブリ 3 に依存している他のアセンブリが存在する場合、これらのアセンブリはどれも更新されていません。  オフにして、**展開**アセンブリ 2 およびアセンブリ 3 プロジェクト用の configuration manager でのオプションです。 これにより、依存する外部アセンブリは展開解除されず、再展開は必要ありません。 詳細については、次を参照してください。 [Visual Studio の配置プロパティを設定する方法](../core/how-to-set-deployment-properties-in-visual-studio.md)です。  
  
-   **ホスト インスタンスを再起動する必要があります。** アセンブリ バージョン番号を変更せずにオーケストレーションを含むアセンブリを再展開すると、BizTalk 管理データベースの既存のアセンブリは上書きされます。 ただし、変更が有効になる前に、オーケストレーションがバインドされているホストの各ホスト インスタンスを再起動する必要があります。 オプションを指定して、アセンブリの再展開時に、ローカル コンピューター上のすべてのホスト インスタンスを自動的に再起動することができます。 手順については、次を参照してください。 [Visual Studio の配置プロパティを設定する方法](../core/how-to-set-deployment-properties-in-visual-studio.md)です。 手動で停止および」の説明に従って、各ホスト インスタンスを開始できます[ホスト インスタンスを停止する方法](../core/how-to-stop-a-host-instance.md)と[ホスト インスタンスを起動する方法](../core/how-to-start-a-host-instance.md)です。  
  
> [!IMPORTANT]
>  再展開オプションではバージョン管理が無視されるので、使用は開発時のみに限定することをお勧めします。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループに属するアカウントでログオンする必要があります。 また、使用するアカウントには、ローカル ファイル システムおよびグローバル アセンブリ キャッシュ (GAC) に対する読み取り/書き込みアクセス許可が必要です。 ローカル コンピューターの管理者アカウントには、これらのアクセス許可が与えられています。  
  
## <a name="to-redeploy-a-biztalk-solution"></a>BizTalk ソリューションを再展開するには  
  
#### <a name="using-visual-studio-solution-explorer"></a>Visual Studio ソリューション エクスプローラーを使用する場合  
  
1.  」の説明に従って、ソリューション内の各プロジェクトの展開プロパティで再展開オプションが有効になっていることを確認[Visual Studio の配置プロパティを設定する方法](../core/how-to-set-deployment-properties-in-visual-studio.md)です。 このオプションは、既定の設定で有効になります。  
  
2.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーは、BizTalk ソリューションを右クリックし、をクリックして**展開**です。  
  
     ソリューションのアセンブリが、指定した BizTalk アプリケーションに展開されます。 ページの左下隅に、ビルドおよび展開プロセスの状態が表示されます。  
  
#### <a name="using-the-visual-studio-command-prompt"></a>Visual Studio コマンド プロンプトを使用する場合  
  
1.  」の説明に従って、ソリューション内の各プロジェクトの展開プロパティで再展開オプションが有効になっていることを確認[Visual Studio の配置プロパティを設定する方法](../core/how-to-set-deployment-properties-in-visual-studio.md)です。 このオプションは、既定の設定で有効になります。  
  
2.  開始**Visual Studio コマンド プロンプト**です。  
  
3.  次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
     **devenv/deploy***SolnConfigName* *SolutionName*   
  
     例:  
  
     **devenv/deploy リリース"C:\Documents と Settings\someuser\My documents \visual Studio\Projects\MySolution\MySolution.sln"**  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |**/deploy**|ビルドまたはリビルド後にソリューションを配置します。|  
    |*SolnConfigName*|SolutionName で指定したソリューションのビルドに使用されるソリューション構成の名前です。|  
    |*SolutionName*|ソリューション ファイルの完全パスと名前です。|  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開します。](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)