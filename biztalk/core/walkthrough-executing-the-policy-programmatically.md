---
title: 'チュートリアル: プログラムによって、ポリシーの実行 |Microsoft Docs'
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6398e7af-2ed1-4596-879c-3b7d000b8de2
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 666b674e30e548489478af898d5fe88c47d21f14
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985723"
---
# <a name="walkthrough-executing-the-policy-programmatically"></a>チュートリアル: プログラムによって、ポリシーの実行
このチュートリアルでは、詳細な手順で作成したポリシーを呼び出す、[チュートリアル: 単純なビジネス ポリシーを作成する](../core/walkthrough-creating-a-simple-business-policy.md)コンソール アプリケーションからチュートリアル プログラムを使用します。  

## <a name="prerequisites"></a>前提条件  
 完了する必要があります、[チュートリアル: 単純なビジネス ポリシーを作成する](../core/walkthrough-creating-a-simple-business-policy.md)チュートリアルのこのチュートリアルを実行する前にします。  

## <a name="overview-of-this-walkthrough"></a>このチュートリアルの概要  
 次の表に示すように、このチュートリアルには 2 つの手順が含まれています。  

|プロシージャ タイトル|手順の説明|  
|---------------------|---------------------------|  
|Policy.Execute メソッドを使用して ProcessPurchaseOrder ポリシーを呼び出すには|使用してポリシーを呼び出すための手順について説明します、 **Policy.Execute**メソッド。|  
|RuleEngine.Execute メソッドを使用して ProcessPurchaseOrder ポリシーを呼び出すには|使用してポリシーを呼び出すための手順について説明します、 **RuleEngine.Execute**メソッド。|  

### <a name="to-invoke-the-processpurchaseorder-policy-by-using-the-policyexecute-method"></a>Policy.Execute メソッドを使用して ProcessPurchaseOrder ポリシーを呼び出すには  

1. 開始**Microsoft Visual Studio**します。  

2. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。  

3. **新しいプロジェクト** ダイアログ ボックスで、次の操作を行います。  


   |             プロパティ              |                             目的                              |
   |-----------------------------------|---------------------------------------------------------------------|
   |         **プロジェクトの種類**         |                        クリックして**Visual c#** します。                         |
   |           **[テンプレート]**           |                   クリックして**コンソール アプリケーション**します。                    |
   |             **名前**              |                       型**ConsoleClient**します。                       |
   |           **場所**            |     プロジェクト ファイルを保存するフォルダーを指定します。      |
   |         **[ソリューション名]**         |                     型**ConsoleClientSol**します。                      |
   | **ソリューションのディレクトリを作成します。** | ソリューション ファイルのディレクトリを作成するには、このチェック ボックスをオンにします。 |


4. **[OK]** をクリックします。 **ConsoleClient**プロジェクトがソリューション エクスプ ローラーで表示されます。 ソリューション エクスプ ローラーが表示されない場合はクリックして**ソリューション エクスプ ローラー**上、**ビュー**メニュー。  

5. ソリューション エクスプ ローラーで右クリックして**参照**、 をクリックし、**参照の追加**します。  

6. をクリックして**参照**を参照、 **\Program Files\Common files \microsoft BizTalk**、し、ダブルクリック **[microsoft.ruleengine.dll]** します。  

7. 先頭に次の行を追加、 **Program.cs**既存の後にファイルを`using`ステートメント。  

   ```  
   //To use the XmlDocument class  
   using System.Xml;  
   //To use the TypedXmlDocument and Policy classes  
   using Microsoft.RuleEngine;   
   ```  

8. 次のコードを追加、 **Main**関数を作成する、 **TypedXmlDocument**オブジェクトが XML ドキュメントに基づきます。  

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

10. 値を確認するための XML 出力に出力、**状態**にフィールドが設定されている**Approved**します。 なお、ビジネス ルール作成ツールとは異なりを呼び出す、 **Policy.Execute**メソッドでは、元のドキュメントは変更されません。  

    ```  
    //Print the output document  
    Console.WriteLine(txd.Document.OuterXml);   
    ```  

11. **ビルド** メニューのをクリックして**ビルド ConsoleClient**します。  

12. Ctrl キーを押しながら F5 キーを押して、アプリケーションを実行します。 いることを確認の値、**状態**にフィールドが設定されている**Approved**。  

### <a name="to-invoke-the-processpurchaseorder-policy-by-using-the-ruleengineexecute-method"></a>RuleEngine.Execute メソッドを使用して ProcessPurchaseOrder ポリシーを呼び出すには  

1.  ソリューション エクスプ ローラーで右クリックして**参照**、 をクリックし、**参照の追加**します。  

2.  をクリックして**参照**を参照**\Program Files\Common files \microsoft BizTalk**、し、ダブルクリック**Microsoft.BizTalk.RuleEngineExtensions.dll**します。  

3.  次の行をコメント アウト、 **Program.cs**ファイル。  

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

5.  次のコードにアクセスする追加**RuleSetInfoCollection** ProcessPurchaseOrder ポリシーの。  

    ```  
    //Get access to RuleSetInfoCollection for the   
    //ProcessPurchaseOrder policy  
    RuleSetInfoCollection rsic = sqlRuleStore.GetRuleSets("ProcessPurchaseOrder", RuleStore.Filter.All);  
    ```  

6.  作成する次のコードを追加、 **RuleSet** ProcessPurchaseOrder ポリシーのルール セットの情報に基づいて、オブジェクト。  

    ```  
    //Create a RuleSet object based on the rule set information   
    //for the ProcessPurchaseOrder policy  
    RuleSet rs = sqlRuleStore.GetRuleSet(rsic[0]);  
    ```  

7.  作成する次のコードを追加、 **RuleEngine**オブジェクト。  

    ```  
    //Create the RuleEngine object  
    Microsoft.RuleEngine.RuleEngine engine = new Microsoft.RuleEngine.RuleEngine(rs);  
    ```  

8.  アサートする次のコードを追加、 **TypedXmlDocument**ルール エンジンの作業メモリにオブジェクト。  

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

10. 確認、 **Console.WriteLine**ステートメントが最後のステートメントで、 **Main**関数。  

11. **ビルド** メニューのをクリックして**ビルド ConsoleClient**します。  

12. Ctrl キーを押しながら F5 キーを押して、アプリケーションを実行します。 いることを確認の値、**状態**にフィールドが設定されている**Approved**。  

## <a name="comments"></a>コメント  

-   コードを完了、 **Main**関数を使用して ProcessPurchaseOrder ポリシーを実行する、 **Policy.Execute**メソッドを次に示します。  

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

-   使用して ProcessPurchaseOrder ポリシーを実行するためのコードの完了、 **RuleEngine.Execute**メソッドを次に示します。  

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

-   追加することがあります、 **Console.ReadLine()** ステートメントの最後に、 **Main**アプリケーションがアプリケーションを終了するまで待機するように機能します。  

-   このチュートリアルでは、クライアントが ProcessPurchaseOrder ポリシーに送信するファクトは 1 つだけです。 ファクトの配列を作成して、オーバー ロードを使用する必要がある場合は、クライアントは、1 つ以上のファクトをポリシーを送信する必要があります、 **Execute**をパラメーターとして配列を受け取るメソッド。 次のサンプル コードは、その方法を示しています。  

    ```  
    Policy policy = new Policy("PolicyName");  
    object[] facts = new object[2];  
    facts[0] = txd;  
    facts[1] = new MyClass();  
    policy.Execute(facts);  
    policy.Dispose();  
    ```  

-   最初のパラメーター、 **TypedXmlDocument**コンス トラクターのコードでは、ポリシーの構築に使用する型の名前です。  

-   **Policy.Execute**メソッドは、ラッパーでは基本的に、 **RuleEngine.Execute**メソッド。 したがってを使用して、 **Policy.Execute**メソッドでは、このチュートリアルで説明したように、ポリシーを呼び出すの最も簡単な方法です。  

-   使用するポリシーの実行をより細かく制御することがあります、 **RuleEngine.Execute**メソッドを使用してではなく**Policy.Execute**します。 使用して、エンジンを一時的に停止するなど、 **Halt**関数とを使用して、再開、 **Execute**関数。 詳細については、[Halt](../core/halt.md)を参照してください。  

## <a name="see-also"></a>参照  
 [ポリシーを実行する方法](../core/how-to-execute-policies.md)