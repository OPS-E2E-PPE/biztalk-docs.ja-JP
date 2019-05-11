---
title: 展開とプログラムで、新しいバージョンのオーケストレーションの開始 |Microsoft Docs
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
ms.openlocfilehash: b2398fbbfce73637d8c9cc3607c1fc5c82c1e0f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389605"
---
# <a name="deploying-and-starting-a-new-version-of-an-orchestration-programmatically"></a>展開とプログラムで、新しいバージョンのオーケストレーションを開始
このトピックのコードは、迅速にデプロイして、新しいバージョンのオーケストレーションを開始する方法を示しています。 手動操作を実行する時間がかかることができます、ため、手動でオーケストレーションを参加解除し、その新しいバージョンを起動により保留や重複メッセージ。 このトピックで示されているプログラムのメソッドでは、これらの操作をはるかに速く実行する 1 つの操作が失敗した場合、両方のオーケストレーションのままにできるように、保留や重複メッセージの単一のトランザクションとしての可能性を減らすこと、同じ状態の開始時と同様にします。  
  
> [!NOTE]
>  まれなケースでを新しいバージョンを更新するオーケストレーションが高負荷の下で動作しているときにいくつかのメッセージできます中断の参加を解除して、プログラムによって、オーケストレーションを参加させる場合でもです。  これらの操作を実行した後、保留中のメッセージ キューを確認している保留メッセージを再開をお勧めします。  
  
 次のコード サンプルは、エクスプ ローラー OM API を使用して、既存のオーケストレーションの参加を解除し、新しいバージョンのオーケストレーションを開始する方法を示しています。  
  
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