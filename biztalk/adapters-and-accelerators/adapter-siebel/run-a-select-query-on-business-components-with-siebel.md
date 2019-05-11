---
title: Siebel ビジネス コンポーネントで SELECT クエリを実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performing operations, selecting data using ADO.NET provider
- how to, select data in business components using ADO.NET provider
ms.assetid: 34a22c2e-6fc9-4760-90a1-131a38ae947b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bae686ace4f7feea8b5084f7d4844df61ea79807
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371130"
---
# <a name="run-a-select-query-on-business-components-with-siebel"></a><span data-ttu-id="73c55-102">Siebel ビジネス コンポーネントで SELECT クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="73c55-102">Run a SELECT Query on Business Components with Siebel</span></span>
<span data-ttu-id="73c55-103">このセクションで使用して Siebel ビジネス コンポーネントからデータを選択する方法を示す、[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="73c55-103">This section demonstrates how to select data from a Siebel business component using the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)].</span></span>  
  
## <a name="selecting-data-from-a-siebel-business-component"></a><span data-ttu-id="73c55-104">Siebel ビジネス コンポーネントからデータを選択</span><span class="sxs-lookup"><span data-stu-id="73c55-104">Selecting Data from a Siebel Business Component</span></span>  
 <span data-ttu-id="73c55-105">このセクションでは、Siebel リポジトリ内の「アカウント」ビジネス コンポーネントからデータを選択する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="73c55-105">This section demonstrates how to select data from the "Account" business component in the Siebel repository.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Data.Common;  
using Microsoft.Adapters.SiebelDbProvider;  
  
namespace SiebelADO  
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
  
         //Here is a list of sample commands. The second command shows how the Siebel ViewMode can be specified in the query.  
         //command.CommandText = "SELECT * from Account.Account where [Name] LIKE '3Com'";  
         //command.CommandText = "Select [Name] from [Account].[Account] where [Name] LIKE '3Com' OPTION ‘ViewMode 1’";  
           command.CommandText = "SELECT [Name], [Postal Code], Id From Account.Account where [Postal Code] != '60626' Order BY Id ASC, Name DESC";  
  
         DbDataReader dbReader = command.ExecuteReader();  
  
         while (dbReader.Read())  
           {  
              for (int i = 0; i < dbReader.FieldCount; i++)  
               {  
                 string name = dbReader.GetName(i);  
                 string val = dbReader[i].ToString();  
                 Console.WriteLine(name + "\t:" + val);  
                 Console.WriteLine("=========================");  
               }  
           }  
             Console.WriteLine("Press any key...");  
             Console.ReadLine();  
       }  
       catch (Exception exp) { Console.WriteLine(exp.Message); }  
       }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="73c55-106">参照</span><span class="sxs-lookup"><span data-stu-id="73c55-106">See Also</span></span>  
 <span data-ttu-id="73c55-107">[.NET Framework Data Provider 用 Siebel eBusiness Applications を使用して、](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md) </span><span class="sxs-lookup"><span data-stu-id="73c55-107">[Use the .NET Framework Data Provider for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md) </span></span>  
 [<span data-ttu-id="73c55-108">Siebel ビジネス サービスに対して EXECUTE 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="73c55-108">Run an EXECUTE Operation on Business Services with Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/run-an-execute-operation-on-business-services-with-siebel.md)