---
title: "SAP の SELECT コマンドを使用してクエリを実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SELECT command, performing a query
- query, performing by using the SELECT command
ms.assetid: 6f03243c-ef50-4a4a-8fe6-4e525bd7efe3
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e03ac093e0fb7b2b8f95d770661bd702d988f01
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="run-a-query-using-the-select-command-in-sap"></a><span data-ttu-id="38775-102">SAP の SELECT コマンドを使用して、クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="38775-102">Run a Query Using the SELECT Command in SAP</span></span>
<span data-ttu-id="38775-103">[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ADO.NET データ ソースとしての SAP システムを公開します。</span><span class="sxs-lookup"><span data-stu-id="38775-103">The [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] exposes the SAP system as an ADO.NET data source.</span></span> <span data-ttu-id="38775-104">[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]、SELECT ステートメントを実行することによって SAP アイテムを照会することができます。</span><span class="sxs-lookup"><span data-stu-id="38775-104">With the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], you can query SAP artifacts by executing a SELECT statement.</span></span>  
  
## <a name="how-to-perform-a-query-by-using-the-select-command"></a><span data-ttu-id="38775-105">SELECT コマンドを使用してクエリを実行する方法</span><span class="sxs-lookup"><span data-stu-id="38775-105">How to Perform a Query by Using the SELECT Command</span></span>  
 <span data-ttu-id="38775-106">使用してクエリ SAP アイテムを[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="38775-106">To query SAP artifacts using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], perform the following steps:</span></span>  
  
#### <a name="to-perform-a-query"></a><span data-ttu-id="38775-107">クエリを実行するには</span><span class="sxs-lookup"><span data-stu-id="38775-107">To perform a query</span></span>  
  
1.  <span data-ttu-id="38775-108">参照を含める (および、コードでステートメントを使用) する**Microsoft.Data.SAPClient**です。</span><span class="sxs-lookup"><span data-stu-id="38775-108">Include a reference (and a using statement in your code) to **Microsoft.Data.SAPClient**.</span></span>  
  
2.  <span data-ttu-id="38775-109">作成、 **SAPConnection** SAP 接続文字列のデータ プロバイダーを使用するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="38775-109">Create a **SAPConnection** object by using a Data Provider for SAP connection string.</span></span> <span data-ttu-id="38775-110">接続文字列の詳細については、次を参照してください。 [SAP 接続文字列のデータ プロバイダーの種類の説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)です。</span><span class="sxs-lookup"><span data-stu-id="38775-110">For more information about the connection string, see [Read about Data Provider types for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
3.  <span data-ttu-id="38775-111">呼び出すことによって、SAP システムへの接続を開く**開く**上、 **SAPConnection**です。</span><span class="sxs-lookup"><span data-stu-id="38775-111">Open a connection to the SAP system by invoking **Open** on the **SAPConnection**.</span></span>  
  
4.  <span data-ttu-id="38775-112">作成、 **SAPCommand**オブジェクトから、 **SAPConnection**です。</span><span class="sxs-lookup"><span data-stu-id="38775-112">Create a **SAPCommand** object from the **SAPConnection**.</span></span>  
  
5.  <span data-ttu-id="38775-113">SELECT ステートメントの指定、 **CommandText**のプロパティ、 **SAPCommand**です。</span><span class="sxs-lookup"><span data-stu-id="38775-113">Specify the SELECT statement in the **CommandText** property of the **SAPCommand**.</span></span> <span data-ttu-id="38775-114">かどうか、必要に応じてパラメーターを指定できますを使用して**SAPParameter**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="38775-114">If necessary, you can specify parameters using **SAPParameter** objects.</span></span> <span data-ttu-id="38775-115">SELECT ステートメントを使用して SAP アイテムのクエリを実行する方法の詳細については、次を参照してください。 [SAP の SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="38775-115">For more information about how to query SAP artifacts using a SELECT statement, see [Syntax for a SELECT Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span></span> <span data-ttu-id="38775-116">RFC または BAPI を指定する方法の例については、次を参照してください。 [SELECT ステートメントの例](../../adapters-and-accelerators/adapter-sap/examples-for-select-statement.md)です。</span><span class="sxs-lookup"><span data-stu-id="38775-116">For examples of how to specify a BAPI or RFC, see [Examples for SELECT Statement](../../adapters-and-accelerators/adapter-sap/examples-for-select-statement.md).</span></span>  
  
6.  <span data-ttu-id="38775-117">クエリの実行し、で結果を取得するコマンドを実行、 **SAPDataReader**です。</span><span class="sxs-lookup"><span data-stu-id="38775-117">Execute the command to perform the query and obtain the results in a **SAPDataReader**.</span></span>  
  
7.  <span data-ttu-id="38775-118">結果を参照してから、 **SAPDataReader**です。</span><span class="sxs-lookup"><span data-stu-id="38775-118">Read the results from the **SAPDataReader**.</span></span>  
  
8.  <span data-ttu-id="38775-119">それらの使用が終了したら、終了 (または破棄)、 **SAPConnection**と**SAPDataReader**です。</span><span class="sxs-lookup"><span data-stu-id="38775-119">When you are finished using them, close (or dispose) the **SAPConnection** and the **SAPDataReader**.</span></span>  
  
 <span data-ttu-id="38775-120">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]も公開、 **SAPClientFactory**クラスは、作成に使用できる**SAPConnection**、 **SAPCommand**と**SAPConnection**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="38775-120">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] also exposes a **SAPClientFactory** class, which you can use to create **SAPConnection**, **SAPCommand** and **SAPConnection** objects.</span></span> <span data-ttu-id="38775-121">によって拡張された ADO.NET クラスの詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP アダプターを持つ ADO.NET インターフェイスを拡張](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="38775-121">For more information about the ADO.NET classes extended by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Extend ADO.NET Interfaces with the SAP adapter](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="38775-122">例</span><span class="sxs-lookup"><span data-stu-id="38775-122">Example</span></span>  
 <span data-ttu-id="38775-123">次の例では、コンソールに内部結合をパラメーター化されたステートメントの select の結果を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="38775-123">The following example writes the results of a select on a parameterized inner join statement to the console.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using Microsoft.Data.SAPClient;  
  
namespace SapAdoSelect  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
        /// <summary>  
        /// select top 1 * from sflight inner join spfli on sflight.connid = spfli.connid where spfli.connid = @connid  
        /// </summary>  
  
        string connstr = "TYPE=A; ASHOST=YourSapHost; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;";  
  
           using (SAPConnection conn = new SAPConnection(connstr))  
            {  
                conn.Open();  
                using (SAPCommand cmd = conn.CreateCommand())  
                {  
                    cmd.CommandText = "select top 1 * from sflight inner join spfli on sflight.connid = spfli.connid where spfli.connid = @connid";  
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
  
## <a name="see-also"></a><span data-ttu-id="38775-124">参照</span><span class="sxs-lookup"><span data-stu-id="38775-124">See Also</span></span>  
 <span data-ttu-id="38775-125">[使用して、.NET Framework Data Provider 用 mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md) </span><span class="sxs-lookup"><span data-stu-id="38775-125">[Use the .NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md) </span></span>  
 [<span data-ttu-id="38775-126">サンプル</span><span class="sxs-lookup"><span data-stu-id="38775-126">Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)