---
title: 展開とプログラムで新しいバージョンのオーケストレーションを開始 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f90025ec-3641-49ef-8918-88238d6ad420
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26887b70a09d4a7af8d41a4385dffda20e964690
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239026"
---
# <a name="deploying-and-starting-a-new-version-of-an-orchestration-programmatically"></a>プログラムによるオーケストレーションの新しいバージョンの展開と開始
このトピックのコードは、オーケストレーションの新しいバージョンをすばやく展開して開始する方法を示しています。 手動操作の実行には数秒かかることがあるため、手動でオーケストレーションの参加を解除してからそのオーケストレーションの新しいバージョンを開始すると、メッセージの保留や重複が発生する可能性があります。 このような操作は、このトピックで説明するようにプログラムで実行するとはるかに速く実行でき、メッセージの保留や重複の可能性が減ります。また、単一のトランザクションとして実行できるため、1 つの操作が失敗しても両方のオーケストレーションを開始時と同じ状態に保つことができます。  
  
> [!NOTE]
>  まれに、更新するオーケストレーションが新しいバージョンでは、負荷の高いオペレーティングいくつかのメッセージできますになる中断参加解除され、プログラムによって、オーケストレーションを参加させる場合でもされます。  これらの操作を実行した後、中断されたメッセージ キューを確認してする保留メッセージを再開ことをお勧めします。  
  
 以下のコード サンプルでは、エクスプローラー OM API を使用して、既存のオーケストレーションの参加を解除し、新しいバージョンのオーケストレーションを開始する方法を示します。  
  
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
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)   
 [オーケストレーションを参加させる方法](../core/how-to-enlist-an-orchestration.md)   
 [オーケストレーションを参加解除する方法](../core/how-to-unenlist-an-orchestration.md)