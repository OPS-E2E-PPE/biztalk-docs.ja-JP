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
# <a name="how-to-create-a-fact-retriever"></a>ファクト取得コンポーネントを作成する方法
ファクト取得コンポーネントは、実行中にポリシーに、長期間のファクトのインスタンスをアサートするために使用するコンポーネントです。 実装することができます、 **IFactRetriever**インターフェイスし、長期間のファクトのインスタンスで実行時にこの実装を使用するポリシーのバージョンを構成します。 ポリシーのバージョンを呼び出す、 **UpdateFacts**ファクト取得コンポーネントが特定のバージョン用に構成されている場合、すべての実行サイクルでファクト取得コンポーネントの実装のメソッド。  
  
 必要に応じて実装することができます、 **IFactRemover**ファクト取得コンポーネントのインターフェイス。 ルール エンジンは、 **UpdateFactsAfterExecution**のメソッド、 **IFactRemover**ポリシーが破棄されるときのインターフェイスします。 これをデータベースの変更をコミットするか、ルール エンジンの作業メモリから任意のオブジェクト インスタンスの取り消しなどの実行後の作業を行うことに、機会を提供します。  
  
## <a name="to-specify-a-fact-retriever-for-a-policy"></a>ポリシーのファクト取得コンポーネントを指定するには  
 ファクト取得コンポーネントとして、"myassembly"アセンブリ内の"Retriever"をという名前のクラスを使用するのに設定のルールを構成するのに次のコードを使用できます。  
  
```  
RuleEngineComponentConfiguration fr = new RuleEngineComponentConfiguration("MyAssembly", "Retriever");  
RuleSet rs = new RuleSet("ruleset");  
// associate the execution configuration with a ruleset  
RuleSetExecutionConfiguration rsCfg = rs.ExecutionConfiguration;  
rsCfg.FactRetriever = factRetriever;  
```  
  
> [!NOTE]
>  RuleEngineComponentConfiguration コンス トラクターの最初のパラメーターとして MyAssembly などの単純なアセンブリ名を指定した場合、BizTalk ルール エンジンではプライベート アセンブリとアプリケーションのフォルダー内のアセンブリが検索されます。 完全修飾アセンブリ名を指定する場合**MyAssembly, Version 1.0.0.0、カルチャを = = neutral, PublicKeyToken = a310908b42c024fe**、ルール エンジンでは、共有アセンブリとグローバル アセンブリが検索されますアセンブリ キャッシュ (GAC)。 シンプルで完全修飾アセンブリ名の定義を検索する[ http://go.microsoft.com/fwlink/?LinkId=64535](http://go.microsoft.com/fwlink/?LinkId=64535)します。  
  
 必要なデータ ソースへの接続、データを長期間のファクトとしてエンジンにアサートし、ロジックを更新またはアサートに長期間のファクトの新しいインスタンスを指定する必要なアプリケーション固有のロジックで、ファクト取得コンポーネントをデザインすることができます、エンジン。 、更新されるまでは、後続の実行サイクルでは最初に、エンジンにアサートし、キャッシュされた値が使用されます。 ファクト取得コンポーネントの実装は、トークンに似ていますオブジェクトを返しますおよびと組み合わせて使用することができます、 **factsHandleIn**オブジェクトを既存のファクトを更新または新しいファクトをアサートするかどうかを判断します。 ポリシーのバージョンは、最初に、そのファクト取得コンポーネントを呼び出すときに、 **factsHandleIn**オブジェクトは常に null とし、ファクト取得コンポーネントの実行後に、返されたオブジェクトの値を取得します。  
  
 同じルール エンジンのインスタンスの長期間のファクトのみ必要があることをアサートする 1 回に注意してください。 たとえば、使用、**ルールの呼び出し**ポリシー インスタンス、オーケストレーションの図形が内部キャッシュに移動します。 この時点では、すべての短期間のファクトは取り消され、長期間のファクトが保持されます。 同じポリシーが呼び出された場合、もう一度同じオーケストレーション インスタンスまたは別のオーケストレーション インスタンスを同じホスト内のいずれかこのポリシー インスタンスはキャッシュからフェッチし、再利用します。 いくつかのバッチ処理のシナリオで、同じポリシーのいくつかのポリシー インスタンスを作成する。 新しいポリシー インスタンスを作成した場合は、適切な長期間のファクトをアサートすることを確認する必要があります。  
  
 さらに、次の戦略を実装するカスタム コードを記述する必要があります。  
  
- 長期間のファクトを更新する時期を把握します。  
  
- どのルール エンジンのインスタンスが長期間のファクトの使用の追跡  
  
  次のサンプル コードは、複数のファクト取得コンポーネントの実装は、MyTableInstance を各種のバインディングを使用して、長期間のファクトとしてアサートする MyPolicy に関連付けられたを示します。  
  
## <a name="datatable-binding"></a>DataTable バインド  
  
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
  
## <a name="datarow-binding"></a>DataRow バインド  
  
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
  
 次のサンプル コードでは、ファクト取得コンポーネントの実装での .NET および XML ファクトをアサートする方法を示します。  
  
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
  
## <a name="dataconnection-binding"></a>DataConnection バインド  
  
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
  
 なお**DataConnection**s は、上記のコード サンプルで示すように、ファクト取得コンポーネントから提供されている場合は、アサート常にする必要があります。 エンジンのインスタンスを使用して、 **DataConnection** 、ルールの条件に基づいて、データベース クエリを実行して、クエリによって返される行がように、エンジンの作業メモリにアサート**TypedDataRow**秒。 DataConnection を再により、エンジンの前回の実行からの行がメモリからクリアされます。  
  
 実際には、アサートするほとんどのメリットがある、 **DataConnection**ファクトを使用する点の取得元はデータ ソースを外部化する方法を提供します。