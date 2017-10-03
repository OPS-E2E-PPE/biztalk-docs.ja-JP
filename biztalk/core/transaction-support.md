---
title: "トランザクションのサポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataConnection object
- Business Rules Framework, code samples
- Business Rules Framework, programming
ms.assetid: 84faac2f-6229-4692-9d1a-bf62d87d69bb
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57fc1d7a1edd18663cb21a85037cf3e662948fc4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="transaction-support"></a>トランザクションのサポート
通常、ルール エンジンではトランザクションがサポートされません。 ただし、データベースを更新できますをトランザクション方式を使用して、 **DataConnection**オブジェクトの次の手順で示すようにします。  
  
1.  作成、 **SqlConnection**接続文字列を使用してオブジェクトし、の接続を開きます。  
  
    ```  
    SqlConnection connection = new SqlConnection("Initial Catalog=Northwind;Data Source=(local);Integrated Security=SSPI;");  
    connection.Open();  
    ```  
  
2.  作成、 **SqlTransaction**オブジェクトを呼び出して、 **BeginTransaction**手順 1. で作成した接続オブジェクトのメソッドです。  
  
    ```  
    SqlTransaction transaction = connection.BeginTransaction();  
    ```  
  
3.  作成、 **DataConnection**手順 1. および 2. で作成した接続とトランザクション オブジェクトを使用してオブジェクト。  
  
    ```  
    DataConnection dc = new DataConnection(datasetName, tableName, connection, transaction);  
    ```  
  
4.  渡す、 **DataConnection**オブジェクト、ポリシーに渡すし、ポリシーを実行すると共に他のファクトをファクトとして。  
  
    ```  
    //Passing a .NET object as a fact along with the data connection  
    MyClass obj = new MyClass();  
    object[] facts = new object[2];  
    facts[0] = dc;  
    facts[1] = obj;  
    Policy pol = new Policy(policyName);  
    policy.Execute(facts);    
    ```  
  
5.  呼び出す、**更新**データ接続オブジェクトのメソッドです。 ポリシーの実行時に処理される更新は、すべてメモリ内だけで実行されます。 呼び出す必要があります、**更新**オブジェクトのメソッドをデータ接続のデータベースを更新します。  
  
    ```  
    dc.Update();  
    ```  
  
6.  ここで、呼び出し**コミット**または**ロールバック**データ接続オブジェクトで、独自のロジックに基づきます。  
  
    ```  
    //Checking the value of PropertyA in .net object   
    //to decide whether to commit or rollback  
    if (obj.PropertyA == true)  
    transaction.Commit();  
    else  
    transaction.Rollback();  
  
    ```  
  
7.  接続を閉じ、ポリシー オブジェクトを破棄します。  
  
    ```  
    sqlCon.Close();  
    policy.Dispose();  
    ```  
  
 これまでの全手順を含めたコードを次に示します。  
  
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
  
-   使用することも、 **OleDbConnection**と**OleDbTransaction**オブジェクトの代わりに、 **SqlConnection**と**SqlTransaction**トランザクション的な方法でデータベースの更新を実行するオブジェクトです。  
  
-   ポリシーによって加えられる変更は、すべてメモリ内で実行されます。 呼び出す必要があります、**更新**メソッドを**DataConnection**データベースを更新するオブジェクト。  
  
-   コミットするかを呼び出してトランザクションをロールバックして、**コミット**または**ロールバック**のメソッド、 **DataConnection**それぞれオブジェクトします。