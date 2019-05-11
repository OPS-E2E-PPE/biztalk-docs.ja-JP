---
title: Siebel ビジネス サービスに対して EXECUTE 操作を実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, execute business services using ADO.NET Provider
- performing operations, executing business services using ADO.NET Provider
ms.assetid: c8f7888f-72c6-4f20-b592-f233721fbddd
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8323de5d24100d4712e3919a37cfff090c612ea4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371214"
---
# <a name="run-an-execute-operation-on-business-services-with-siebel"></a><span data-ttu-id="32041-102">Siebel ビジネス サービスに対して EXECUTE 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="32041-102">Run an EXECUTE Operation on Business Services with Siebel</span></span>
<span data-ttu-id="32041-103">このセクションでは、Siebel ビジネス サービスを使用して、操作を実行する方法を示します、[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="32041-103">This section demonstrates how to execute an operation on a Siebel business service using the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)].</span></span>  
  
## <a name="executing-a-siebel-business-service"></a><span data-ttu-id="32041-104">Siebel ビジネス サービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="32041-104">Executing a Siebel Business Service</span></span>  
 <span data-ttu-id="32041-105">このセクションでは、Siebel リポジトリ内のビジネス サービスの操作を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="32041-105">This section demonstrates how to execute operations on a business service in the Siebel repository.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Data.Common;  
using System.Data;  
using Microsoft.Adapters.SiebelDbProvider;  
  
namespace SiebelADOBS  
{  
 class Program  
  {  
   static void Main(string[] args)  
    {  
      try  
       {  
        SiebelProviderFactory factory = SiebelProviderFactory.Instance;  
        DbConnection connection = factory.CreateConnection();  
        connection.ConnectionString = "Username=SADMIN;Password=SADMIN;ServiceUri=172.23.115.223:2321;SiebelObjectManager=SSEObjMgr;SiebelEnterpriseServer=ent771;Language=enu;SiebelRepository=Siebel Repository";  
  
        connection.Open();  
        DbCommand command = connection.CreateCommand();  
        command.CommandText = "EXEC ExtractDataService.Echo @In, @InOut, @Out OUTPUT";  
  
        //Add @In  
        DbParameter param1 = command.CreateParameter();  
        param1.ParameterName = "@In";  
        param1.Direction = ParameterDirection.Input;  
        param1.Value = "SomethingElse";  
        command.Parameters.Add(param1);  
  
        //Add @InOut  
        DbParameter param2 = command.CreateParameter();  
        param2.ParameterName = "@InOut";  
        param2.Direction = ParameterDirection.InputOutput;  
        command.Parameters.Add(param2);  
  
        //Add @Out  
        DbParameter outParam = command.CreateParameter();  
        outParam.ParameterName = "@Out";  
        outParam.Direction = ParameterDirection.Output;  
        command.Parameters.Add(outParam);  
  
        DbDataReader dbReader = command.ExecuteReader();  
  
        Console.WriteLine("Param2: " + param2.Value);  
        Console.WriteLine("OutParam: " + outParam.Value);  
  
        Console.WriteLine("Press any key...");  
        Console.ReadLine();  
      }  
     catch (Exception exp) { Console.WriteLine(exp.Message); }  
      }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="32041-106">参照</span><span class="sxs-lookup"><span data-stu-id="32041-106">See Also</span></span>  
 <span data-ttu-id="32041-107">[.NET Framework Data Provider 用 Siebel eBusiness Applications を使用して、](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md) </span><span class="sxs-lookup"><span data-stu-id="32041-107">[Use the .NET Framework Data Provider for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md) </span></span>  
 [<span data-ttu-id="32041-108">Siebel ビジネス コンポーネントで SELECT クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="32041-108">Run a SELECT Query on Business Components with Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/run-a-select-query-on-business-components-with-siebel.md)