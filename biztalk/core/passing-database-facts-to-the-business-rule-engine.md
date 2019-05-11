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
# <a name="passing-database-facts-to-the-business-rule-engine"></a>ビジネス ルール エンジンへのデータベース ファクトの引き渡し
DataConnection と TypedDataTable のオブジェクトをファクトとしてを必要とするポリシーをテストするビジネス ルール作成ツールを使用する場合、DataConnection と TypedDataTable オブジェクトが自動的に作成され、ビジネス ルール エンジンの作業メモリにアサートします。 さらに、すべてのデータベース更新ポリシーによって自動的にコミットされます。  
  
 これに対し、オーケストレーションからポリシーを呼び出すを使用してルールの呼び出し図形またはプログラムでは、DataConnection と TypedDataTable オブジェクトは作成されませんがされ、データベースの更新はコミットされません自動的にします。 ここでは、DataConnection と TypedDataTable オブジェクトの作成をファクトとしてルール エンジンに渡す、およびプログラムで、次のメソッドのいずれかを使用して、データベースの変更をコミットする必要があります。  
  
## <a name="passing-a-dataconnection-object-from-an-orchestration"></a>オーケストレーションからの DataConnection オブジェクトの引き渡し  
 次のサンプル コードでは、オーケストレーションで DataConnection オブジェクトを作成、DataConnection オブジェクトをパラメーターとして渡すルールの呼び出し図形の構成し、ポリシーの実行後にすべてのデータベース更新をコミットする方法を示します。  
  
1.  オーケストレーション デザイナーでオーケストレーションを開き、[オーケストレーションの種類] タブを使用して、次の変数を作成します。  
  
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
  
3.  DataCon 変数をパラメーターとして渡すルールの呼び出し図形を構成します。 詳細については、次を参照してください。[ルールの呼び出し図形の使用方法](../core/how-to-use-the-call-rules-shape.md)します。  
  
4.  ルールの呼び出し図形の後に、式図形では、ポリシーによって、データベースの変更をコミットします。 次のコード例では、ポリシーによるデータベース変更をコミットする方法を示します。  
  
    ```  
    DataCon.Update();   
    SqlTran.Commit();  
    ```  
  
> [!NOTE]
>  使用する必要がある、 [SqlTransaction](http://msdn.microsoft.com/library/system.data.sqlclient.sqltransaction.aspx)オブジェクトのみ、ポリシー、データベースを更新します。  
  
## <a name="passing-a-dataconnection-object-from-a-fact-retriever"></a>ファクト取得コンポーネントから DataConnection オブジェクトの引き渡し  
 次に、ファクト取得コンポーネントから DataConnection オブジェクトを通過するために実装する必要がある一般的な手順を示します。  
  
1.  作成し、DataConnection オブジェクトをルール エンジンの作業メモリにアサートするファクト取得コンポーネントを作成します。 ファクト取得コンポーネントを作成する方法の詳細については、次を参照してください。[ファクト取得コンポーネントを作成する方法](../core/how-to-create-a-fact-retriever.md)します。  
  
2.  実装、 [IFactRemover](http://msdn.microsoft.com/library/Microsoft.RuleEngine.IFactRemover.aspx)ファクト取得コンポーネントのインターフェイスし、データベースの変更をコミット、 [UpdateFactsAfterExecution](http://msdn.microsoft.com/library/microsoft.ruleengine.ifactremover.updatefactsafterexecution.aspx)メソッド。 このメソッドは、ポリシーの実行が終了した後に、ルール エンジンによって呼び出されます。  
  
3.  ビジネス ルール作成ツールを使用して、ファクト取得コンポーネントを使用するポリシーを構成します。 詳細については、次を参照してください。[ポリシーのファクト取得コンポーネントを構成する方法](../core/how-to-configure-a-fact-retriever-for-a-policy.md)します。  
  
## <a name="see-also"></a>参照  
 [ビジネス ルール エンジンでのデータ アクセス](../core/data-access-in-the-business-rule-engine.md)   
 [ファクト取得コンポーネントを作成する方法](../core/how-to-create-a-fact-retriever.md)   
 [ポリシーのファクト取得コンポーネントを構成する方法](../core/how-to-configure-a-fact-retriever-for-a-policy.md)