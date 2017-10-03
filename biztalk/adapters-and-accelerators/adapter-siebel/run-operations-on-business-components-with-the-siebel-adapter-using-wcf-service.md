---
title: "WCF サービス モデルを使用して、Siebel アダプターとビジネス コンポーネントでの操作を実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model, performing operations on business components
- how to, perform operations using the proxy
- business components, performing operations by using the WCF service model
- performing operations, using the proxy
ms.assetid: 7a5fdc95-6159-4f43-aac5-4e2f84e9138b
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99ac40efda9ed8c27fb5ac5fedfbe782b9a4f645
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="run-operations-on-business-components-with-the-siebel-adapter-using-the-wcf-service-model"></a>WCF サービス モデルを使用して、Siebel アダプターとビジネス コンポーネントでの操作を実行します。
Siebel ビジネス コンポーネントを対象とする WCF クライアントを作成することができます。 Siebel システムに挿入、更新、クエリ、削除、関連付ける、関連付けを解除、およびビジネス コンポーネントに対して子レコードのクエリ操作を実行し、WCF クライアントを使用できます。 [ビジネス オブジェクト] ノードに表示された Siebel ビジネス オブジェクト、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]です。 各ビジネス オブジェクトを作成するビジネス コンポーネントは、そのオブジェクトに対応するノードの下に表示されます。 」の手順を行うことができる[Siebel アダプターと WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-siebel/overview-of-the-wcf-service-model-with-the-siebel-adapter.md)を特定の操作を対象とするビジネス コンポーネント用の WCF クライアントを生成して、ビジネスでこれらの操作を呼び出すクライアントを使用するにはコンポーネント。  
  
> [!NOTE]
>  このトピックでは、ビジネス コンポーネントの基本操作 (挿入、更新、クエリ、削除) の実行に関する情報を提供します。 関連付ける、関連付けを解除、および子レコードのクエリ操作の実行に関する詳細については、次を参照してください[WCF サービス モデルを使用して MVG フィールドのビジネス コンポーネントでの操作を実行。](../../adapters-and-accelerators/adapter-siebel/work-with-mvp-fields-using-the-siebel-adapter-and-the-wcf-service-model.md)  
  
 次のコードでは、WCF クライアントを使用して、アカウントのビジネス オブジェクトのビジネス コンポーネントのアカウント レコードに対して Insert、Update、および Delete の操作を実行します。 各操作の間でクエリ操作は結果を確認する実行されます。 によって生成される構成ファイルからこの例では、WCF クライアントが初期化されて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 生成された構成ファイルの例は、次を参照してください。 [Siebel システムの WCF クライアントを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)です。  
  
```  
  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using microsoft.lobservices.siebel._2007._03.BusinessObjects;  
using microsoft.lobservices.siebel._2007._03;  
  
namespace Business_Component_Operations  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            BusinessObjects_Account_Account_OperationClient client = null;  
  
            try  
            {  
  
                client = new BusinessObjects_Account_Account_OperationClient("SiebelBinding_BusinessObjects_Account_Account_Operation");  
                client.ClientCredentials.UserName.UserName = "YourUserName";  
                client.ClientCredentials.UserName.Password = "YourPassword";  
  
                Console.WriteLine("Opening connection to " + client.Endpoint.Address.Uri.Host);  
                client.Open();  
                AccountInsertRecord[] air = new AccountInsertRecord[1];  
                air[0] = new AccountInsertRecord();  
                Random r = new Random();  
                int count = r.Next();  
  
                air[0].Name = "Anil" + count.ToString();  
                Console.WriteLine("Inserting " + air[0].Name + " ...");  
                client.Insert(air);  
  
                //Query for the record.  
                Console.WriteLine("Querying to check inserted record ...");  
                AccountQueryInputRecord aqir = new AccountQueryInputRecord();  
                short viewmode = new short(); viewmode = 3;  
                string[] fields = new string[2];  
                fields[0] = "Name";  
                fields[1] = "Id";  
                aqir.QueryFields = fields;  
                aqir.SearchExpr = "[Name] LIKE \"Anil*\"";  
                AccountQueryRecord[] aqr = client.Query(viewmode, aqir);  
                Console.WriteLine(aqr.Length + " records returned");  
                string[] ids = new string[1];  
                AccountUpdateRecord[] aur = new AccountUpdateRecord[1];  
                aur[0] = new AccountUpdateRecord();  
                foreach (AccountQueryRecord rec in aqr)  
                {  
                    Console.WriteLine("Name: " + rec.Name);  
                    Console.WriteLine("Id: " + rec.Id);  
                    Console.WriteLine("");  
                    ids[0] = rec.Id;  
                    aur[0].Name = rec.Name;  
                    aur[0].Id = rec.Id;  
                }  
  
                //Update it.  
  
                aur[0].Name = "Anil" + count.ToString() + "modified";  
                Console.WriteLine("Update the record to " + aur[0].Name + " ...");  
                client.Update(viewmode, aur);  
                //query again  
                aqr = client.Query(viewmode, aqir);  
                Console.WriteLine(aqr.Length + " records returned");  
                foreach (AccountQueryRecord rec in aqr)  
                {  
                    Console.WriteLine("Name: " + rec.Name);  
                    Console.WriteLine("Id: " + rec.Id);  
                    Console.WriteLine("");  
                }  
  
                //Delete it.  
                Console.WriteLine("Deleting record ...");  
                client.Delete(viewmode, ids, "");  
  
                //Check again.  
                Console.WriteLine("Check that " + aur[0].Name + " is not present");  
                aqr = client.Query(viewmode, aqir);  
  
                Console.WriteLine(aqr.Length + " records returned");  
                foreach (AccountQueryRecord rec in aqr)  
                {  
                    Console.WriteLine(rec.Name);  
                    Console.WriteLine(rec.Id);  
  
                }  
  
                // Wait for <RETURN> to end sample.  
                Console.WriteLine("\nHit <RETURN> to finish");  
                Console.ReadLine();  
  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine(e.Message);  
            }  
            finally  
            {  
                // Close the client.  
                if (client != null)  
                {  
                    if (client.State == CommunicationState.Opened)  
                        client.Close();  
                    else  
                        client.Abort();  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Siebel アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)