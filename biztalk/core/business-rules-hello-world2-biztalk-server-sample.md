---
title: Business Rules こんにちは World2 (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, business rules
- business rules, examples
ms.assetid: 2a88a2a0-8cb6-4373-8441-0ab04345a477
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ccc78579c9febfa93b489d72c40ccb603bed92a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972811"
---
# <a name="business-rules-hello-world2-biztalk-server-sample"></a>Business Rules こんにちは World2 (BizTalk Server サンプル)
Business Rules こんにちは World2 サンプルを説明 Business Rules こんにちは World1 サンプルを拡張する方法のバージョンに次のように公開、および共有 SQL ルール ストア、およびポリシーを使用して、実行する方法に設定 XML 規則を展開、**ポリシー**オブジェクトビジネス ルール フレームワークによって提供されます。 また、実行中のポリシーを動的に更新する方法についても示します。  
  
> [!NOTE]
>  このサンプルでは、製品のインストール時に、ルール エンジン更新サービスおよびビジネス ルール コンポーネントがインストールされている ([追加ソフトウェア] ノードの下) ことを前提としています。  
  
> [!NOTE]
>  使用する**ポリシー**をスタンドアロン アプリケーションにルール エンジンを統合するオブジェクト。 **ポリシー**オブジェクトの抽象化を通じて複数のルール エンジン インスタンスの管理には、規則セットの取得し、共有 SQL ストアからインスタンス化し、ポリシーの更新が取得され、ホストに発行アプリケーション。  
  
 このサンプルでは、によって構築されたファクトを参照してください、ルール セットの定義、およびサンプルについての基本的な[Business Rules こんにちは World1](../core/business-rules-hello-world1-biztalk-server-sample.md)します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、次の一連の手順を実行する実行可能ファイルを作成します。  
  
1.  メソッドを呼び出して**CreateRuleset** 「解説」セクションで説明されている設定ルールを作成しますします。  
  
2.  メソッドを呼び出して**SaveToFile**を示すファイルへのルール セットを保存します。  
  
3.  メソッドを呼び出して**LoadFromFile**を読み込み、ファイルからルール セットを示すためにします。  
  
4.  ルール セットを共有 SQL ルール ストアに展開します。  
  
5.  ルールを使用してセットの実行、**ポリシー**オブジェクト、および Business Rules こんにちは World1 で使用されるサンプル ファクトの同じセットを使用してサンプルします。  
  
6.  一時停止し、ファイルの設定、ルールを変更することを有効にする**SampleRuleStore.xml**特定の方法でします。  
  
7.  ルール セットを使用して再度の実行、**ポリシー**オブジェクト、変ルールは、設定し、もう一度、Business Rules こんにちは World1 で使用されるサンプル ファクトの同じセットのサンプルです。  
  
8.  後でこのサンプルを実行するための準備として、ルール セット ファイルおよび展開されたルール セット レコードを削除して、クリーンアップします。  
  
> [!NOTE]
>  この SDK のすべてのサンプルに関する重要な情報は、[サンプル](../core/samples-in-the-sdk.md)を参照してください。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<パスのサンプル\>* \Business Rules\Business こんにちは World2\ のルール  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|---------------|-----------------|  
|App.ico、AssemblyInfo.cs、BusinessRulesHelloWorld2.csproj、および BusinessRulesHelloWorld2.sln|このサンプルで、ルール セットの作成、保存、ロード、展開、実行を行う部分で使用するプロジェクト ファイル、ソリューション ファイル、その他の関連ファイルです。|  
|HelloWorld2.cs|方法を示すルールを作成するメソッドを含む visual c# ファイルの設定、ルール セット ファイルからのルール セットを読み込み、ファイルの保存ルール セットの展開共有の Microsoft SQL Server ルール ストアにおよびによるセットのルールを実行し、**ポリシー**オブジェクト。|  
|Cleanup.bat|アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。|  
|SampleDocumentInstance.xml|ファイル SampleSchema.xsd で定義されているスキーマに準拠したサンプル入力ファイルです。|  
|SampleSchema.xsd|簡潔なスキーマを定義したスキーマ ファイルで、Visual C# ファイル Class1.cs で作成されたルール セットから参照される要素が含まれます。|  
|Setup.bat|このサンプルをビルドおよび初期化するために使用されます。|  
|\HelloWorld2Library フォルダーに含まれるファイル: <br /><br /> AssemblyInfo.cs、HelloWorld2Library.csproj、HelloWorld2Library.sln|このサンプルで、作成したルール セットから参照されるオブジェクトを定義するクラスを提供する部分で使用するプロジェクト ファイル、ソリューション ファイル、その他の関連ファイルです。|  
|\HelloWorld2Library フォルダーに含まれるファイル: <br /><br /> HelloWorld2LibraryClass.cs|参照されているプロパティを含む visual c# ファイル、**場合**、作成した規則で呼び出されるメソッドの部分、**し**作成した規則の一部です。|  
  
### <a name="to-build-and-initialize-the-business-rules-hello-world2-sample"></a>Business Rules Hello World2 サンプルをビルドして初期化するには  
  
1. コマンド ウィンドウで、次のフォルダーに移動します。  
  
    *\<パスのサンプル\>* \Business Rules\Business こんにちは World2\ のルール  
  
2. ファイルは、次の操作を実行します。 Setup.bat を実行します。  
  
   - このサンプル用に [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをコンパイルし、展開します。  
  
   > [!NOTE]
   >  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。  
   > 
   > [!NOTE]
   >  開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。 このキー ペアは、生成されたアセンブリの署名に使用します。  
   > 
   > [!NOTE]
   >  Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
### <a name="to-run-the-business-rules-hello-world2-sample"></a>Business Rules Hello World2 サンプルを実行するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     *\<パスのサンプル\>* \Business Rules\Business こんにちは World2\bin\Debug\ のルール  
  
2.  コマンド ウィンドウで、このサンプルのファイルの名前を入力します (**BusinessRulesHelloWorld2.exe**)、し、ENTER キーを押します。  
  
## <a name="hello-world2-output"></a>Hello World2 の出力  
 [コメント] セクションで説明されている、作成したルール セットの特性に基づいて[Business Rules こんにちは World1](../core/business-rules-hello-world1-biztalk-server-sample.md)で提供されているサンプル入力ファイル SampleDocumentInstance.xml 定義 (1) 1 つの値を持つこのサンプルを実行する場合は、その**ID**要素では、次の出力が表示されます。  
  
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
>  太字で表示される出力がファイルに定義されているサンプル ビジネス オブジェクトによって生成される出力、 **HelloWorld2Library**ルール セットから参照するフォルダー。 この時点で、アプリケーションはこの状態で待機します。  
  
 次のサンプルの実行部分では、ビジネス ルール作成ツールを使用してビジネス ルールを変更します。  
  
#### <a name="to-use-the-business-rules-composer-to-change-the-business-rules"></a>ビジネス ルール作成ツールを使用してビジネス ルールを変更するには  
  
1. ビジネス ルール作成ツールを開くには、次のようにクリックします。**開始**、 をクリック**すべてのプログラム**、 をクリック[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリックし、**ビジネス ルール作成ツール**。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
2. SQL Server を実行するコンピューターで、SQL Server ダイアログ ボックスが表示されたら、クリックして**OK**ルール ストアに接続します。  
  
3. **ポリシー エクスプ ローラー**下の**SampleRuleSet**ノード、ノードを右クリックして**バージョン 1.0-展開済み**、 をクリックし、**コピー**します。  
  
4. 右クリックして**SampleRuleSet**、 をクリックし、**貼り付け (ポリシーのバージョン)** します。  
  
5. ルール条件とアクションは、必要に応じて変更できます。 この手順では、次のようにクリックします。 **rule1**で**バージョン 1.1 (未保存)** します。 右側のウィンドウで右クリック**条件**、 をクリックし、**論理否定の追加**します。 追加、**論理否定**操作を**等しく**述語を使用することは、**と等しい**述語。  
  
6. ノードを右クリックして**バージョン 1.1 (未保存)**、 をクリックし、**保存**します。 ここでもを右クリックし、をクリックし、**発行**します。 3 番目の時間を右クリックし、をクリックして**デプロイ**します。  
  
7. 一時停止しているコマンド ウィンドウ (ポリシーの更新後に任意のキーを押して続行するよう要求)、任意のキーを押します。  
  
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
  
-   メソッド内の出力行**MySampleMethod**しかここで 1 回は、インスタンスの出力、 **MySampleBusinessObject**クラスを**MyValue**プロパティが 1 に等しい、以前のルールのではなく、 **MyValue**プロパティが 1 と等しくありません。  
  
-   ポリシーのマイナー バージョン番号は、1 になりました。  
  
## <a name="see-also"></a>参照  
 [ビジネス ルール (BizTalk Server サンプル フォルダー)](../core/business-rules-biztalk-server-samples-folder.md)