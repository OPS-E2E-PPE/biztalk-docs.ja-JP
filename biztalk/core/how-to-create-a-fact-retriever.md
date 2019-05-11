---
title: ファクト取得コンポーネントを作成する方法 |Microsoft Docs
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
ms.openlocfilehash: 1910d143aaac50d7690c4338c053873f70d2db38
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340052"
---
# <a name="how-to-create-a-fact-retriever"></a><span data-ttu-id="e788a-102">ファクト取得コンポーネントを作成する方法</span><span class="sxs-lookup"><span data-stu-id="e788a-102">How to Create a Fact Retriever</span></span>
<span data-ttu-id="e788a-103">ファクト取得コンポーネントは、実行中にポリシーに、長期間のファクトのインスタンスをアサートするために使用するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="e788a-103">A fact retriever is a component that is used to assert instances of long-term facts into a policy during its execution.</span></span> <span data-ttu-id="e788a-104">実装することができます、 **IFactRetriever**インターフェイスし、長期間のファクトのインスタンスで実行時にこの実装を使用するポリシーのバージョンを構成します。</span><span class="sxs-lookup"><span data-stu-id="e788a-104">You can implement the **IFactRetriever** interface and configure a policy version to use this implementation at run time to bring in the long-term fact instances.</span></span> <span data-ttu-id="e788a-105">ポリシーのバージョンを呼び出す、 **UpdateFacts**ファクト取得コンポーネントが特定のバージョン用に構成されている場合、すべての実行サイクルでファクト取得コンポーネントの実装のメソッド。</span><span class="sxs-lookup"><span data-stu-id="e788a-105">The policy version invokes the **UpdateFacts** method of the fact retriever implementation on every execution cycle, if a fact retriever is configured for that particular version.</span></span>  
  
 <span data-ttu-id="e788a-106">必要に応じて実装することができます、 **IFactRemover**ファクト取得コンポーネントのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="e788a-106">You can optionally implement the **IFactRemover** interface on a fact retriever component.</span></span> <span data-ttu-id="e788a-107">ルール エンジンは、 **UpdateFactsAfterExecution**のメソッド、 **IFactRemover**ポリシーが破棄されるときのインターフェイスします。</span><span class="sxs-lookup"><span data-stu-id="e788a-107">The rule engine invokes the **UpdateFactsAfterExecution** method of the **IFactRemover** interface when the policy is disposed.</span></span> <span data-ttu-id="e788a-108">これをデータベースの変更をコミットするか、ルール エンジンの作業メモリから任意のオブジェクト インスタンスの取り消しなどの実行後の作業を行うことに、機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="e788a-108">This provides an opportunity to you to do any post-execution work such as committing any database changes or retracting any object instances from the rule engine's working memory.</span></span>  
  
## <a name="to-specify-a-fact-retriever-for-a-policy"></a><span data-ttu-id="e788a-109">ポリシーのファクト取得コンポーネントを指定するには</span><span class="sxs-lookup"><span data-stu-id="e788a-109">To specify a fact retriever for a policy</span></span>  
 <span data-ttu-id="e788a-110">ファクト取得コンポーネントとして、"myassembly"アセンブリ内の"Retriever"をという名前のクラスを使用するのに設定のルールを構成するのに次のコードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e788a-110">You could use the following code to configure the rule set to use a class named "Retriever" in the assembly named "MyAssembly" as the fact retriever.</span></span>  
  
```  
RuleEngineComponentConfiguration fr = new RuleEngineComponentConfiguration("MyAssembly", "Retriever");  
RuleSet rs = new RuleSet("ruleset");  
// associate the execution configuration with a ruleset  
RuleSetExecutionConfiguration rsCfg = rs.ExecutionConfiguration;  
rsCfg.FactRetriever = factRetriever;  
```  
  
> [!NOTE]
>  <span data-ttu-id="e788a-111">RuleEngineComponentConfiguration コンス トラクターの最初のパラメーターとして MyAssembly などの単純なアセンブリ名を指定した場合、BizTalk ルール エンジンではプライベート アセンブリとアプリケーションのフォルダー内のアセンブリが検索されます。</span><span class="sxs-lookup"><span data-stu-id="e788a-111">If you specify simple assembly name such as MyAssembly as the first parameter for RuleEngineComponentConfiguration constructor, the BizTalk rule engine assumes that it is a private assembly and looks for the assembly in your application folder.</span></span> <span data-ttu-id="e788a-112">完全修飾アセンブリ名を指定する場合**MyAssembly, Version 1.0.0.0、カルチャを = = neutral, PublicKeyToken = a310908b42c024fe**、ルール エンジンでは、共有アセンブリとグローバル アセンブリが検索されますアセンブリ キャッシュ (GAC)。</span><span class="sxs-lookup"><span data-stu-id="e788a-112">If you specify fully qualified assembly name such as **MyAssembly, Version=1.0.0.0, Culture=neutral, PublicKeyToken=a310908b42c024fe**, the rule engine assumes that it is a shared assembly and looks for the assembly in the global assembly cache (GAC).</span></span> <span data-ttu-id="e788a-113">シンプルで完全修飾アセンブリ名の定義を検索する[ http://go.microsoft.com/fwlink/?LinkId=64535](http://go.microsoft.com/fwlink/?LinkId=64535)します。</span><span class="sxs-lookup"><span data-stu-id="e788a-113">You can find the definitions of simple and fully qualified assembly names at [http://go.microsoft.com/fwlink/?LinkId=64535](http://go.microsoft.com/fwlink/?LinkId=64535).</span></span>  
  
 <span data-ttu-id="e788a-114">必要なデータ ソースへの接続、データを長期間のファクトとしてエンジンにアサートし、ロジックを更新またはアサートに長期間のファクトの新しいインスタンスを指定する必要なアプリケーション固有のロジックで、ファクト取得コンポーネントをデザインすることができます、エンジン。</span><span class="sxs-lookup"><span data-stu-id="e788a-114">You can design the fact retriever with the required application-specific logic to connect to the required data sources, assert the data as long-term facts into the engine, and specify the logic for refreshing or asserting new instances of the long-term facts into the engine.</span></span> <span data-ttu-id="e788a-115">、更新されるまでは、後続の実行サイクルでは最初に、エンジンにアサートし、キャッシュされた値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e788a-115">Until updated, the values that are initially asserted into the engine and consequently cached will be used on subsequent execution cycles.</span></span> <span data-ttu-id="e788a-116">ファクト取得コンポーネントの実装は、トークンに似ていますオブジェクトを返しますおよびと組み合わせて使用することができます、 **factsHandleIn**オブジェクトを既存のファクトを更新または新しいファクトをアサートするかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="e788a-116">The fact retriever implementation returns an object that is analogous to a token and can be used along with the **factsHandleIn** object to determine whether to update existing facts or assert new facts.</span></span> <span data-ttu-id="e788a-117">ポリシーのバージョンは、最初に、そのファクト取得コンポーネントを呼び出すときに、 **factsHandleIn**オブジェクトは常に null とし、ファクト取得コンポーネントの実行後に、返されたオブジェクトの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e788a-117">When a policy version calls its fact retriever for the first time, the **factsHandleIn** object is always null and then takes the value of the return object after the fact retriever's execution.</span></span>  
  
 <span data-ttu-id="e788a-118">同じルール エンジンのインスタンスの長期間のファクトのみ必要があることをアサートする 1 回に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e788a-118">Note that for the same rule engine instance, a long-term fact only needs to be asserted once.</span></span> <span data-ttu-id="e788a-119">たとえば、使用、**ルールの呼び出し**ポリシー インスタンス、オーケストレーションの図形が内部キャッシュに移動します。</span><span class="sxs-lookup"><span data-stu-id="e788a-119">For example, when you use the **Call Rules** shape in an orchestration, the policy instance is moved into an internal cache.</span></span> <span data-ttu-id="e788a-120">この時点では、すべての短期間のファクトは取り消され、長期間のファクトが保持されます。</span><span class="sxs-lookup"><span data-stu-id="e788a-120">At this time, all short-term facts are retracted and long-term facts are kept.</span></span> <span data-ttu-id="e788a-121">同じポリシーが呼び出された場合、もう一度同じオーケストレーション インスタンスまたは別のオーケストレーション インスタンスを同じホスト内のいずれかこのポリシー インスタンスはキャッシュからフェッチし、再利用します。</span><span class="sxs-lookup"><span data-stu-id="e788a-121">If the same policy is called again, either by the same orchestration instance or by a different orchestration instance in the same host, this policy instance is fetched from the cache and reused.</span></span> <span data-ttu-id="e788a-122">いくつかのバッチ処理のシナリオで、同じポリシーのいくつかのポリシー インスタンスを作成する。</span><span class="sxs-lookup"><span data-stu-id="e788a-122">In some batch processing scenarios, several policy instances of the same policy could be created.</span></span> <span data-ttu-id="e788a-123">新しいポリシー インスタンスを作成した場合は、適切な長期間のファクトをアサートすることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e788a-123">If a new policy instance is created, you must ensure that the correct long-term facts are asserted.</span></span>  
  
 <span data-ttu-id="e788a-124">さらに、次の戦略を実装するカスタム コードを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e788a-124">Additionally, you would need to write custom code to implement the following strategies:</span></span>  
  
- <span data-ttu-id="e788a-125">長期間のファクトを更新する時期を把握します。</span><span class="sxs-lookup"><span data-stu-id="e788a-125">Know when to update the long-term facts</span></span>  
  
- <span data-ttu-id="e788a-126">どのルール エンジンのインスタンスが長期間のファクトの使用の追跡</span><span class="sxs-lookup"><span data-stu-id="e788a-126">Keep track of which rule engine instance uses which long-term facts</span></span>  
  
  <span data-ttu-id="e788a-127">次のサンプル コードは、複数のファクト取得コンポーネントの実装は、MyTableInstance を各種のバインディングを使用して、長期間のファクトとしてアサートする MyPolicy に関連付けられたを示します。</span><span class="sxs-lookup"><span data-stu-id="e788a-127">The following sample code shows different fact retriever implementations, which are associated with MyPolicy to assert MyTableInstance as a long-term fact, using different binding types.</span></span>  
  
## <a name="datatable-binding"></a><span data-ttu-id="e788a-128">DataTable バインド</span><span class="sxs-lookup"><span data-stu-id="e788a-128">DataTable binding</span></span>  
  
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
  
## <a name="datarow-binding"></a><span data-ttu-id="e788a-129">DataRow バインド</span><span class="sxs-lookup"><span data-stu-id="e788a-129">DataRow binding</span></span>  
  
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
  
 <span data-ttu-id="e788a-130">次のサンプル コードでは、ファクト取得コンポーネントの実装での .NET および XML ファクトをアサートする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e788a-130">The following sample code demonstrates how to assert .NET and XML facts in a fact retriever implementation.</span></span>  
  
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
  
## <a name="dataconnection-binding"></a><span data-ttu-id="e788a-131">DataConnection バインド</span><span class="sxs-lookup"><span data-stu-id="e788a-131">DataConnection Binding</span></span>  
  
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
  
 <span data-ttu-id="e788a-132">なお**DataConnection**s は、上記のコード サンプルで示すように、ファクト取得コンポーネントから提供されている場合は、アサート常にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e788a-132">Note that **DataConnection**s should always be reasserted, when provided from a fact retriever, as shown in the preceding code sample.</span></span> <span data-ttu-id="e788a-133">エンジンのインスタンスを使用して、 **DataConnection** 、ルールの条件に基づいて、データベース クエリを実行して、クエリによって返される行がように、エンジンの作業メモリにアサート**TypedDataRow**秒。</span><span class="sxs-lookup"><span data-stu-id="e788a-133">The engine instance uses the **DataConnection** to query the database based on the rule conditions, and any rows returned by the query would be asserted into the engine's working memory as **TypedDataRow**s.</span></span> <span data-ttu-id="e788a-134">DataConnection を再により、エンジンの前回の実行からの行がメモリからクリアされます。</span><span class="sxs-lookup"><span data-stu-id="e788a-134">Reasserting the DataConnection ensures that rows from a previous execution of the engine are cleared from memory.</span></span>  
  
 <span data-ttu-id="e788a-135">実際には、アサートするほとんどのメリットがある、 **DataConnection**ファクトを使用する点の取得元はデータ ソースを外部化する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="e788a-135">In fact, there is little advantage to asserting a **DataConnection** through a fact retriever except that it provides a way to externalize the data source.</span></span>