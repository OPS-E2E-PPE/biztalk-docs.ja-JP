---
title: トランザクションのサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DataConnection object
- Business Rules Framework, code samples
- Business Rules Framework, programming
ms.assetid: 84faac2f-6229-4692-9d1a-bf62d87d69bb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79f078800926852be5dcd24679157b000dab1c19
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279702"
---
# <a name="transaction-support"></a><span data-ttu-id="68b5c-102">トランザクションのサポート</span><span class="sxs-lookup"><span data-stu-id="68b5c-102">Transaction Support</span></span>
<span data-ttu-id="68b5c-103">ルール エンジンでは、トランザクションを一般にサポートしません。</span><span class="sxs-lookup"><span data-stu-id="68b5c-103">The rule engine does not support transactions in general.</span></span> <span data-ttu-id="68b5c-104">使用して、トランザクション的に、データベースを更新するただし、 **DataConnection**オブジェクトの次の手順で示すようにします。</span><span class="sxs-lookup"><span data-stu-id="68b5c-104">However, you can update a database in a transactional manner by using the **DataConnection** object as shown in the following steps:</span></span>  
  
1. <span data-ttu-id="68b5c-105">作成、 **SqlConnection**接続文字列を使用してオブジェクトし、の接続を開きます。</span><span class="sxs-lookup"><span data-stu-id="68b5c-105">Create a **SqlConnection** object by using a connection string, and open the connection.</span></span>  
  
   ```  
   SqlConnection connection = new SqlConnection("Initial Catalog=Northwind;Data Source=(local);Integrated Security=SSPI;");  
   connection.Open();  
   ```  
  
2. <span data-ttu-id="68b5c-106">作成、 **SqlTransaction**オブジェクトを呼び出すことによって、 **BeginTransaction**手順 1 で作成した接続オブジェクトのメソッド。</span><span class="sxs-lookup"><span data-stu-id="68b5c-106">Create a **SqlTransaction** object by calling the **BeginTransaction** method on the connection object you created in step 1.</span></span>  
  
   ```  
   SqlTransaction transaction = connection.BeginTransaction();  
   ```  
  
3. <span data-ttu-id="68b5c-107">作成、 **DataConnection**手順 1. および 2. で作成した接続とトランザクション オブジェクトを使用してオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="68b5c-107">Create a **DataConnection** object by using the connection and transaction objects you created in steps 1 and 2.</span></span>  
  
   ```  
   DataConnection dc = new DataConnection(datasetName, tableName, connection, transaction);  
   ```  
  
4. <span data-ttu-id="68b5c-108">渡す、 **DataConnection**オブジェクト、ポリシーに渡すし、ポリシーを実行すると共に、他のファクトをファクトとして。</span><span class="sxs-lookup"><span data-stu-id="68b5c-108">Pass the **DataConnection** object as a fact along with any other facts you want to pass to the policy, and execute the policy.</span></span>  
  
   ```  
   //Passing a .NET object as a fact along with the data connection  
   MyClass obj = new MyClass();  
   object[] facts = new object[2];  
   facts[0] = dc;  
   facts[1] = obj;  
   Policy pol = new Policy(policyName);  
   policy.Execute(facts);    
   ```  
  
5. <span data-ttu-id="68b5c-109">呼び出す、 **Update**データ接続オブジェクトのメソッド。</span><span class="sxs-lookup"><span data-stu-id="68b5c-109">Invoke the **Update** method on the data connection object.</span></span> <span data-ttu-id="68b5c-110">すべての更新プログラムは、メモリ内にのみ完了したら、ポリシーの実行中に実行します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-110">All the updates done while executing the policy are done only in memory.</span></span> <span data-ttu-id="68b5c-111">呼び出す必要があります、**更新**データベースを更新するデータ接続オブジェクトのメソッド。</span><span class="sxs-lookup"><span data-stu-id="68b5c-111">You must call the **Update** method on the data connection object to update the database.</span></span>  
  
   ```  
   dc.Update();  
   ```  
  
6. <span data-ttu-id="68b5c-112">次に、呼び出す**コミット**または**ロールバック**独自のロジックに基づいて、データ接続オブジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="68b5c-112">Now, invoke **Commit** or **Rollback** on the data connection object based on your own logic.</span></span>  
  
   ```  
   //Checking the value of PropertyA in .net object   
   //to decide whether to commit or rollback  
   if (obj.PropertyA == true)  
   transaction.Commit();  
   else  
   transaction.Rollback();  
  
   ```  
  
7. <span data-ttu-id="68b5c-113">接続を閉じ、ポリシー オブジェクトを破棄します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-113">Close the connection, and dispose the policy object.</span></span>  
  
   ```  
   sqlCon.Close();  
   policy.Dispose();  
   ```  
  
   <span data-ttu-id="68b5c-114">次のコードでは、すべての手順で完全なコードを示します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-114">The following code is the complete code with all the steps:</span></span>  
  
```  
SqlConnection connection = new SqlConnection("Initial Catalog=Northwind;Data Source=(local);Integrated Security=SSPI;");  
connection.Open();  
SqlTransaction transaction = connection.BeginTransaction();  
DataConnection dc = new DataConnection(datasetName, tableName, connection, transaction);  
MyClass obj = new MyClass();  
object[] facts = new object[2];  
facts[0] = dc;  
facts[1] = obj;  
Policy pol = new Policy(policyName);  
policy.Execute(facts);    
dc.Update();  
if (obj.PropertyA == true)  
transaction.Commit();  
else  
transaction.Rollback();  
sqlCon.Close();  
policy.Dispose();  
```  
  
## <a name="comments"></a><span data-ttu-id="68b5c-115">コメント</span><span class="sxs-lookup"><span data-stu-id="68b5c-115">Comments</span></span>  
  
-   <span data-ttu-id="68b5c-116">使用することも、 **OleDbConnection**と**OleDbTransaction**オブジェクトを使用してではなく、 **SqlConnection**と**SqlTransaction**トランザクション的にデータベースの更新を実行するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="68b5c-116">You can also use the **OleDbConnection** and **OleDbTransaction** objects instead of using the **SqlConnection** and **SqlTransaction** objects to perform database updates in a transactional manner.</span></span>  
  
-   <span data-ttu-id="68b5c-117">ポリシーから行われたすべての変更は、メモリ内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="68b5c-117">All the modifications done from the policy are done in memory.</span></span> <span data-ttu-id="68b5c-118">呼び出す必要があります、**更新**メソッドを**DataConnection**データベースを更新するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="68b5c-118">You must invoke the **Update** method on the **DataConnection** object to update the database.</span></span>  
  
-   <span data-ttu-id="68b5c-119">コミットするか、呼び出すことによってトランザクションをロールバックして、**コミット**または**ロールバック**のメソッド、 **DataConnection**それぞれオブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="68b5c-119">You can either commit or roll back the transaction by invoking the **Commit** or **Rollback** method of the **DataConnection** objects respectively.</span></span>