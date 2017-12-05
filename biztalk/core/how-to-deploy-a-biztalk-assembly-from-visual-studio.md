---
title: "Visual Studio から BizTalk アセンブリを展開する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69d70c52-3e71-4eb2-876e-b467c7ca24b7
caps.latest.revision: "39"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fc232edf6d99e31b5679932eb19873481fa579b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-deploy-a-biztalk-assembly-from-visual-studio"></a>Visual Studio から BizTalk アセンブリを展開する方法
このトピックでは、使用に関する説明[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーまたは[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトから BizTalk アセンブリを展開する[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk アプリケーションにします。 プロジェクト レベルから 1 つのアセンブリを展開する方法 (手順は、プロジェクトを右クリックして [配置] をクリックするなど) と、ソリューション レベルからすべてのアセンブリをソリューションで展開する方法 (ソリューションを右クリックして [配置] をクリックするなど) を利用できますが、ソリューション レベルからすべてのアセンブリを一度に展開する方法を強くお勧めします。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の以前のバージョンでは、複数のアセンブリをソリューションで展開する場合、いずれかのアセンブリに他のアセンブリとの依存関係があると、これらのアセンブリを依存関係と逆の順序で個別に展開する必要がありました。 たとえば、Assembly1 が Assembly2 に依存していた場合、最初に Assembly2 を展開しないと、Assembly1 は展開できませんでした。  
  
 プロジェクト レベルからアセンブリを展開する場合、このことは変わりません。 BizTalk Server、ただし、ときに展開して、プロジェクト レベルではなくソリューション レベルからアセンブリ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]自動的に正しい順序でアセンブリの展開を含む、展開の手順のすべての処理です。 したがって、展開するアセンブリに他のアセンブリとの依存関係がある場合、展開を簡略化するには、ソリューション レベルでアセンブリを展開してください。  
  
 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 内からプロジェクトまたはソリューションを展開するオプションを選択すると、1 つのまたは複数のアセンブリが自動的にビルドされ、ローカルの BizTalk グループ内の指定した BizTalk アプリケーションに展開されます。 アプリケーションがグループ内に存在しない場合は、展開によってアプリケーションの作成も行われます。 アセンブリとアセンブリに含まれるアイテムは登録され、それらのデータは BizTalk グループの BizTalk 管理 (構成) データベースに格納されます。 また、プロジェクトの展開のプロパティでこのオプションを指定した場合、アセンブリはグローバル アセンブリ キャッシュ (GAC) に追加されます。  
  
 "アイテム" とは、BizTalk アプリケーション内に存在するあらゆる項目のことです。これには、アセンブリ、オーケストレーションなど、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で使用するリソースだけでなく、送信ポート、受信ポート、証明書、スクリプトなど、アプリケーションの展開後に作成または追加したその他の項目も含まれます。 アセンブリが展開されたら、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]コンソールの [アプリケーション] ノードでアセンブリのアイテムを表示および管理できるようになります。 各アプリケーションは個別のフォルダーに格納され、サブフォルダーにアプリケーション内のアイテムが表示されます。 詳細については、次を参照してください。 [、BizTalk Server 管理コンソールを使用して](../core/using-the-biztalk-server-administration-console.md)です。 作成して、アプリケーションの管理に関する詳細については、次を参照してください。[を管理する BizTalk アプリケーションの展開と](../core/deploying-and-managing-biztalk-applications.md)です。  
  
 アセンブリを展開する場合、まず、次の手順を実行する必要があります。  
  
-   厳密な名前のアセンブリ キー ファイルを作成し、」の説明に従って、各プロジェクトに割り当てられた、[厳密な名前のアセンブリ キー ファイルを構成する方法](../core/how-to-configure-a-strong-name-assembly-key-file.md)です。  
  
-   」の説明に従って、プロジェクトの配置プロパティを設定[Visual Studio の配置プロパティを設定する方法](../core/how-to-set-deployment-properties-in-visual-studio.md)です。  
  
-   以前に展開したアセンブリがある場合は、プロジェクトの再展開オプションを有効にします。 手順と再展開する場合は、その他の重要な情報では、次を参照してください。[を Visual Studio から BizTalk アセンブリを再展開する方法](../core/how-to-redeploy-a-biztalk-assembly-from-visual-studio.md)です。  
  
> [!IMPORTANT]
>  ここで説明する作業は、実稼働コンピューターでは行わないでください。 開発の過程ではしばしば、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] からのアセンブリの再展開が必要になります。 再展開を可能にするため、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] では同一または別のアプリケーション内に存在するアイテムの展開解除、バインド解除、停止、および参加解除が行われます。 これは開発環境では必要であり適切なことですが、実稼働環境では予期しない結果や結果や好ましくない結果を引き起こす可能性があります。 また、実稼働コンピューター上の [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] からアセンブリが展開される危険性を回避するために、実稼働コンピューターには [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] をインストールしないことをお勧めします。  
  
> [!NOTE]
>  .NET Framework のランタイム セキュリティ ポリシーでは、既定でネットワーク共有からアセンブリを展開できません。 ネットワーク共有からアセンブリを展開しようとして問題が発生した場合は、.NET Framework のセキュリティ管理者に連絡するか、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 連結ヘルプ コレクションの「セキュリティ ポリシーの管理」を参照してください。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループに属するアカウントでログオンする必要があります。 場合で**展開**プロパティ、グローバル アセンブリ キャッシュ (GAC) にアセンブリをインストールするオプションを有効にし、GAC に対する読み取り/書き込みアクセス許可も必要があります。 ローカル コンピューターの管理者アカウントには、このアクセス許可があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="to-deploy-a-biztalk-assembly-or-assemblies"></a>1 つまたは複数の BizTalk アセンブリを展開するには  
  
#### <a name="using-visual-studio-solution-explorer"></a>Visual Studio ソリューション エクスプローラーを使用する場合  
  
-   [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーは、BizTalk プロジェクトまたはソリューションを右クリックし、をクリックして**展開**です。  
  
     プロジェクトのアセンブリ、またはソリューションのアセンブリが、指定した BizTalk アプリケーションに展開されます。 ページの左下隅に、ビルドおよび展開プロセスの状態が表示されます。  
  
#### <a name="using-the-visual-studio-command-prompt"></a>Visual Studio コマンド プロンプトを使用する場合  
  
1.  開始**Visual Studio コマンド プロンプト**です。  
  
2.  次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
     **devenv/deploy***SolnConfigName* *SolutionName* [**/project** *ProjName*] [**/projectconfig** *ProjConfigName*]  
  
     例:  
  
     **devenv/展開リリース"C:\Documents と Settings\someuser\My documents \visual Studio\Projects\MySolution\MySolution.sln"/"MyBizTalkApp\MyBizTalkApp.csproj"projectconfig リリースのプロジェクト**  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |**/deploy**|ビルドまたはリビルド後にソリューションを配置します。|  
    |*SolnConfigName*|SolutionName で指定したソリューションのビルドに使用されるソリューション構成の名前です。|  
    |*SolutionName*|ソリューション ファイルの完全パスと名前です。|  
    |**/project***ProjName* |ソリューション内のプロジェクト ファイルのパスと名前です。 SolutionName フォルダーからプロジェクト ファイルまでの相対パス、プロジェクトの表示名、またはプロジェクト ファイルの完全パスと名前を入力できます。|  
    |**/projectconfig***ProjConfigName* |プロジェクトをビルドするときに使用される、プロジェクトのビルド構成の名前です。|  
  
     オーケストレーションを含むアセンブリを初めて展開すると、オーケストレーションがバインド ファイルに含まれていないことを通知する警告メッセージが表示されることがあります。 これは、展開時にオーケストレーションがホストに自動的にバインドされないためです。 この手順は手動で行う必要があります。  
  
## <a name="see-also"></a>参照  
 [Visual Studio から BizTalk アプリケーションへの BizTalk アセンブリの展開](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)