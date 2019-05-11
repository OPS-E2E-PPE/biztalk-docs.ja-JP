---
title: ビジネス ルール エンジンにデータベース ファクトを渡す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62285bbe-ee64-4c26-b48e-55f666dc1304
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8e3b389b3b606089005fa089604b3ba81452fdf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395021"
---
# <a name="passing-database-facts-to-the-business-rule-engine"></a><span data-ttu-id="5807f-102">ビジネス ルール エンジンへのデータベース ファクトの引き渡し</span><span class="sxs-lookup"><span data-stu-id="5807f-102">Passing Database Facts to the Business Rule Engine</span></span>
<span data-ttu-id="5807f-103">DataConnection と TypedDataTable のオブジェクトをファクトとしてを必要とするポリシーをテストするビジネス ルール作成ツールを使用する場合、DataConnection と TypedDataTable オブジェクトが自動的に作成され、ビジネス ルール エンジンの作業メモリにアサートします。</span><span class="sxs-lookup"><span data-stu-id="5807f-103">When you use the Business Rule Composer tool to test a policy that requires a DataConnection/TypedDataTable object as a fact, a DataConnection/TypedDataTable object is automatically created for you and asserted into the Business Rule Engine's working memory.</span></span> <span data-ttu-id="5807f-104">さらに、すべてのデータベース更新ポリシーによって自動的にコミットされます。</span><span class="sxs-lookup"><span data-stu-id="5807f-104">Additionally, any database updates by the policy are committed automatically.</span></span>  
  
 <span data-ttu-id="5807f-105">これに対し、オーケストレーションからポリシーを呼び出すを使用してルールの呼び出し図形またはプログラムでは、DataConnection と TypedDataTable オブジェクトは作成されませんがされ、データベースの更新はコミットされません自動的にします。</span><span class="sxs-lookup"><span data-stu-id="5807f-105">In contrast, when you invoke the policy from an orchestration, either by using the Call Rules shape or programmatically, the DataConnection/TypedDataTable object is not created for you and the database updates are not committed automatically.</span></span> <span data-ttu-id="5807f-106">ここでは、DataConnection と TypedDataTable オブジェクトの作成をファクトとしてルール エンジンに渡す、およびプログラムで、次のメソッドのいずれかを使用して、データベースの変更をコミットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5807f-106">In this case, you should create a DataConnection/TypedDataTable object, pass it as a fact to the rule engine, and commit the database changes programmatically by using one of the following methods.</span></span>  
  
## <a name="passing-a-dataconnection-object-from-an-orchestration"></a><span data-ttu-id="5807f-107">オーケストレーションからの DataConnection オブジェクトの引き渡し</span><span class="sxs-lookup"><span data-stu-id="5807f-107">Passing a DataConnection Object from an Orchestration</span></span>  
 <span data-ttu-id="5807f-108">次のサンプル コードでは、オーケストレーションで DataConnection オブジェクトを作成、DataConnection オブジェクトをパラメーターとして渡すルールの呼び出し図形の構成し、ポリシーの実行後にすべてのデータベース更新をコミットする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5807f-108">The following sample code demonstrates how to create a DataConnection object in the orchestration, configure the Call Rules shape to pass the DataConnection object as a parameter, and commit any database updates after the policy is executed.</span></span>  
  
1.  <span data-ttu-id="5807f-109">オーケストレーション デザイナーでオーケストレーションを開き、[オーケストレーションの種類] タブを使用して、次の変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="5807f-109">Create the following variables using the Orchestration View tab with the orchestration open in the Orchestration Designer.</span></span>  
  
    ```  
    DataCon of type Microsoft.RuleEngine.DataConnection   
    SqlCon of type System.Data.SqlClient.SqlConnection   
    SqlTran of type System.Data.SqlClient.SqlTransaction   
    ```  
  
2.  <span data-ttu-id="5807f-110">ルールの呼び出し図形の前に、式図形では、DataConnection オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="5807f-110">In an Expression shape before the Call Rules shape, create a DataConnection object.</span></span> <span data-ttu-id="5807f-111">次のコード例では、DataConnection オブジェクトを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5807f-111">The following code example demonstrates how to create a DataConnection object.</span></span>  
  
    ```  
    SqlCon.ConnectionString = "Data Source=(local);Initial Catalog=Test;Integrated Security=SSPI";   
    SqlCon.Open();   
    SqlTran = SqlCon.BeginTransaction();   
    DataCon = new Microsoft.RuleEngine.DataConnection("test", "FlagTable", SqlCon, SqlTran);    
    ```  
  
3.  <span data-ttu-id="5807f-112">DataCon 変数をパラメーターとして渡すルールの呼び出し図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="5807f-112">Configure the Call Rules shape to pass the DataCon variable as a parameter.</span></span> <span data-ttu-id="5807f-113">詳細については、次を参照してください。[ルールの呼び出し図形の使用方法](../core/how-to-use-the-call-rules-shape.md)します。</span><span class="sxs-lookup"><span data-stu-id="5807f-113">For more information, see [How to Use the Call Rules Shape](../core/how-to-use-the-call-rules-shape.md).</span></span>  
  
4.  <span data-ttu-id="5807f-114">ルールの呼び出し図形の後に、式図形では、ポリシーによって、データベースの変更をコミットします。</span><span class="sxs-lookup"><span data-stu-id="5807f-114">In an Expression shape after the Call Rules shape, commit the database changes made by the policy.</span></span> <span data-ttu-id="5807f-115">次のコード例では、ポリシーによるデータベース変更をコミットする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5807f-115">The following code example demonstrates how to commit the database changes made by the policy.</span></span>  
  
    ```  
    DataCon.Update();   
    SqlTran.Commit();  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="5807f-116">使用する必要がある、 [SqlTransaction](http://msdn.microsoft.com/library/system.data.sqlclient.sqltransaction.aspx)オブジェクトのみ、ポリシー、データベースを更新します。</span><span class="sxs-lookup"><span data-stu-id="5807f-116">You need to use a [SqlTransaction](http://msdn.microsoft.com/library/system.data.sqlclient.sqltransaction.aspx) object only if the policy updates the database.</span></span>  
  
## <a name="passing-a-dataconnection-object-from-a-fact-retriever"></a><span data-ttu-id="5807f-117">ファクト取得コンポーネントから DataConnection オブジェクトの引き渡し</span><span class="sxs-lookup"><span data-stu-id="5807f-117">Passing a DataConnection Object from a Fact Retriever</span></span>  
 <span data-ttu-id="5807f-118">次に、ファクト取得コンポーネントから DataConnection オブジェクトを通過するために実装する必要がある一般的な手順を示します。</span><span class="sxs-lookup"><span data-stu-id="5807f-118">Here are the typical steps you need to implement to pass a DataConnection object from a fact retriever component.</span></span>  
  
1.  <span data-ttu-id="5807f-119">作成し、DataConnection オブジェクトをルール エンジンの作業メモリにアサートするファクト取得コンポーネントを作成します。</span><span class="sxs-lookup"><span data-stu-id="5807f-119">Create a fact retriever component that creates and asserts a DataConnection object into the rule engine's working memory.</span></span> <span data-ttu-id="5807f-120">ファクト取得コンポーネントを作成する方法の詳細については、次を参照してください。[ファクト取得コンポーネントを作成する方法](../core/how-to-create-a-fact-retriever.md)します。</span><span class="sxs-lookup"><span data-stu-id="5807f-120">For more information about how to create a fact retriever component, see [How to Create a Fact Retriever](../core/how-to-create-a-fact-retriever.md).</span></span>  
  
2.  <span data-ttu-id="5807f-121">実装、 [IFactRemover](http://msdn.microsoft.com/library/Microsoft.RuleEngine.IFactRemover.aspx)ファクト取得コンポーネントのインターフェイスし、データベースの変更をコミット、 [UpdateFactsAfterExecution](http://msdn.microsoft.com/library/microsoft.ruleengine.ifactremover.updatefactsafterexecution.aspx)メソッド。</span><span class="sxs-lookup"><span data-stu-id="5807f-121">Implement the [IFactRemover](http://msdn.microsoft.com/library/Microsoft.RuleEngine.IFactRemover.aspx) interface on fact retriever component, and commit the database changes from the [UpdateFactsAfterExecution](http://msdn.microsoft.com/library/microsoft.ruleengine.ifactremover.updatefactsafterexecution.aspx) method.</span></span> <span data-ttu-id="5807f-122">このメソッドは、ポリシーの実行が終了した後に、ルール エンジンによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5807f-122">This method is called by the rule engine after it is done with executing the policy.</span></span>  
  
3.  <span data-ttu-id="5807f-123">ビジネス ルール作成ツールを使用して、ファクト取得コンポーネントを使用するポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="5807f-123">Configure the policy to use the fact retriever component by using the Business Rule Composer tool.</span></span> <span data-ttu-id="5807f-124">詳細については、次を参照してください。[ポリシーのファクト取得コンポーネントを構成する方法](../core/how-to-configure-a-fact-retriever-for-a-policy.md)します。</span><span class="sxs-lookup"><span data-stu-id="5807f-124">For more information, see [How to Configure a Fact Retriever for a Policy](../core/how-to-configure-a-fact-retriever-for-a-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5807f-125">参照</span><span class="sxs-lookup"><span data-stu-id="5807f-125">See Also</span></span>  
 <span data-ttu-id="5807f-126">[ビジネス ルール エンジンでのデータ アクセス](../core/data-access-in-the-business-rule-engine.md) </span><span class="sxs-lookup"><span data-stu-id="5807f-126">[Data Access in the Business Rule Engine](../core/data-access-in-the-business-rule-engine.md) </span></span>  
 <span data-ttu-id="5807f-127">[ファクト取得コンポーネントを作成する方法](../core/how-to-create-a-fact-retriever.md) </span><span class="sxs-lookup"><span data-stu-id="5807f-127">[How to Create a Fact Retriever](../core/how-to-create-a-fact-retriever.md) </span></span>  
 [<span data-ttu-id="5807f-128">ポリシーのファクト取得コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="5807f-128">How to Configure a Fact Retriever for a Policy</span></span>](../core/how-to-configure-a-fact-retriever-for-a-policy.md)