---
title: "インポート エクスポートとビジネス ポリシーの展開スクリプトを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, policies
- business rules, deploying
- policies, deploying
- business rules, exporting
- RuleSetDeploymentDriver
- business rules, importing
- Business Rules Framework, policies
- Business Rules Framework, business rules
- Business Rules Framework, code samples
- deploying, business rules
- Business Rules Framework, programming
ms.assetid: 333d37dc-e0ee-460c-922d-70eedf7b7ccb
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fda67a54c63c8d1dd092e615b2057f00ad41bba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-script-import-export-and-deployment-of-business-policies"></a><span data-ttu-id="e1d07-102">インポート エクスポートとビジネス ポリシーの展開スクリプトを作成する方法</span><span class="sxs-lookup"><span data-stu-id="e1d07-102">How to Script Import-Export and Deployment of Business Policies</span></span>
<span data-ttu-id="e1d07-103">プログラムでインポート/エクスポートしを使用してポリシーを展開する方法について説明**RuleSetDeploymentDriver**です。</span><span class="sxs-lookup"><span data-stu-id="e1d07-103">This section describes how to programmatically import/export and deploy policies using **RuleSetDeploymentDriver**.</span></span>  
  
 <span data-ttu-id="e1d07-104">次の例は、ポリシーをファイルにエクスポートする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e1d07-104">The following example shows how to export a policy to a file.</span></span>  
  
```  
using System;  
using Microsoft.RuleEngine;  
using Microsoft.BizTalk.RuleEngineExtensions;  
namespace SimpleExport  
{  
   class ExportPolicy  
   {  
      [STAThread]  
      static void Main(string[] args)  
      {  
         if (args.Length != 3)  
            Console.WriteLine("Format: PolicyName MajorVersion MinorVersion");  
         else  
         {  
            string policyName = args[0];  
            int majorRev = Convert.ToInt16(args[1]);  
            int minorRev = Convert.ToInt16(args[2]);  
            RuleSetInfo rsi = new RuleSetInfo(policyName,majorRev,minorRev);  
            Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
            dd = new Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver();  
                        string fileName = (rsi.Name + "-" + rsi.MajorRevision + "." + rsi.MinorRevision + ".xml");  
            dd.ExportRuleSetToFileRuleStore(rsi,fileName);  
         }  
      }  
   }  
}  
```  
  
 <span data-ttu-id="e1d07-105">次の例は、ファイルからポリシーをインポートおよび展開する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e1d07-105">The following example shows how you can import and deploy a policy from a file.</span></span>  
  
```  
using System;  
using Microsoft.RuleEngine;  
using Microsoft.BizTalk.RuleEngineExtensions;  
namespace SimpleImport  
{  
   class ImportPolicy  
   {  
      [STAThread]  
      static void Main(string[] args)  
      {  
         String filename = args[0];  
         Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
         dd = new Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver();  
         SqlRuleStore sqlRuleStore = (SqlRuleStore) dd.GetRuleStore();  
         FileRuleStore fileRuleStore = new FileRuleStore(filename);  
         RuleSetInfoCollection rsic = fileRuleStore.GetRuleSets(RuleStore.Filter.All);  
         foreach (RuleSetInfo rsi in rsic)  
         {  
            RuleSet ruleSet = fileRuleStore.GetRuleSet(rsi);  
            bool publishRuleSets = true;  
            sqlRuleStore.Add(ruleSet,publishRuleSets);  
            dd.Deploy(rsi);  
         }  
      }  
   }  
}    
```  
  
> [!NOTE]
>  <span data-ttu-id="e1d07-106">このコードは、ボキャブラリの依存関係がないことを前提としています。ポリシーがボキャブラリを使用する場合、最初にボキャブラリをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1d07-106">The code assumes no dependencies on vocabularies; if the policy uses vocabularies they must be imported first.</span></span>