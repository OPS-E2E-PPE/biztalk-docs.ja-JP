---
title: "展開とプログラムで新しいバージョンのオーケストレーションを開始 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f90025ec-3641-49ef-8918-88238d6ad420
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26887b70a09d4a7af8d41a4385dffda20e964690
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-and-starting-a-new-version-of-an-orchestration-programmatically"></a><span data-ttu-id="5d03f-102">プログラムによるオーケストレーションの新しいバージョンの展開と開始</span><span class="sxs-lookup"><span data-stu-id="5d03f-102">Deploying and Starting a New Version of an Orchestration Programmatically</span></span>
<span data-ttu-id="5d03f-103">このトピックのコードは、オーケストレーションの新しいバージョンをすばやく展開して開始する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5d03f-103">The code in this topic illustrates how to quickly deploy and start a new version of the orchestration.</span></span> <span data-ttu-id="5d03f-104">手動操作の実行には数秒かかることがあるため、手動でオーケストレーションの参加を解除してからそのオーケストレーションの新しいバージョンを開始すると、メッセージの保留や重複が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5d03f-104">Because manual operations can take a few seconds to perform, manually unenlisting an orchestration and then starting a new version of it can result in suspended or duplicate messages.</span></span> <span data-ttu-id="5d03f-105">このような操作は、このトピックで説明するようにプログラムで実行するとはるかに速く実行でき、メッセージの保留や重複の可能性が減ります。また、単一のトランザクションとして実行できるため、1 つの操作が失敗しても両方のオーケストレーションを開始時と同じ状態に保つことができます。</span><span class="sxs-lookup"><span data-stu-id="5d03f-105">The programmatic method illustrated in this topic allows you to perform these operations much more quickly – reducing the likelihood of suspended and duplicate messages – and as a single transaction, so that if one operation fails, both orchestrations are left in the same state as they were at the beginning.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d03f-106">まれに、更新するオーケストレーションが新しいバージョンでは、負荷の高いオペレーティングいくつかのメッセージできますになる中断参加解除され、プログラムによって、オーケストレーションを参加させる場合でもされます。</span><span class="sxs-lookup"><span data-stu-id="5d03f-106">In rare cases, when the orchestration you are updating with a new version is operating under high load, some messages can become suspended even when you unenlist and enlist the orchestrations programmatically.</span></span>  <span data-ttu-id="5d03f-107">これらの操作を実行した後、中断されたメッセージ キューを確認してする保留メッセージを再開ことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5d03f-107">We recommend that after performing these operations, you check your suspended message queue and resume any suspended messages.</span></span>  
  
 <span data-ttu-id="5d03f-108">以下のコード サンプルでは、エクスプローラー OM API を使用して、既存のオーケストレーションの参加を解除し、新しいバージョンのオーケストレーションを開始する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5d03f-108">The following code sample illustrates how to use the Explorer OM API to unenlist an existing orchestration and start the new version of the orchestration.</span></span>  
  
```  
using System;  
using Microsoft.BizTalk.ExplorerOM;  
#endregion  
namespace OrchestrationBinding  
{  
class OrchestrationBinding  
{  
static void Main(string[] args)  
{  
            UpdateOrchestration();  
}  
        static public void UpdateOrchestration()  
        {  
            // Create the root object and set the connection string  
            BtsCatalogExplorer catalog = new BtsCatalogExplorer();  
            catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI";  
            string orchestrationAssemblyV1 = "HelloWorld, Version=1.0.0.0, Culture=neutral, PublicKeyToken=99561c477e487f14";  
            string orchestrationAssemblyV2 = "HelloWorld, Version=2.0.0.0, Culture=neutral, PublicKeyToken=99561c477e487f14";  
            string orchestrationName = "Microsoft.Samples.BizTalk.HelloWorld.HelloSchedule";  
            try  
            {  
                BtsAssembly assemblyV1 = FindAssemblyByFullName(catalog.Assemblies, orchestrationAssemblyV1);  
                BtsAssembly assemblyV2 = FindAssemblyByFullName(catalog.Assemblies, orchestrationAssemblyV2);  
                BtsOrchestration orchestrationV1 = assemblyV1.Orchestrations[orchestrationName];  
                BtsOrchestration orchestrationV2 = assemblyV2.Orchestrations[orchestrationName];  
                orchestrationV1.Status = OrchestrationStatus.Unenlisted;  
                orchestrationV2.Status = OrchestrationStatus.Started;  
                // Commit the accumulated changes transactionally  
                catalog.SaveChanges();  
            }  
            catch (Exception e)  
            {  
                catalog.DiscardChanges();  
                throw;  
            }  
        }  
        static BtsAssembly FindAssemblyByFullName(BtsAssemblyCollection assemblies, string fullName)  
        {  
            foreach (BtsAssembly assembly in assemblies)  
            {  
                if (assembly.DisplayName == fullName)  
                    return assembly;  
            }  
            return null;  
        }  
}  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="5d03f-109">参照</span><span class="sxs-lookup"><span data-stu-id="5d03f-109">See Also</span></span>  
 <span data-ttu-id="5d03f-110">[BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="5d03f-110">[Updating BizTalk Applications](../core/updating-biztalk-applications.md) </span></span>  
 <span data-ttu-id="5d03f-111">[オーケストレーションを参加させる方法](../core/how-to-enlist-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="5d03f-111">[How to Enlist an Orchestration](../core/how-to-enlist-an-orchestration.md) </span></span>  
 [<span data-ttu-id="5d03f-112">オーケストレーションを参加解除する方法</span><span class="sxs-lookup"><span data-stu-id="5d03f-112">How to Unenlist an Orchestration</span></span>](../core/how-to-unenlist-an-orchestration.md)