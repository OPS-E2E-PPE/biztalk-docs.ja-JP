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
# <a name="run-an-execute-operation-on-business-services-with-siebel"></a>Siebel ビジネス サービスに対して EXECUTE 操作を実行します。
このセクションでは、Siebel ビジネス サービスを使用して、操作を実行する方法を示します、[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]します。  
  
## <a name="executing-a-siebel-business-service"></a>Siebel ビジネス サービスを実行します。  
 このセクションでは、Siebel リポジトリ内のビジネス サービスの操作を実行する方法を示します。  
  
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
  
## <a name="see-also"></a>参照  
 [.NET Framework Data Provider 用 Siebel eBusiness Applications を使用して、](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)   
 [Siebel ビジネス コンポーネントで SELECT クエリを実行します。](../../adapters-and-accelerators/adapter-siebel/run-a-select-query-on-business-components-with-siebel.md)