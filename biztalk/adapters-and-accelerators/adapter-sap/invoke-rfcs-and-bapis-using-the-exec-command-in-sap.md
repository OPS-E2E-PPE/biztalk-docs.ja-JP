---
title: Rfc と EXEC コマンドを使用して SAP の Bapi を呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- EXEC command, invoking RFCs and BAPIs
- BAPIs and RFCs, invoking by using the EXEC command
- RFCs and BAPIs, invoking by using the EXEC command
ms.assetid: 55443679-2fa8-4c13-ac3b-1c85b5166cd2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7ddd9e4d3e7d4c4d34445c7a42d83262d04f4b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988195"
---
# <a name="invoke-rfcs-and-bapis-using-the-exec-command-in-sap"></a><span data-ttu-id="c7263-102">Rfc と EXEC コマンドを使用して SAP の Bapi を呼び出す</span><span class="sxs-lookup"><span data-stu-id="c7263-102">Invoke RFCs and BAPIs using the EXEC Command in SAP</span></span>
<span data-ttu-id="c7263-103">[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ADO.NET データ ソースとしての SAP システムを公開します。</span><span class="sxs-lookup"><span data-stu-id="c7263-103">The [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] exposes the SAP system as an ADO.NET data source.</span></span> <span data-ttu-id="c7263-104">使用して[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]、EXEC コマンドを通して、SAP システムの Rfc および Bapi を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="c7263-104">By using [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], you can invoke RFCs and BAPIs on the SAP system through an EXEC command.</span></span>  
  
## <a name="how-to-invoke-rfcs-and-bapis-on-the-sap-system"></a><span data-ttu-id="c7263-105">SAP システムでの呼び出しの Rfc および Bapi の方法</span><span class="sxs-lookup"><span data-stu-id="c7263-105">How to Invoke RFCs and BAPIs on the SAP system</span></span>  
 <span data-ttu-id="c7263-106">RFC または BAPI を使用してを呼び出す、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c7263-106">To invoke an RFC or BAPI using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], perform the following steps:</span></span>  
  
#### <a name="to-invoke-an-rfc-or-bapi"></a><span data-ttu-id="c7263-107">RFC または BAPI を呼び出す</span><span class="sxs-lookup"><span data-stu-id="c7263-107">To invoke an RFC or BAPI</span></span>  
  
1. <span data-ttu-id="c7263-108">参照を含める (と、コードでステートメントを使用) に**Microsoft.Data.SAPClient**します。</span><span class="sxs-lookup"><span data-stu-id="c7263-108">Include a reference (and a using statement in your code) to **Microsoft.Data.SAPClient**.</span></span>  
  
2. <span data-ttu-id="c7263-109">作成、 **SAPConnection** SAP 接続文字列のデータ プロバイダーを使用してオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c7263-109">Create a **SAPConnection** object by using a Data Provider for SAP connection string.</span></span> <span data-ttu-id="c7263-110">接続文字列の詳細については、[SAP 接続文字列のデータ プロバイダーの種類について](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7263-110">For more information about the connection string, see [Read about Data Provider types for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
3. <span data-ttu-id="c7263-111">呼び出すことによって、SAP システムへの接続を開く**オープン**上、 **SAPConnection**します。</span><span class="sxs-lookup"><span data-stu-id="c7263-111">Open a connection to the SAP system by invoking **Open** on the **SAPConnection**.</span></span>  
  
4. <span data-ttu-id="c7263-112">作成、 **SAPCommand**オブジェクトから、 **SAPConnection**します。</span><span class="sxs-lookup"><span data-stu-id="c7263-112">Create a **SAPCommand** object from the **SAPConnection**.</span></span>  
  
5. <span data-ttu-id="c7263-113">BAPI または RFC の呼び出しを指定、 **CommandText**のプロパティ、 **SAPCommand**します。</span><span class="sxs-lookup"><span data-stu-id="c7263-113">Specify the BAPI or RFC call in the **CommandText** property of the **SAPCommand**.</span></span> <span data-ttu-id="c7263-114">かどうか、必要に応じてパラメーターを指定できますを使用して**SAPParameter**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c7263-114">If necessary, you can specify parameters using **SAPParameter** objects.</span></span> <span data-ttu-id="c7263-115">EXEC ステートメントを使用して、BAPI または RFC の呼び出しを指定する方法の詳細については、[sap EXEC ステートメントの構文](../../adapters-and-accelerators/adapter-sap/syntax-for-an-exec-statement-in-sap.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7263-115">For more information about how to specify a BAPI or RFC call using an EXEC statement, see [Syntax for an EXEC Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-an-exec-statement-in-sap.md).</span></span> <span data-ttu-id="c7263-116">RFC または BAPI を指定する方法の例については、[EXEC ステートメントの例](../../adapters-and-accelerators/adapter-sap/examples-for-exec-statement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7263-116">For examples of how to specify a BAPI or RFC, see [Examples for EXEC Statement](../../adapters-and-accelerators/adapter-sap/examples-for-exec-statement.md).</span></span>  
  
6. <span data-ttu-id="c7263-117">RFC または BAPI を呼び出すしで結果を取得するコマンドを実行する**SAPDataReader**します。</span><span class="sxs-lookup"><span data-stu-id="c7263-117">Execute the command to invoke the RFC or BAPI and obtain the results in a **SAPDataReader**.</span></span>  
  
7. <span data-ttu-id="c7263-118">結果を読み取り、 **SAPDataReader**します。</span><span class="sxs-lookup"><span data-stu-id="c7263-118">Read the results from the **SAPDataReader**.</span></span>  
  
8. <span data-ttu-id="c7263-119">それらの使用が終了したら、閉じる (または dispose)、 **SAPConnection**と**SAPDataReader**します。</span><span class="sxs-lookup"><span data-stu-id="c7263-119">When you are finished using them, close (or dispose) the **SAPConnection** and the **SAPDataReader**.</span></span>  
  
   <span data-ttu-id="c7263-120">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]も公開、 **SAPClientFactory**クラスで、作成に使用できる**SAPConnection**、 **SAPCommand**と**SAPConnection**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c7263-120">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] also exposes a **SAPClientFactory** class, which you can use to create **SAPConnection**, **SAPCommand** and **SAPConnection** objects.</span></span> <span data-ttu-id="c7263-121">拡張によって、ADO.NET のクラスの詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP アダプターを使用した ADO.NET インターフェイスの拡張](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="c7263-121">For more information about the ADO.NET classes extended by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Extend ADO.NET Interfaces with the SAP adapter](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7263-122">例</span><span class="sxs-lookup"><span data-stu-id="c7263-122">Example</span></span>  
 <span data-ttu-id="c7263-123">次の例では、"AB"で始まる名前のすべてのお客様の顧客情報を取得する SD_RFC_CUSTOMER_GET を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c7263-123">The following example invokes SD_RFC_CUSTOMER_GET to retrieve customer information for all customers whose names start with "AB".</span></span> <span data-ttu-id="c7263-124">顧客レコードをコンソールに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="c7263-124">It then writes the customer records to the console.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using Microsoft.Data.SAPClient;  
  
namespace SapAdoExec  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            string connstr = "TYPE=A; ASHOST=YourSAPHost; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;";  
  
            using (SAPConnection conn = new SAPConnection(connstr))  
            {  
                conn.Open();  
  
                using (SAPCommand cmd = conn.CreateCommand())  
                {  
                    cmd.CommandText = "exec sd_rfc_customer_get @name1='AB*' ";  
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
                                    b.Append(dr[i].ToString() + " ");  
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
  
## <a name="see-also"></a><span data-ttu-id="c7263-125">参照</span><span class="sxs-lookup"><span data-stu-id="c7263-125">See Also</span></span>  
 <span data-ttu-id="c7263-126">[使用して、.NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md) </span><span class="sxs-lookup"><span data-stu-id="c7263-126">[Use the .NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md) </span></span>  
 [<span data-ttu-id="c7263-127">サンプル</span><span class="sxs-lookup"><span data-stu-id="c7263-127">Samples</span></span>](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)