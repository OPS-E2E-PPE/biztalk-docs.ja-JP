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
# <a name="transaction-support"></a>トランザクションのサポート
ルール エンジンでは、トランザクションを一般にサポートしません。 使用して、トランザクション的に、データベースを更新するただし、 **DataConnection**オブジェクトの次の手順で示すようにします。  
  
1. 作成、 **SqlConnection**接続文字列を使用してオブジェクトし、の接続を開きます。  
  
   ```  
   SqlConnection connection = new SqlConnection("Initial Catalog=Northwind;Data Source=(local);Integrated Security=SSPI;");  
   connection.Open();  
   ```  
  
2. 作成、 **SqlTransaction**オブジェクトを呼び出すことによって、 **BeginTransaction**手順 1 で作成した接続オブジェクトのメソッド。  
  
   ```  
   SqlTransaction transaction = connection.BeginTransaction();  
   ```  
  
3. 作成、 **DataConnection**手順 1. および 2. で作成した接続とトランザクション オブジェクトを使用してオブジェクト。  
  
   ```  
   DataConnection dc = new DataConnection(datasetName, tableName, connection, transaction);  
   ```  
  
4. 渡す、 **DataConnection**オブジェクト、ポリシーに渡すし、ポリシーを実行すると共に、他のファクトをファクトとして。  
  
   ```  
   //Passing a .NET object as a fact along with the data connection  
   MyClass obj = new MyClass();  
   object[] facts = new object[2];  
   facts[0] = dc;  
   facts[1] = obj;  
   Policy pol = new Policy(policyName);  
   policy.Execute(facts);    
   ```  
  
5. 呼び出す、 **Update**データ接続オブジェクトのメソッド。 すべての更新プログラムは、メモリ内にのみ完了したら、ポリシーの実行中に実行します。 呼び出す必要があります、**更新**データベースを更新するデータ接続オブジェクトのメソッド。  
  
   ```  
   dc.Update();  
   ```  
  
6. 次に、呼び出す**コミット**または**ロールバック**独自のロジックに基づいて、データ接続オブジェクトにします。  
  
   ```  
   //Checking the value of PropertyA in .net object   
   //to decide whether to commit or rollback  
   if (obj.PropertyA == true)  
   transaction.Commit();  
   else  
   transaction.Rollback();  
  
   ```  
  
7. 接続を閉じ、ポリシー オブジェクトを破棄します。  
  
   ```  
   sqlCon.Close();  
   policy.Dispose();  
   ```  
  
   次のコードでは、すべての手順で完全なコードを示します。  
  
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
  
## <a name="comments"></a>コメント  
  
-   使用することも、 **OleDbConnection**と**OleDbTransaction**オブジェクトを使用してではなく、 **SqlConnection**と**SqlTransaction**トランザクション的にデータベースの更新を実行するオブジェクト。  
  
-   ポリシーから行われたすべての変更は、メモリ内で実行されます。 呼び出す必要があります、**更新**メソッドを**DataConnection**データベースを更新するオブジェクト。  
  
-   コミットするか、呼び出すことによってトランザクションをロールバックして、**コミット**または**ロールバック**のメソッド、 **DataConnection**それぞれオブジェクトします。