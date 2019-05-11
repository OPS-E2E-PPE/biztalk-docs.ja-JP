---
title: Business Rules こんにちは World1 (BizTalk Server サンプル) |Microsoft Docs
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
ms.assetid: 0623ad20-96cc-430e-bb36-35431a5d17ee
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48097f4803aba02c19abbd0a1a48c7f9103545c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357668"
---
# <a name="business-rules-hello-world1-biztalk-server-sample"></a>Business Rules こんにちは World1 (BizTalk Server サンプル)
Business Rules こんにちは World1 サンプルでは、BizTalk ルール セットを作成、ファイル (SampleRuleSet.xml) に保存、読み込み、およびサンプルのファクト セットに基づいて実行する方法を示します。 サンプルのルール セットが XML 要素を含む単純なルールを含むとします。NET ベースのオブジェクト (プロパティとメンバ) ルールの定義の条件として。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、次の一連の手順を実行する実行可能ファイルを作成します。  
  
1.  メソッドを呼び出して**CreateRuleset** 「解説」セクションで説明されている設定ルールを作成しますします。  
  
2.  メソッドを呼び出して**SaveToFile**を示すファイルへのルール セットを保存します。  
  
3.  メソッドを呼び出して**LoadFromFile**を読み込み、ファイルからルール セットを示すためにします。  
  
4.  構成要素のサンプル ファクトに対してルール セットを実行します。  
  
5.  画面出力を生成する、サンプル ファクトに対してルール セットを実行します。  
  
6.  一時停止し、ファイル SampleRuleStore.xml を設定をルールを確認します。  
  
7.  サンプルの後続の実行の準備のルール セット ファイルを削除してクリーンアップします。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*パスのサンプル*\>\Business Rules\Business こんにちは World1\ のルール  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|---------------|-----------------|  
|App.ico, AssemblyInfo.cs, BusinessRulesHelloWorld1.csproj, BusinessRulesHelloWorld1.sln|プロジェクト、ソリューション、および他の関連ファイルを作成、保存、このサンプルの一部が読み込まれ、ルール セットを実行します。|  
|HelloWorld1.cs|VisualC#ファイルからルール セットを作成する、規則セットをファイルに保存、およびルールの読み込みを示すためにメソッドを含むファイルを設定します。 これらのメソッドを呼び出すし、作成したルール セットを実行する前後のコードも含まれています。|  
|Cleanup.bat|アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。|  
|SampleDocumentInstance.xml|ファイル SampleSchema.xsd で定義されているスキーマに準拠したサンプル入力ファイルです。|  
|SampleSchema.xsd|セットは、ビジュアルの作成ルールによって参照される要素を単純なスキーマを定義したスキーマ ファイルC#ファイル HelloWorld1.cs します。|  
|Setup.bat|このサンプルをビルドおよび初期化するために使用されます。|  
|\MySampleLibrary フォルダーには。<br /><br /> AssemblyInfo.cs、MySampleLibrary.csproj、および MySampleLibrary.sln|このサンプルで、作成したルール セットから参照されるオブジェクトを定義するクラスを提供する部分で使用するプロジェクト ファイル、ソリューション ファイル、その他の関連ファイルです。|  
|\MySampleLibrary フォルダーには。<br /><br /> MySampleLibraryClass.cs|参照されているプロパティを含む visual c# ファイル、**場合**、作成した規則で呼び出されるメソッドの部分、**し**作成した規則の一部です。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 ビルドおよび初期化する Business Rules こんにちは World1 サンプルを次の手順を使用します。  
  
#### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  
  
1. コマンド ウィンドウで、次のフォルダーに移動します。  
  
    \<*パスのサンプル*\>\Business Rules\Business こんにちは World1\ のルール  
  
2. ファイルは、次の操作を実行します。 Setup.bat を実行します。  
  
   - コンパイルし、Microsoft の展開[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルのプロジェクト。  
  
   > [!NOTE]
   >  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。  
   > 
   > [!NOTE]
   >  開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。 このキー ペアは、生成されたアセンブリの署名に使用します。  
   > 
   > [!NOTE]
   >  Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
 Business Rules こんにちは World1 サンプルを実行するのにには、次の手順を使用します。  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1. コマンド ウィンドウで、次のフォルダーに移動します。  
  
    \<*パスのサンプル*\>\Business Rules\Business こんにちは World1\bin\Debug\ のルール  
  
2. コマンド ウィンドウで (BusinessRulesHelloWorld1.exe)、このサンプルの実行可能ファイルの名前を入力し、ENTER キーを押します。  
  
   > [!NOTE]
   >  規則セット ファイル SampleRuleStore.xml このサンプルでの実行中に、 **bin \debug**フォルダー。 実行可能ファイルが一時停止したときにすると、完了、ENTER キーを押すを待つことができますを確認するこのファイルの内容。 終了する任意のキーを押す前に閉じることに注意してください。 それ以外の場合、実行可能ファイルは、サンプルの後続の実行の準備では削除できません可能性があります。  
  
   提供されているサンプル入力ファイル SampleDocumentInstance.xml に対して定義されている (1) 1 つの値を持つこのサンプルを実行する場合、作成したルール セットの特性に基づき、 **ID**要素、次の出力が表示されます。  
  
```  
Creating a new ruleset ...  
Saving ruleset to SampleRuleStore.xml ...  
Loading ruleset ...  
Asserting objects ...  
Executing ...  
MySampleBusinessObject Class -- MySampleMethod executed for object 2 with parameter 5  
MySampleBusinessObject Class -- MySampleMethod executed for object 3 with parameter 5  
Press any key to finish ...  
```  
  
> [!NOTE]
>  太字、上記のコードでは両方と、次のコードでは、出力によって生成されたファイルに定義されているサンプル ビジネス オブジェクトに示した出力、 **MySampleLibrary**フォルダーで、ルール セットによって参照されています。  
  
 関連付けられている値を変更する場合、 **ID**サンプル入力ファイル内の要素**SampleDocumentInstance.xml**から 1 つ (1) に 2 つ (2)、出力はように変更します。  
  
```  
Creating a new ruleset ...  
Saving ruleset to SampleRuleStore.xml ...  
Loading ruleset ...  
Asserting objects ...  
Executing ...  
MySampleBusinessObject Class -- MySampleMethod executed for object 1 with parameter 5  
MySampleBusinessObject Class -- MySampleMethod executed for object 3 with parameter 5  
Press any key to finish ...  
```  
  
 オブジェクトの場合、出力行は取得されません、 **MySampleBusinessObject**を持つクラス、 **MyValue**プロパティ、に関連付けられている値と一致する値(構築時)に設定**ID**サンプル入力ファイル SampleDocumentInstance.xml 内の要素。  
  
## <a name="comments"></a>コメント  
 内にプログラムで作成した規則、 **CreateRuleset()** メソッドに示します。  
  
 **IF**  
  
 **MySampleBusinessObject.MyValue**の値と等しく、 **ID** XML ドキュメント内の要素。  
  
 **THEN**  
  
 **MySampleBusinessObject.MySampleMethod(int)** パラメーターを使用して、整数、ハードここでは、定数 5 (5) にコード化されました。 このメソッドが始まる出力行を生成**MySampleBusinessObject Class –-** します。  
  
 このルールは、次に依存します。  
  
- A **MySampleBusinessObject**というパブリック プロパティを持つクラス**MyValue**というパブリック メソッドと**MySampleMethod** (整数パラメーターで受け取る)。  
  
- 含む XML ドキュメントを定義する XML スキーマ定義言語 (XSD) スキーマ、 **ID**要素。  
  
  クラスと、スキーマの観点から規則を定義するが、実行中に、関連するクラスのオブジェクトのインスタンスと、適切なスキーマのドキュメント インスタンスが必要です。 これらの実行時インスタンス (ファクトと呼ばれます) に対してルールを評価します。 このサンプルでは、ファクトはの複数のインスタンス、 **MySampleBusinessObject**に別の値を使用して構築されているオブジェクト、 **MyValue**プロパティ、および定義済みのスキーマの単一の XML インスタンス値を格納している、 **ID**要素。  
  
## <a name="see-also"></a>参照  
 [ビジネス ルール (BizTalk Server サンプル フォルダー)](../core/business-rules-biztalk-server-samples-folder.md)