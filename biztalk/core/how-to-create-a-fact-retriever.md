---
title: ファクト取得コンポーネントを作成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IFactRetriever interface
- Business Rules Framework, bindings
- factsHandleIn object
- Business Rules Framework, code samples
- Business Rules Framework, fact retrievers
- UpdateFacts method
- Business Rules Framework, programming
ms.assetid: 503dc769-3ada-4099-a5fe-4dd03d995600
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20ea60356580ae7d5a6ac2be3336ec07314211f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250210"
---
# <a name="how-to-create-a-fact-retriever"></a><span data-ttu-id="f5aee-102">ファクト取得コンポーネントを作成する方法</span><span class="sxs-lookup"><span data-stu-id="f5aee-102">How to Create a Fact Retriever</span></span>
<span data-ttu-id="f5aee-103">ファクト取得コンポーネントは、ポリシーの実行時に、長期間のファクトのインスタンスをポリシーとしてアサートする際に使用されるコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="f5aee-103">A fact retriever is a component that is used to assert instances of long-term facts into a policy during its execution.</span></span> <span data-ttu-id="f5aee-104">実装することができます、 **IFactRetriever**インターフェイスおよびを長期間のファクトのインスタンスで実行時にこの実装を使用するポリシーのバージョンを構成します。</span><span class="sxs-lookup"><span data-stu-id="f5aee-104">You can implement the **IFactRetriever** interface and configure a policy version to use this implementation at run time to bring in the long-term fact instances.</span></span> <span data-ttu-id="f5aee-105">ポリシーのバージョンを呼び出す、 **UpdateFacts**メソッドのすべての実行サイクルで、その特定のバージョンのファクト取得コンポーネントが構成されている場合、ファクト取得コンポーネントを実装します。</span><span class="sxs-lookup"><span data-stu-id="f5aee-105">The policy version invokes the **UpdateFacts** method of the fact retriever implementation on every execution cycle, if a fact retriever is configured for that particular version.</span></span>  
  
 <span data-ttu-id="f5aee-106">必要に応じてを実装することができます、 **IFactRemover**ファクト取得コンポーネントのインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="f5aee-106">You can optionally implement the **IFactRemover** interface on a fact retriever component.</span></span> <span data-ttu-id="f5aee-107">ルール エンジン、 **UpdateFactsAfterExecution**のメソッド、 **IFactRemover**インターフェイスのポリシーが破棄されるときにします。</span><span class="sxs-lookup"><span data-stu-id="f5aee-107">The rule engine invokes the **UpdateFactsAfterExecution** method of the **IFactRemover** interface when the policy is disposed.</span></span> <span data-ttu-id="f5aee-108">これは、データベースの変更をコミットするか、ルール エンジンの作業メモリからすべてのオブジェクト インスタンスの取り消しなどの実行後の作業を実行するため、機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="f5aee-108">This provides an opportunity to you to do any post-execution work such as committing any database changes or retracting any object instances from the rule engine's working memory.</span></span>  
  
## <a name="to-specify-a-fact-retriever-for-a-policy"></a><span data-ttu-id="f5aee-109">ポリシーに対してファクト取得コンポーネントを指定するには</span><span class="sxs-lookup"><span data-stu-id="f5aee-109">To specify a fact retriever for a policy</span></span>  
 <span data-ttu-id="f5aee-110">ファクト取得コンポーネントとして、"MyAssembly" アセンブリの "Retriever" というクラスを使用するようにルール セットを構成するには、次のようなコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="f5aee-110">You could use the following code to configure the rule set to use a class named "Retriever" in the assembly named "MyAssembly" as the fact retriever.</span></span>  
  
```  
RuleEngineComponentConfiguration fr = new RuleEngineComponentConfiguration("MyAssembly", "Retriever");  
RuleSet rs = new RuleSet("ruleset");  
// associate the execution configuration with a ruleset  
RuleSetExecutionConfiguration rsCfg = rs.ExecutionConfiguration;  
rsCfg.FactRetriever = factRetriever;  
```  
  
> [!NOTE]
>  <span data-ttu-id="f5aee-111">RuleEngineComponentConfiguration コンストラクターの最初のパラメーターとして MyAssembly のような単純なアセンブリ名を指定した場合、BizTalk ルール エンジンではプライベート アセンブリと認識され、ユーザーのアプリケーション フォルダー内のアセンブリが検索されます。</span><span class="sxs-lookup"><span data-stu-id="f5aee-111">If you specify simple assembly name such as MyAssembly as the first parameter for RuleEngineComponentConfiguration constructor, the BizTalk rule engine assumes that it is a private assembly and looks for the assembly in your application folder.</span></span> <span data-ttu-id="f5aee-112">アセンブリの完全修飾名をなどを指定する場合**MyAssembly, バージョン 1.0.0.0、カルチャを = = neutral, PublicKeyToken = a310908b42c024fe**、ルール エンジンは共有アセンブリとグローバル アセンブリの検索を前提としていますアセンブリ キャッシュ (GAC)。</span><span class="sxs-lookup"><span data-stu-id="f5aee-112">If you specify fully qualified assembly name such as **MyAssembly, Version=1.0.0.0, Culture=neutral, PublicKeyToken=a310908b42c024fe**, the rule engine assumes that it is a shared assembly and looks for the assembly in the global assembly cache (GAC).</span></span> <span data-ttu-id="f5aee-113">単純、完全修飾アセンブリ名の定義を見つけることができます[http://go.microsoft.com/fwlink/?LinkId=64535](http://go.microsoft.com/fwlink/?LinkId=64535)です。</span><span class="sxs-lookup"><span data-stu-id="f5aee-113">You can find the definitions of simple and fully qualified assembly names at [http://go.microsoft.com/fwlink/?LinkId=64535](http://go.microsoft.com/fwlink/?LinkId=64535).</span></span>  
  
 <span data-ttu-id="f5aee-114">特定のデータ ソースに接続するためのアプリケーション固有のロジックを備えたファクト取得コンポーネントを設計し、そのデータをエンジンに対する長期間のファクトとしてアサートして、新しいファクトのインスタンスをエンジンに対して更新またはアサートするためのロジックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f5aee-114">You can design the fact retriever with the required application-specific logic to connect to the required data sources, assert the data as long-term facts into the engine, and specify the logic for refreshing or asserting new instances of the long-term facts into the engine.</span></span> <span data-ttu-id="f5aee-115">後続の実行サイクルでは、値が更新されるまで、最初にエンジンに対してアサートされ、キャッシュされた値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5aee-115">Until updated, the values that are initially asserted into the engine and consequently cached will be used on subsequent execution cycles.</span></span> <span data-ttu-id="f5aee-116">ファクト取得コンポーネントの実装がトークンに似ていますが、オブジェクトを返しますおよびと組み合わせて使用することができます、 **factsHandleIn**オブジェクトを既存のファクトを更新または新しいファクトをアサートするかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="f5aee-116">The fact retriever implementation returns an object that is analogous to a token and can be used along with the **factsHandleIn** object to determine whether to update existing facts or assert new facts.</span></span> <span data-ttu-id="f5aee-117">ポリシーのバージョンが最初に、そのファクト取得コンポーネントを呼び出したときに、 **factsHandleIn**オブジェクトは常に null とし、ファクト取得コンポーネントの実行後に、返されたオブジェクトの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="f5aee-117">When a policy version calls its fact retriever for the first time, the **factsHandleIn** object is always null and then takes the value of the return object after the fact retriever's execution.</span></span>  
  
 <span data-ttu-id="f5aee-118">長期間のファクトをアサートするのは、同じルール エンジンのインスタンスに対して 1 回だけでかまいません。</span><span class="sxs-lookup"><span data-stu-id="f5aee-118">Note that for the same rule engine instance, a long-term fact only needs to be asserted once.</span></span> <span data-ttu-id="f5aee-119">たとえば、使用、**ルールの呼び出し**ポリシー インスタンスのオーケストレーションの図形が内部キャッシュに移動します。</span><span class="sxs-lookup"><span data-stu-id="f5aee-119">For example, when you use the **Call Rules** shape in an orchestration, the policy instance is moved into an internal cache.</span></span> <span data-ttu-id="f5aee-120">このとき、短期間のファクトはすべて取り消され、長期間のファクトが維持されます。</span><span class="sxs-lookup"><span data-stu-id="f5aee-120">At this time, all short-term facts are retracted and long-term facts are kept.</span></span> <span data-ttu-id="f5aee-121">同じオーケストレーション インスタンスまたは同じホストの別のオーケストレーション インスタンスによって同じポリシーが再び呼び出された場合、このポリシー インスタンスがキャッシュから取得され再利用されます。</span><span class="sxs-lookup"><span data-stu-id="f5aee-121">If the same policy is called again, either by the same orchestration instance or by a different orchestration instance in the same host, this policy instance is fetched from the cache and reused.</span></span> <span data-ttu-id="f5aee-122">バッチ処理のシナリオによっては、同じポリシーのインスタンスが複数作成される場合があります。</span><span class="sxs-lookup"><span data-stu-id="f5aee-122">In some batch processing scenarios, several policy instances of the same policy could be created.</span></span> <span data-ttu-id="f5aee-123">新しいポリシー インスタンスが作成された場合は、適切な長期間のファクトがアサートされるように配慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5aee-123">If a new policy instance is created, you must ensure that the correct long-term facts are asserted.</span></span>  
  
 <span data-ttu-id="f5aee-124">また、次のような処理を実現するカスタム コードを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f5aee-124">Additionally, you would need to write custom code to implement the following strategies:</span></span>  
  
-   <span data-ttu-id="f5aee-125">長期間のファクトが更新されたタイミングを確認する。</span><span class="sxs-lookup"><span data-stu-id="f5aee-125">Know when to update the long-term facts</span></span>  
  
-   <span data-ttu-id="f5aee-126">どのルール エンジンのインスタンスが、どの長期間のファクトによって使用されたかを追跡する。</span><span class="sxs-lookup"><span data-stu-id="f5aee-126">Keep track of which rule engine instance uses which long-term facts</span></span>  
  
 <span data-ttu-id="f5aee-127">次のコード例は、ファクト取得コンポーネントの実装例です。ファクト取得コンポーネントを MyPolicy に関連付け、各種のバインディング方法を使って MyTableInstance を長期間のファクトとしてアサートします。</span><span class="sxs-lookup"><span data-stu-id="f5aee-127">The following sample code shows different fact retriever implementations, which are associated with MyPolicy to assert MyTableInstance as a long-term fact, using different binding types.</span></span>  
  
## <a name="datatable-binding"></a><span data-ttu-id="f5aee-128">DataTable バインド</span><span class="sxs-lookup"><span data-stu-id="f5aee-128">DataTable binding</span></span>  
  
```  
using System;  
using System.Xml;  
using System.Collections;  
using Microsoft.RuleEngine;  
using System.IO;  
using System.Data;  
using System.Data.SqlClient;  
namespace MyBizTalkApplication.FactRetriever  
{  
   public class myFactRetriever:IFactRetriever  
   {  
      public object UpdateFacts(RuleSetInfo rulesetInfo, Microsoft.RuleEngine.RuleEngine engine, object factsHandleIn)  
      {  
         object factsHandleOut;  
         if (factsHandleIn == null)   
  
         {  
            SqlDataAdapter dAdapt = new SqlDataAdapter();  
            dAdapt.TableMappings.Add("Table", "CustInfo");  
            SqlConnection conn = new SqlConnection("Initial Catalog=Northwind;Data Source=(local);Integrated Security=SSPI;");  
            conn.Open();  
            SqlCommand myCommand = new SqlCommand("SELECT * FROM CustInfo", conn);  
            myCommand.CommandType = CommandType.Text;  
            dAdapt.SelectCommand = myCommand;  
            DataSet ds = new DataSet("Northwind");  
            dAdapt.Fill(ds);  
            TypedDataTable tdt = new TypedDataTable(ds.Tables["CustInfo"]);  
            engine.Assert(tdt);  
            factsHandleOut = tdt;  
         }  
  
         else  
            factsHandleOut = factsHandleIn;  
         return factsHandleOut;  
      }  
   }  
}  
```  
  
## <a name="datarow-binding"></a><span data-ttu-id="f5aee-129">DataRow バインド</span><span class="sxs-lookup"><span data-stu-id="f5aee-129">DataRow binding</span></span>  
  
```  
using System;  
using System.Xml;  
using System.Collections;  
using Microsoft.RuleEngine;  
using System.IO;  
using System.Data;  
using System.Data.SqlClient;  
namespace MyBizTalkApplication.FactRetriever  
{  
   public class myFactRetriever:IFactRetriever  
   {  
  
      public object UpdateFacts(RuleSetInfo rulesetInfo, Microsoft.RuleEngine.RuleEngine engine, object factsHandleIn)  
      {  
         object factsHandleOut;  
         if (factsHandleIn == null)   
  
         {  
            SqlDataAdapter dAdapt = new SqlDataAdapter();  
            dAdapt.TableMappings.Add("Table", "CustInfo");  
            SqlConnection conn = new SqlConnection("Initial Catalog=Northwind;Data Source=(local);Integrated Security=SSPI;");  
            conn.Open();  
            SqlCommand myCommand = new SqlCommand("SELECT * FROM CustInfo", conn);  
            myCommand.CommandType = CommandType.Text;  
            dAdapt.SelectCommand = myCommand;  
            DataSet ds = new DataSet("Northwind");  
            dAdapt.Fill(ds);  
            TypedDataTable tdt = new TypedDataTable(ds.Tables["CustInfo"]);  
  
            // binding to the first row of CustInfo table  
            TypedDataRow tdr = new TypedDataRow(ds.Tables["CustInfo"].Rows[0],tdt);  
            engine.Assert(tdr);  
            factsHandleOut = tdr;     
         }  
         else  
            factsHandleOut = factsHandleIn;  
         return factsHandleOut;  
      }  
   }   
}  
```  
  
 <span data-ttu-id="f5aee-130">次のコード例は、ファクト取得コンポーネントを実装することにより、.NET および XML のファクトをアサートする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f5aee-130">The following sample code demonstrates how to assert .NET and XML facts in a fact retriever implementation.</span></span>  
  
```  
using System;  
using System.Xml;  
using System.Collections;  
using Microsoft.RuleEngine;  
using System.IO;  
using System.Data;  
using System.Data.SqlClient;  
namespace MyBizTalkApplication.FactRetriever  
{  
   public class myFactRetriever:IFactRetriever  
   {  
      public object UpdateFacts(RuleSetInfo rulesetInfo, Microsoft.RuleEngine.RuleEngine engine, object factsHandleIn)  
      {  
         object factsHandleOut;  
         if (factsHandleIn == null)   
         {  
            //create .NET object instances  
            bookInstance = new Book();  
            magazineInstance = new Magazine();              
  
            //create an instance of the XML object  
            XmlDocument xd = new XmlDocument();  
  
            //load the document  
            xd.Load(@"..\myXMLInstance.xml");  
  
            //create and instantiate an instance of TXD  
            TypedXmlDocument doc = new TypedXmlDocument("mySchema",xd1);  
  
            engine.Assert(bookInstance);  
            engine.Assert(magazineInstance);  
            engine.Assert(doc);  
            factsHandleOut = doc;  
         }  
         else  
            factsHandleOut = factsHandleIn;  
         return factsHandleOut;  
      }  
   }  
}  
```  
  
## <a name="dataconnection-binding"></a><span data-ttu-id="f5aee-131">DataConnection バインド</span><span class="sxs-lookup"><span data-stu-id="f5aee-131">DataConnection Binding</span></span>  
  
```  
using System;  
using System.Xml;  
using System.Collections;  
using Microsoft.RuleEngine;  
using System.IO;  
using System.Data;  
using System.Data.SqlClient;  
namespace MyBizTalkApplication.FactRetriever  
{  
   public class myFactRetriever:IFactRetriever  
   {  
      public object UpdateFacts(RuleSetInfo rulesetInfo, Microsoft.RuleEngine.RuleEngine engine, object factsHandleIn)  
      {  
         object factsHandleOut;  
  
         {   
            string strCmd = "Initial Catalog=Northwind;Data Source=(local);Integrated Security=SSPI;";  
            SqlConnection conn = new SqlConnection(strCmd);  
            DataConnection dc = new DataConnection("Northwind", "CustInfo", conn);  
  
            engine.Assert(dc);  
            factsHandleOut = dc;           
         }  
         return factsHandleOut;  
      }  
   }  
}  
```  
  
 <span data-ttu-id="f5aee-132">なお**DataConnection**s は常に再アサートされます、上記のコード サンプルで示すように、ファクト取得コンポーネントから提供されています。</span><span class="sxs-lookup"><span data-stu-id="f5aee-132">Note that **DataConnection**s should always be reasserted, when provided from a fact retriever, as shown in the preceding code sample.</span></span> <span data-ttu-id="f5aee-133">エンジンのインスタンスを使用して、 **DataConnection** 、ルールの条件に基づいて、データベースを照会して、クエリによって返された行がように、エンジンの作業メモリにアサート**TypedDataRow**s。</span><span class="sxs-lookup"><span data-stu-id="f5aee-133">The engine instance uses the **DataConnection** to query the database based on the rule conditions, and any rows returned by the query would be asserted into the engine's working memory as **TypedDataRow**s.</span></span> <span data-ttu-id="f5aee-134">DataConnection を再アサートにより、エンジンの前回の実行からの行がメモリからクリアされます。</span><span class="sxs-lookup"><span data-stu-id="f5aee-134">Reasserting the DataConnection ensures that rows from a previous execution of the engine are cleared from memory.</span></span>  
  
 <span data-ttu-id="f5aee-135">実際には、アサートするほとんどの利点は、 **DataConnection**ファクトを通じて取得機能する点が異なりますが、データ ソースを外部化する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="f5aee-135">In fact, there is little advantage to asserting a **DataConnection** through a fact retriever except that it provides a way to externalize the data source.</span></span>