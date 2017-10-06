---
title: "チュートリアル: プログラムによって、ポリシーの実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6398e7af-2ed1-4596-879c-3b7d000b8de2
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5afbe8bd29f18e71999ff32e0a1100de8a65fcc4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-executing-the-policy-programmatically"></a>チュートリアル: プログラムによって、ポリシーの実行
このチュートリアルで作成したポリシーを呼び出すための手順では、[チュートリアル: 単純なビジネス ポリシーを作成する](../core/walkthrough-creating-a-simple-business-policy.md)チュートリアルのコンソール アプリケーションからプログラムでします。  
  
## <a name="prerequisites"></a>前提条件  
 完了する必要があります、[チュートリアル: 単純なビジネス ポリシーを作成する](../core/walkthrough-creating-a-simple-business-policy.md)チュートリアルのこのチュートリアルを実行する前にします。  
  
## <a name="overview-of-this-walkthrough"></a>このチュートリアルの概要  
 次の表に示すように、このチュートリアルには 2 つの手順が含まれています。  
  
|手順のタイトル|手順の説明|  
|---------------------|---------------------------|  
|Policy.Execute メソッドを使用して ProcessPurchaseOrder ポリシーを呼び出すには|使用してポリシーを呼び出すための手順をわかりやすく説明、 **Policy.Execute**メソッドです。|  
|RuleEngine.Execute メソッドを使用して ProcessPurchaseOrder ポリシーを呼び出すには|使用してポリシーを呼び出すための手順をわかりやすく説明、 **RuleEngine.Execute**メソッドです。|  
  
### <a name="to-invoke-the-processpurchaseorder-policy-by-using-the-policyexecute-method"></a>Policy.Execute メソッドを使用して ProcessPurchaseOrder ポリシーを呼び出すには  
  
1.  開始**Microsoft Visual Studio**です。  
  
2.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]の**ファイル**メニューのをポイント**新規**、クリックして**プロジェクト**です。  
  
3.  **新しいプロジェクト** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロジェクトの種類**|をクリックして**Visual c#**です。|  
    |**[テンプレート]**|をクリックして**コンソール アプリケーション**です。|  
    |**名前**|型**ConsoleClient**です。|  
    |**場所**|プロジェクト ファイルを保存するフォルダーを指定します。|  
    |**[ソリューション名]**|型**ConsoleClientSol**です。|  
    |**ソリューションのディレクトリを作成します。**|ソリューション ファイルのディレクトリを作成するには、このチェック ボックスをオンにします。|  
  
4.  **[OK]**をクリックします。 **ConsoleClient**プロジェクトがソリューション エクスプ ローラーで表示されます。 ソリューション エクスプ ローラーが表示されない場合はクリックして**ソリューション エクスプ ローラー**上、**ビュー**メニュー。  
  
5.  ソリューション エクスプ ローラーで右クリック**参照**、クリックして**参照の追加**です。  
  
6.  をクリックして**参照**を参照、 **\program files \microsoft BizTalk**、順にダブルクリック**[microsoft.ruleengine.dll]**です。  
  
7.  先頭に次の行を追加、 **Program.cs**後、既存のファイル`using`ステートメント。  
  
    ```  
    //To use the XmlDocument class  
    using System.Xml;  
    //To use the TypedXmlDocument and Policy classes  
    using Microsoft.RuleEngine;   
    ```  
  
8.  次のコードを追加、 **Main**を作成する関数、 **TypedXmlDocument**オブジェクトが XML ドキュメントに基づきます。  
  
    ```  
    XmlDocument doc = new XmlDocument();  
    //Loading the XML from SamplePO.xml file.  
    //Change the directory as needed  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
    ```  
  
9. 次のコードを追加、 **Main**ポリシーを実行する関数。  
  
    ```  
    //Create a policy object based on the name, ProcessPurchaseOrder  
    Policy policy = new Policy("ProcessPurchaseOrder");  
    //Execute the policy by invoking Policy.Execute method and   
    //by passing the typed xml document as a fact.   
    policy.Execute(txd);   
    ```  
  
10. 出力 XML を確認するための値を出力、**ステータス**にフィールドが設定されている**Approved**です。 なお、ビジネス ルール作成ツールとは異なりを呼び出す、 **Policy.Execute**メソッドでは、元のドキュメントは変更されません。  
  
    ```  
    //Print the output document  
    Console.WriteLine(txd.Document.OuterXml);   
    ```  
  
11. **ビルド** メニューのをクリックして**ビルド ConsoleClient**です。  
  
12. Ctrl キーを押しながら F5 キーを押して、アプリケーションを実行します。 いることを確認の値、**ステータス**にフィールドが設定されている**Approved**です。  
  
### <a name="to-invoke-the-processpurchaseorder-policy-by-using-the-ruleengineexecute-method"></a>RuleEngine.Execute メソッドを使用して ProcessPurchaseOrder ポリシーを呼び出すには  
  
1.  ソリューション エクスプ ローラーで右クリック**参照**、クリックして**参照の追加**です。  
  
2.  をクリックして**参照**を参照**\program files \microsoft BizTalk**、順にダブルクリック**Microsoft.BizTalk.RuleEngineExtensions.dll**です。  
  
3.  次の行をコメント、 **Program.cs**ファイル。  
  
    ```  
    //Create a policy object based on the name, ProcessPurchaseOrder  
    Policy policy = new Policy("ProcessPurchaseOrder");  
    //Execute the policy by invoking Policy.Execute method and   
    //by passing the typed xml document as a fact.   
    policy.Execute(txd);   
    ```  
  
4.  次のコードをコメント化したコードの後に追加して、ルール エンジン データベースにアクセスします。  
  
    ```  
    //Get access to the SQL rule store   
    Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
    dd = new Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver();  
    SqlRuleStore sqlRuleStore = (SqlRuleStore)dd.GetRuleStore();  
    ```  
  
5.  次のコードにアクセスする追加**RuleSetInfoCollection** ProcessPurchaseOrder ポリシー。  
  
    ```  
    //Get access to RuleSetInfoCollection for the   
    //ProcessPurchaseOrder policy  
    RuleSetInfoCollection rsic = sqlRuleStore.GetRuleSets("ProcessPurchaseOrder", RuleStore.Filter.All);  
    ```  
  
6.  次のコード作成を追加、 **RuleSet** ProcessPurchaseOrder ポリシーのルール セット情報に基づいてオブジェクト。  
  
    ```  
    //Create a RuleSet object based on the rule set information   
    //for the ProcessPurchaseOrder policy  
    RuleSet rs = sqlRuleStore.GetRuleSet(rsic[0]);  
    ```  
  
7.  次のコード作成を追加、 **RuleEngine**オブジェクト。  
  
    ```  
    //Create the RuleEngine object  
    Microsoft.RuleEngine.RuleEngine engine = new Microsoft.RuleEngine.RuleEngine(rs);  
    ```  
  
8.  Assert を次のコードを追加、 **TypedXmlDocument**ルール エンジンの作業メモリにオブジェクト。  
  
    ```  
    //Assert the TypedXmlDocument object into working memory  
    //of the rule engine  
    engine.Assert(txd);  
    ```  
  
9. 使用してポリシーを実行するコードを追加、 **RuleEngine.Execute**メソッド。  
  
    ```  
    //Execute the policy by invoking RuleEngine.Execute method  
    engine.Execute();  
    ```  
  
10. 確認して、 **Console.WriteLine**ステートメントは、最後のステートメントで、 **Main**関数。  
  
11. **ビルド** メニューのをクリックして**ビルド ConsoleClient**です。  
  
12. Ctrl キーを押しながら F5 キーを押して、アプリケーションを実行します。 いることを確認の値、**ステータス**にフィールドが設定されている**Approved**です。  
  
## <a name="comments"></a>コメント  
  
-   コードを完了、 **Main**を使用して ProcessPurchaseOrder ポリシーを実行する関数、 **Policy.Execute**メソッドを次に示します。  
  
    ```  
    static void Main(string[] args)  
    {  
    XmlDocument doc = new XmlDocument();  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
    Policy policy = new Policy("ProcessPurchaseOrder");  
    policy.Execute(txd);  
    Console.WriteLine(txd.Document.OuterXml);   
    }  
    ```  
  
-   使用して ProcessPurchaseOrder ポリシーを実行するためのコードを完了、 **RuleEngine.Execute**メソッドを次に示します。  
  
    ```  
    static void Main(string[] args)  
    {  
    XmlDocument doc = new XmlDocument();  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
    Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
    dd = new Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver();  
    SqlRuleStore sqlRuleStore = (SqlRuleStore)dd.GetRuleStore();  
    RuleSetInfoCollection rsic = sqlRuleStore.GetRuleSets("ProcessPurchaseOrder", RuleStore.Filter.All);  
    RuleSet rs = sqlRuleStore.GetRuleSet(rsic[0]);  
    Microsoft.RuleEngine.RuleEngine engine = new Microsoft.RuleEngine.RuleEngine(rs);  
    engine.Assert(txd);  
    engine.Execute();  
    Console.WriteLine(txd.Document.OuterXml);   
    }  
    ```  
  
-   追加することがあります、 **Console.ReadLine()**ステートメントの最後に、 **Main**アプリケーションが待機すると、アプリケーションを終了するように機能します。  
  
-   このチュートリアルでは、クライアントが ProcessPurchaseOrder ポリシーに送信するファクトは 1 つだけです。 ファクトの配列を作成し、オーバー ロードを使用する必要がある場合は、クライアントは、1 つ以上のファクトをポリシーを送信する必要があります、 **Execute**メソッド パラメーターとして配列を受け取る。 次のサンプル コードは、その方法を示しています。  
  
    ```  
    Policy policy = new Policy("PolicyName");  
    object[] facts = new object[2];  
    facts[0] = txd;  
    facts[1] = new MyClass();  
    policy.Execute(facts);  
    policy.Dispose();  
    ```  
  
-   最初のパラメーター、 **TypedXmlDocument**コードでコンス トラクターは、ポリシーの構築に使用した型の名前。  
  
-   **Policy.Execute**メソッドがラップするラッパーでは基本的に、 **RuleEngine.Execute**メソッドです。 したがってを使用して、 **Policy.Execute**メソッドは、このチュートリアルで説明したように、ポリシーを呼び出すの最も簡単な方法です。  
  
-   使用する、ポリシーの実行をより細かく制御する可能性があります、 **RuleEngine.Execute**メソッドを使用してではなく**Policy.Execute**です。 使用してエンジンを一時的に停止するなど、**停止**関数とを使用して、再開、 **Execute**関数。 詳細については、次を参照してください。[停止](../core/halt.md)です。  
  
## <a name="see-also"></a>参照  
 [ポリシーを実行する方法](../core/how-to-execute-policies.md)