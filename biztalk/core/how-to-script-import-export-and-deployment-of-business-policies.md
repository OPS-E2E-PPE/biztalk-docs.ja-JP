---
title: インポート/エクスポートとビジネス ポリシーの展開を記述する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50358be7c04218321f76b56cb670d1b65f8c9477
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334851"
---
# <a name="how-to-script-import-export-and-deployment-of-business-policies"></a><span data-ttu-id="6c891-102">インポート/エクスポートとビジネス ポリシーの展開を記述する方法</span><span class="sxs-lookup"><span data-stu-id="6c891-102">How to Script Import-Export and Deployment of Business Policies</span></span>
<span data-ttu-id="6c891-103">このセクションは、プログラムでインポート/エクスポートしを使用してポリシーを展開する方法を説明します**RuleSetDeploymentDriver**します。</span><span class="sxs-lookup"><span data-stu-id="6c891-103">This section describes how to programmatically import/export and deploy policies using **RuleSetDeploymentDriver**.</span></span>  
  
 <span data-ttu-id="6c891-104">次の例では、ポリシーをファイルにエクスポートする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6c891-104">The following example shows how to export a policy to a file.</span></span>  
  
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
  
 <span data-ttu-id="6c891-105">次の例では、インポートし、ファイルからポリシーを展開する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6c891-105">The following example shows how you can import and deploy a policy from a file.</span></span>  
  
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
>  <span data-ttu-id="6c891-106">コードにボキャブラリ; への依存関係が前提としませんポリシーがボキャブラリを使用している場合最初にインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c891-106">The code assumes no dependencies on vocabularies; if the policy uses vocabularies they must be imported first.</span></span>