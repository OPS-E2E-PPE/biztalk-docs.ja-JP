---
title: "Business Rules こんにちは World1 (BizTalk Server サンプル) |Microsoft ドキュメント"
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
ms.assetid: 0623ad20-96cc-430e-bb36-35431a5d17ee
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7231fd0d2aba7298127534eb43f1bf3c8c453b61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="business-rules-hello-world1-biztalk-server-sample"></a>Business Rules こんにちは World1 (BizTalk Server サンプル)
Business Rules Hello World1 サンプルでは、BizTalk ルール セットを作成して、そのルール セットをファイル (SampleRuleSet.xml) に保存し、読み込んでから、サンプルのファクト セットに基づいて実行する方法を示します。 サンプルのルール セットには、ルール定義の条件として XML 要素を含む単一のルール、および .NET ベースのオブジェクト (プロパティとメンバ) が含まれます。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、次の一連の手順を実行する実行可能ファイルを作成します。  
  
1.  メソッドを呼び出して**CreateRuleset**ルール「解説」セクションで説明されているセットを作成します。  
  
2.  メソッドを呼び出して**SaveToFile**ファイルへのルール セットの保存を示すためにします。  
  
3.  メソッドを呼び出して**LoadFromFile**ファイルからルール セットの読み込みを示すためにします。  
  
4.  ルール セットの実行対象のサンプル ファクトを作成します。  
  
5.  サンプル ファクトに対してルール セットを実行し、画面出力を作成します。  
  
6.  一時停止し、ルール セット ファイル SampleRuleStore.xml を確認できるようにします。  
  
7.  後でこのサンプルを実行するための準備として、ルール セット ファイルを削除して、クリーンアップします。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*パスのサンプル*> \Business Rules\Business こんにちは World1\ のルール  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|App.ico、AssemblyInfo.cs、BusinessRulesHelloWorld1.csproj、および BusinessRulesHelloWorld1.sln|このサンプルで、ルール セットの作成、保存、読み込み、実行を行う部分で使用するプロジェクト ファイル、ソリューション ファイル、その他の関連ファイルです。|  
|HelloWorld1.cs|ルール セットの作成、ファイルへのルール セットの保存、およびファイルからルール セットを読み込む方法を示すメソッドを含む Visual C# ファイルです。 これらのメソッドを呼び出し、作成したルール セットを実行する、前後のコードも含まれます。|  
|Cleanup.bat|アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。|  
|SampleDocumentInstance.xml|ファイル SampleSchema.xsd で定義されているスキーマに準拠したサンプル入力ファイルです。|  
|SampleSchema.xsd|簡潔なスキーマを定義したスキーマ ファイルで、Visual C# ファイル HelloWorld1.cs で作成されたルール セットから参照される要素が含まれます。|  
|Setup.bat|このサンプルをビルドおよび初期化するために使用されます。|  
|\MySampleLibrary フォルダーに含まれるファイル: <br /><br /> AssemblyInfo.cs、MySampleLibrary.csproj、および MySampleLibrary.sln|このサンプルで、作成したルール セットから参照されるオブジェクトを定義するクラスを提供する部分で使用するプロジェクト ファイル、ソリューション ファイル、その他の関連ファイルです。|  
|\MySampleLibrary フォルダーに含まれるファイル: <br /><br /> MySampleLibraryClass.cs|参照されているプロパティを含む visual c# ファイル、 **IF** 、作成した規則で呼び出されるメソッドの部分、**し**作成したルールの一部です。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 次の手順を使用して、Business Rules Hello World1 サンプルの作成および初期化を行います。  
  
#### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*> \Business Rules\Business こんにちは World1\ のルール  
  
2.  次の操作を実行する Setup.bat ファイルを実行します。  
  
    -   コンパイルし、展開、Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルのプロジェクトです。  
  
    > [!NOTE]
    >  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。  
  
    > [!NOTE]
    >  開き、Setup.bat ファイルを実行せずにこのサンプルのプロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して、厳密な名前のキー ペアを作成する必要があります。 このキー ペアは、生成されたアセンブリの署名に使用します。  
  
    > [!NOTE]
    >  Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
 次の手順を使用して、Business Rules Hello World1 サンプルを実行します。  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*> \Business Rules\Business こんにちは World1\bin\Debug\ のルール  
  
2.  コマンド ウィンドウで、このサンプルの実行可能ファイル名 (BusinessRulesHelloWorld1.exe) を入力して、<localizedText>Enter</localizedText> キーを押します。  
  
    > [!NOTE]
    >  実行中に、この サンプルが生成されますが、ルール セット ファイル SampleRuleStore.xml で、 **bin \debug**フォルダーです。 実行可能ファイルを一時停止すると、<localizedText>Enter</localizedText> キーを押すまで終了が待機されるので、このファイルの内容を確認できます。 このファイルは、任意のキーを押して終了する前に閉じてください。 これを行わないと、後でこのサンプルを実行するための準備として、実行可能ファイルからこのファイルを削除できません。  
  
 提供されているサンプル入力ファイル SampleDocumentInstance.xml に対して定義されている (1) 1 つの値を持つと共に、このサンプルを実行する場合は、作成したルール セットの特性に基づいてその**ID**要素を次の出力が表示されます。  
  
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
>  太字、上記のコードでは両方と、次のコードでは、出力によって生成されるファイルに定義されているサンプル ビジネス オブジェクトに示す出力、 **MySampleLibrary**規則セットで参照されているフォルダーです。  
  
 関連付けられている値を変更する場合、 **ID**サンプル入力ファイル内の要素**SampleDocumentInstance.xml**から 1 つ (1 2 (2) に、出力はように変更します。  
  
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
  
 オブジェクトの場合、出力行は取得されません、 **MySampleBusinessObject**を持つクラス、 **MyValue**プロパティ、に関連付けられている値と一致する値(構築時)に設定します。**ID**サンプル入力ファイル SampleDocumentInstance.xml 内の要素。  
  
## <a name="comments"></a>コメント  
 内にプログラムで作成したルール、 **CreateRuleset()**メソッドに示します。  
  
 **もし**  
  
 **MySampleBusinessObject.MyValue**がの値と等しくない、 **ID** XML ドキュメント内の要素。  
  
 **そうしたら**  
  
 **MySampleBusinessObject.MySampleMethod(int)**整数のパラメータをハードここでは、定数 5 (5) するようにコーディングします。 このメソッドが始まる出力行を生成する**MySampleBusinessObject Class –-**です。  
  
 このルールは、次の要因に依存します。  
  
-   A **MySampleBusinessObject**というパブリック プロパティを持つクラス**MyValue**され、パブリック メソッドが呼び出されます**MySampleMethod** (整数のパラメータを所要時間)。  
  
-   含む XML ドキュメントを定義する XML スキーマ定義言語 (XSD) スキーマ、 **ID**要素。  
  
 ルールは、クラスやスキーマとして定義しますが、実行中の場合は、関連するクラスのオブジェクト インスタンスおよび関連するスキーマのドキュメント インスタンスが必要です。 このような実行時のインスタンス (ファクト) に対してルールを評価します。 このサンプルでは、ファクトはの複数のインスタンス、 **MySampleBusinessObject**の値が異なる構築されたオブジェクト、 **MyValue**プロパティ、および定義済みのスキーマの単一の XML インスタンス値を格納している、 **ID**要素。  
  
## <a name="see-also"></a>参照  
 [ビジネス ルール (BizTalk Server Samples フォルダ)](../core/business-rules-biztalk-server-samples-folder.md)