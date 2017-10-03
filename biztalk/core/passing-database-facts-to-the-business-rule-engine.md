---
title: "ビジネス ルール エンジン データベース ファクトを渡す |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62285bbe-ee64-4c26-b48e-55f666dc1304
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01ae35802263b71965698e0bb56d1ddbee9ae0a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="passing-database-facts-to-the-business-rule-engine"></a>ビジネス ルール エンジンへのデータベースのファクトの引き渡し
DataConnection と TypedDataTable オブジェクトをファクトとしてを必要とするポリシーをテストするビジネス ルール作成ツールを使用する場合、DataConnection と TypedDataTable オブジェクトが自動的に作成され、ビジネス ルール エンジンの作業メモリにアサートします。 さらに、ポリシーによるデータベースの更新がすべて自動的にコミットされます。  
  
 これに対し、オーケストレーションからポリシーを呼び出すと、いずれかを使用してルールの呼び出し図形またはプログラムでは、DataConnection と TypedDataTable オブジェクトは作成されず、データベースの更新はコミットされません自動的にされます。 この例では、DataConnection と TypedDataTable オブジェクトを作成をファクトとしてルール エンジンに渡すこと、および、次のメソッドのいずれかを使用してプログラムでデータベースの変更をコミットする必要があります。  
  
## <a name="passing-a-dataconnection-object-from-an-orchestration"></a>オーケストレーションからの DataConnection オブジェクトの引き渡し  
 次のサンプル コードは、オーケストレーションで DataConnection オブジェクトを作成し、DataConnection オブジェクトをパラメーターとして渡すようにルールの呼び出し図形を構成して、ポリシーが実行された後にすべてのデータベース更新をコミットする方法を示しています。  
  
1.  オーケストレーション デザイナーで、オーケストレーションを開いた状態で [オーケストレーションの種類] タブを使用して次の変数を作成します。  
  
    ```  
    DataCon of type Microsoft.RuleEngine.DataConnection   
    SqlCon of type System.Data.SqlClient.SqlConnection   
    SqlTran of type System.Data.SqlClient.SqlTransaction   
    ```  
  
2.  ルールの呼び出し図形の前に、式図形では、DataConnection オブジェクトを作成します。 次のコード例では、DataConnection オブジェクトを作成する方法を示します。  
  
    ```  
    SqlCon.ConnectionString = "Data Source=(local);Initial Catalog=Test;Integrated Security=SSPI";   
    SqlCon.Open();   
    SqlTran = SqlCon.BeginTransaction();   
    DataCon = new Microsoft.RuleEngine.DataConnection("test", "FlagTable", SqlCon, SqlTran);    
    ```  
  
3.  DataCon 変数をパラメーターとして渡すようにルールの呼び出し図形を構成します。 詳細については、次を参照してください。[ルールの呼び出し図形を使用する方法](../core/how-to-use-the-call-rules-shape.md)です。  
  
4.  ルールの呼び出し図形の後の式図形で、ポリシーによるデータベースの変更をコミットします。 ポリシーによるデータベースの変更をコミットする方法を次のコード例に示します。  
  
    ```  
    DataCon.Update();   
    SqlTran.Commit();  
    ```  
  
> [!NOTE]
>  使用する必要があります、 [SqlTransaction](http://msdn.microsoft.com/library/system.data.sqlclient.sqltransaction.aspx)ポリシーが、データベースを更新するかどうかのオブジェクトのみです。  
  
## <a name="passing-a-dataconnection-object-from-a-fact-retriever"></a>ファクト取得コンポーネントからの DataConnection オブジェクトの引き渡し  
 ここでは、ファクト取得コンポーネントから DataConnection オブジェクトを渡すために実装する必要のある通常の手順を示します。  
  
1.  DataConnection オブジェクトを作成してルール エンジンの作業メモリにアサートするファクト取得コンポーネントを作成します。 ファクト取得コンポーネントを作成する方法の詳細については、次を参照してください。[ファクト取得コンポーネントを作成する方法](../core/how-to-create-a-fact-retriever.md)です。  
  
2.  実装、 [IFactRemover](http://msdn.microsoft.com/library/Microsoft.RuleEngine.IFactRemover.aspx)ファクト取得コンポーネントのインターフェイスし、のデータベースの変更をコミット、 [UpdateFactsAfterExecution](http://msdn.microsoft.com/library/microsoft.ruleengine.ifactremover.updatefactsafterexecution.aspx)メソッドです。 このメソッドは、ポリシーの実行が終了した後、ルール エンジンによって呼び出されます。  
  
3.  ビジネス ルール作成ツールを使用して、ファクト取得コンポーネントを使用するようにポリシーを構成します。 詳細については、次を参照してください。[ポリシーのファクト取得コンポーネントを構成する方法](../core/how-to-configure-a-fact-retriever-for-a-policy.md)です。  
  
## <a name="see-also"></a>参照  
 [ビジネス ルール エンジンでのデータ アクセス](../core/data-access-in-the-business-rule-engine.md)   
 [ファクト取得コンポーネントを作成する方法](../core/how-to-create-a-fact-retriever.md)   
 [ポリシーのファクト取得コンポーネントを構成する方法](../core/how-to-configure-a-fact-retriever-for-a-policy.md)