---
title: "Business Rules こんにちは World2 (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, business rules
- business rules, examples
ms.assetid: 2a88a2a0-8cb6-4373-8441-0ab04345a477
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48d92d3de6b4ef6b4d541d7f64e0d483feb9c30f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="business-rules-hello-world2-biztalk-server-sample"></a>Business Rules こんにちは World2 (BizTalk Server サンプル)
Business Rules こんにちは World2 サンプルのデモで Business Rules こんにちは World1 サンプルを拡張する方法のバージョンに次のように公開、および共有 SQL ルール ストア、およびポリシーを使用して、実行する方法に設定 XML 規則を展開、**ポリシー**オブジェクトビジネス ルール フレームワークによって提供されます。 また、実行中のポリシーを動的に更新する方法についても示します。  
  
> [!NOTE]
>  このサンプルでは、製品のインストール時に、ルール エンジン更新サービスおよびビジネス ルール コンポーネントがインストールされている ([追加ソフトウェア] ノードの下) ことを前提としています。  
  
> [!NOTE]
>  使用する**ポリシー**ルール エンジンをスタンドアロン アプリケーションに統合するオブジェクト。 **ポリシー**オブジェクトの抽象化エンジンのインスタンスを管理する複数の規則では、ルール セットの取得し、共有 SQL ストアからインスタンス化、およびポリシーの更新が取得され、ホストに発行アプリケーション。  
  
 このサンプルによって構築されたファクトを参照してください、ルール セットの定義、およびサンプルについての基本的な[Business Rules こんにちは World1](../core/business-rules-hello-world1-biztalk-server-sample.md)です。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、次の一連の手順を実行する実行可能ファイルを作成します。  
  
1.  メソッドを呼び出して**CreateRuleset**ルール「解説」セクションで説明されているセットを作成します。  
  
2.  メソッドを呼び出して**SaveToFile**ファイルへのルール セットの保存を示すためにします。  
  
3.  メソッドを呼び出して**LoadFromFile**ファイルからルール セットの読み込みを示すためにします。  
  
4.  ルール セットを共有 SQL ルール ストアに展開します。  
  
5.  ルールを使用してセットを実行、**ポリシー**オブジェクト、および Business Rules こんにちは World1 で使用されるサンプル ファクトの同じセットを使用してサンプルです。  
  
6.  ファイルの設定、ルールを変更できるように、一時停止**SampleRuleStore.xml**特定の方法でします。  
  
7.  使用してもう一度設定ルールを実行、**ポリシー**オブジェクト、変更したルール セットにし、もう一度、Business Rules こんにちは World1 で使用されるサンプル ファクトの同じセットのサンプルです。  
  
8.  後でこのサンプルを実行するための準備として、ルール セット ファイルおよび展開されたルール セット レコードを削除して、クリーンアップします。  
  
> [!NOTE]
>  この SDK のすべてのサンプルに関する重要な情報は、次を参照してください。[サンプル](../core/samples-in-the-sdk.md)です。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<サンプル パス >*\Business Rules\Business こんにちは World2\ のルール  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|App.ico、AssemblyInfo.cs、BusinessRulesHelloWorld2.csproj、および BusinessRulesHelloWorld2.sln|このサンプルで、ルール セットの作成、保存、ロード、展開、実行を行う部分で使用するプロジェクト ファイル、ソリューション ファイル、その他の関連ファイルです。|  
|HelloWorld2.cs|ルールの作成を示すためにメソッドを含む visual c# ファイルの設定、ルール セットをファイルからルール セットを読み込み、ファイルの保存ルール セットの展開共有の Microsoft SQL Server ルール ストアへとによるセットのルールを実行、**ポリシー**オブジェクト。|  
|Cleanup.bat|アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。|  
|SampleDocumentInstance.xml|ファイル SampleSchema.xsd で定義されているスキーマに準拠したサンプル入力ファイルです。|  
|SampleSchema.xsd|簡潔なスキーマを定義したスキーマ ファイルで、Visual C# ファイル Class1.cs で作成されたルール セットから参照される要素が含まれます。|  
|Setup.bat|このサンプルをビルドおよび初期化するために使用されます。|  
|\HelloWorld2Library フォルダーに含まれるファイル: <br /><br /> AssemblyInfo.cs、HelloWorld2Library.csproj、HelloWorld2Library.sln|このサンプルで、作成したルール セットから参照されるオブジェクトを定義するクラスを提供する部分で使用するプロジェクト ファイル、ソリューション ファイル、その他の関連ファイルです。|  
|\HelloWorld2Library フォルダーに含まれるファイル: <br /><br /> HelloWorld2LibraryClass.cs|参照されているプロパティを含む visual c# ファイル、 **IF** 、作成した規則で呼び出されるメソッドの部分、**し**作成したルールの一部です。|  
  
### <a name="to-build-and-initialize-the-business-rules-hello-world2-sample"></a>Business Rules Hello World2 サンプルをビルドして初期化するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     *\<サンプル パス >*\Business Rules\Business こんにちは World2\ のルール  
  
2.  次の操作を実行する Setup.bat ファイルを実行します。  
  
    -   このサンプル用に [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをコンパイルし、展開します。  
  
    > [!NOTE]
    >  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。  
  
    > [!NOTE]
    >  開き、Setup.bat ファイルを実行せずにこのサンプルのプロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して、厳密な名前のキー ペアを作成する必要があります。 このキー ペアは、生成されたアセンブリの署名に使用します。  
  
    > [!NOTE]
    >  Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
### <a name="to-run-the-business-rules-hello-world2-sample"></a>Business Rules Hello World2 サンプルを実行するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     *\<サンプル パス >*\Business Rules\Business こんにちは World2\bin\Debug\ のルール  
  
2.  コマンド ウィンドウで、このサンプルのファイルの名前を入力します (**BusinessRulesHelloWorld2.exe**)、ENTER キーを押します。  
  
## <a name="hello-world2-output"></a>Hello World2 の出力  
 [コメント] セクションで説明されている、作成したルール セットの特性に基づいて[Business Rules こんにちは World1](../core/business-rules-hello-world1-biztalk-server-sample.md)提供されているサンプル入力ファイル SampleDocumentInstance.xml が定義されている (1) 1 つの値を持つと共に、このサンプルを実行する場合は、その**ID**要素を次の出力が表示されます。  
  
```  
Creating a new ruleset ...  
Saving ruleset to SampleRuleStore.xml ...  
Loading ruleset ...  
Deploying the ruleset ...  
Sleeping for 60 seconds (so that the deployed ruleset becomes effective) ...  
Grabbing the policy ...  
Executing the policy...  
MySampleBusinessObject Class -- MySampleMethod executed for object 2 with parameter 5  
MySampleBusinessObject Class -- MySampleMethod executed for object 3 with parameter 5  
The major version of the policy was: 1  
The minor version of the policy was: 0  
Press the ENTER to continue after updating the policy...  
```  
  
> [!NOTE]
>  太字で表示される出力は次のファイルに定義されているサンプル ビジネス オブジェクトによって生成される出力、 **HelloWorld2Library**フォルダーに、ルールが参照を設定します。 この時点で、アプリケーションはこの状態で待機します。  
  
 次のサンプルの実行部分では、ビジネス ルール作成ツールを使用してビジネス ルールを変更します。  
  
#### <a name="to-use-the-business-rules-composer-to-change-the-business-rules"></a>ビジネス ルール作成ツールを使用してビジネス ルールを変更するには  
  
1.  ビジネス ルール作成ツールを開くにはクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**ビジネス ルール作成ツール**です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**です。  
  
2.  SQL Server を実行しているコンピューターで SQL Server ダイアログ ボックスが表示されたら、クリックして**OK**ルール ストアに接続します。  
  
3.  **ポリシー エクスプ ローラー**、下、 **SampleRuleSet**ノード、ノードを右クリックして**バージョン 1.0-展開済み**、クリックして**コピー**です。  
  
4.  右クリック**SampleRuleSet**、クリックして**貼り付け (ポリシーのバージョン)**です。  
  
5.  ルール条件とアクションは、必要に応じて変更できます。 この手順をクリックして**rule1**で**バージョン 1.1 (未保存)**です。 右側のペインで右クリック**条件**、順にクリック**論理否定**です。 追加、**論理否定**操作を**等しくない**述語を使用すると、**等しい**述語。  
  
6.  ノードを右クリックして**バージョン 1.1 (未保存)**、クリックして**保存**です。 再度右クリックし、をクリックして**発行**です。 3 番目の時間を右クリックし、をクリックして**展開**です。  
  
7.  一時停止しているコマンド ウィンドウ (ポリシーの更新後に任意のキーを押して続行するよう要求)、任意のキーを押します。  
  
 論理否定を追加してルールを変更したとすると、実行可能ファイル BusinessRulesHelloWorld2.exe からの出力は、次のように継続されます。  
  
```  
Sleeping for 60 seconds (so that the deployed ruleset becomes effective) ...         
Grabbing the policy ...         
Executing the policy...         
MySampleBusinessObject Class -- MySampleMethod executed for object 1 with parameter 5         
The major version of the policy was: 1         
The minor version of the policy was: 1         
Press ENTER to continue after updating the policy...         
```  
  
 出力の変更内容を確認します。  
  
-   メソッドの出力行**MySampleMethod**のみのインスタンスの 1 回ここでは、印刷、 **MySampleBusinessObject**クラスを**MyValue**プロパティが 1 に等しい、前のルールと印刷のではなく、 **MyValue**プロパティが 1 と等しくないです。  
  
-   ポリシーのマイナー バージョン番号は、1 になりました。  
  
## <a name="see-also"></a>参照  
 [ビジネス ルール (BizTalk Server Samples フォルダ)](../core/business-rules-biztalk-server-samples-folder.md)