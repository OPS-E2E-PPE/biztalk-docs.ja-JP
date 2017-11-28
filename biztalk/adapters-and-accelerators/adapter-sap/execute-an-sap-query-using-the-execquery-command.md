---
title: "EXECQUERY コマンドを使用して SAP クエリの実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 520153bf-9477-4b35-8953-3f5cb444ab9f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86159a03858ae5aa31bb37da56b6e5ea68dac3ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="execute-an-sap-query-using-the-execquery-command"></a><span data-ttu-id="422bc-102">EXECQUERY コマンドを使用して SAP クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="422bc-102">Execute an SAP Query Using the EXECQUERY Command</span></span>
<span data-ttu-id="422bc-103">[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ADO.NET データ ソースとしての SAP システムを公開します。</span><span class="sxs-lookup"><span data-stu-id="422bc-103">The [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] exposes the SAP system as an ADO.NET data source.</span></span> <span data-ttu-id="422bc-104">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]、EXECQUERY ステートメントを実行して、SAP システムで定義済みのクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="422bc-104">With the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], you can execute pre-defined queries in the SAP system by executing an EXECQUERY statement.</span></span>  
  
## <a name="how-to-perform-a-query-by-using-the-execquery-command"></a><span data-ttu-id="422bc-105">EXECQUERY コマンドを使用してクエリを実行する方法</span><span class="sxs-lookup"><span data-stu-id="422bc-105">How to Perform a Query by Using the EXECQUERY Command</span></span>  
 <span data-ttu-id="422bc-106">定義済みの SAP を実行するクエリを使用して、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="422bc-106">To execute pre-defined SAP queries using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], perform the following steps:</span></span>  
  
#### <a name="to-perform-a-query"></a><span data-ttu-id="422bc-107">クエリを実行するには</span><span class="sxs-lookup"><span data-stu-id="422bc-107">To perform a query</span></span>  
  
1.  <span data-ttu-id="422bc-108">参照を含める (および、コードでステートメントを使用) する**Microsoft.Data.SAPClient**です。</span><span class="sxs-lookup"><span data-stu-id="422bc-108">Include a reference (and a using statement in your code) to **Microsoft.Data.SAPClient**.</span></span>  
  
2.  <span data-ttu-id="422bc-109">作成、 **SAPConnection** SAP 接続文字列のデータ プロバイダーを使用するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="422bc-109">Create a **SAPConnection** object by using a Data Provider for SAP connection string.</span></span> <span data-ttu-id="422bc-110">接続文字列の詳細については、次を参照してください。 [SAP 接続文字列のデータ プロバイダーの種類の説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)です。</span><span class="sxs-lookup"><span data-stu-id="422bc-110">For more information about the connection string, see [Read about Data Provider types for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
3.  <span data-ttu-id="422bc-111">呼び出すことによって、SAP システムへの接続を開く**開く**上、 **SAPConnection**です。</span><span class="sxs-lookup"><span data-stu-id="422bc-111">Open a connection to the SAP system by invoking **Open** on the **SAPConnection**.</span></span>  
  
4.  <span data-ttu-id="422bc-112">作成、 **SAPCommand**オブジェクトから、 **SAPConnection**です。</span><span class="sxs-lookup"><span data-stu-id="422bc-112">Create a **SAPCommand** object from the **SAPConnection**.</span></span>  
  
5.  <span data-ttu-id="422bc-113">EXECQUERY ステートメントを指定して、 **CommandText**のプロパティ、 **SAPCommand**です。</span><span class="sxs-lookup"><span data-stu-id="422bc-113">Specify the EXECQUERY statement in the **CommandText** property of the **SAPCommand**.</span></span> <span data-ttu-id="422bc-114">かどうか、必要に応じてパラメーターを指定できますを使用して**SAPParameter**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="422bc-114">If necessary, you can specify parameters using **SAPParameter** objects.</span></span> <span data-ttu-id="422bc-115">EXECQUERY ステートメントを使用して SAP システムで定義されているクエリを実行する方法の詳細については、次を参照してください。 [SAP 内の EXECQUERY ステートメントに対して構文](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="422bc-115">For more information about how to execute queries defined in an SAP system using an EXECQUERY statement, see [Syntax for an EXECQUERY Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md).</span></span>  
  
6.  <span data-ttu-id="422bc-116">クエリの実行し、で結果を取得するコマンドを実行、 **SAPDataReader**です。</span><span class="sxs-lookup"><span data-stu-id="422bc-116">Execute the command to perform the query and obtain the results in a **SAPDataReader**.</span></span>  
  
7.  <span data-ttu-id="422bc-117">結果を参照してから、 **SAPDataReader**です。</span><span class="sxs-lookup"><span data-stu-id="422bc-117">Read the results from the **SAPDataReader**.</span></span>  
  
8.  <span data-ttu-id="422bc-118">それらの使用が終了したら、終了 (または破棄)、 **SAPConnection**と**SAPDataReader**です。</span><span class="sxs-lookup"><span data-stu-id="422bc-118">When you are finished using them, close (or dispose) the **SAPConnection** and the **SAPDataReader**.</span></span>  
  
 <span data-ttu-id="422bc-119">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]も公開、 **SAPClientFactory**クラスは、作成に使用できる**SAPConnection**、 **SAPCommand**と**SAPConnection**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="422bc-119">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] also exposes a **SAPClientFactory** class, which you can use to create **SAPConnection**, **SAPCommand** and **SAPConnection** objects.</span></span> <span data-ttu-id="422bc-120">によって拡張された ADO.NET クラスの詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP アダプターを持つ ADO.NET インターフェイスを拡張](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="422bc-120">For more information about the ADO.NET classes extended by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Extend ADO.NET Interfaces with the SAP adapter](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="422bc-121">例</span><span class="sxs-lookup"><span data-stu-id="422bc-121">Example</span></span>  
 <span data-ttu-id="422bc-122">次の例では、ZTEST1、クエリの結果をコンソールに出力します。</span><span class="sxs-lookup"><span data-stu-id="422bc-122">The following example writes the results of a query, ZTEST1, to the console.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using Microsoft.Data.SAPClient;  
  
namespace SapAdoExecQuery  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
           string connstr = "TYPE=A; ASHOST=YourSapHost; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;";  
           using (SAPConnection conn = new SAPConnection(connstr))  
            {  
                conn.Open();  
                using (SAPCommand cmd = conn.CreateCommand())  
                {  
                    cmd.CommandText = "EXECQUERY ZTEST1 @userGRoup='SYSTQV000024',@P1='0000001390',@P2='0000080150'";  
                    cmd.Parameters.Add(new SAPParameter("@connid", 17));                      
                    using (SAPDataReader dr = cmd.ExecuteReader())  
                    {  
                        do  
                        {  
                            int rows = 0;  
                            while (dr.Read())  
                            {  
                                rows++;  
                                StringBuilder b = new StringBuilder();  
                                for (int i = 0; i < dr.FieldCount; i++)  
                                {  
                                    b.Append(dr[i].ToString()+" ");  
                                }  
                                Console.WriteLine("row {0}: {1} ", rows, b.ToString());  
                            }  
                            Console.WriteLine("Number of rows:{0}", rows);  
                        } while (dr.NextResult());  
                    }  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="422bc-123">参照</span><span class="sxs-lookup"><span data-stu-id="422bc-123">See Also</span></span>  
 [<span data-ttu-id="422bc-124">使用して、.NET Framework Data Provider 用 mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="422bc-124">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)  
 [<span data-ttu-id="422bc-125">サンプル</span><span class="sxs-lookup"><span data-stu-id="422bc-125">Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)