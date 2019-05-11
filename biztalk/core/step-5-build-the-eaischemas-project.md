---
title: 手順 5:EAISchemas プロジェクトのビルド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c20cd368-7446-4861-8d71-5bc25ce408a2
caps.latest.revision: 41
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b82d7b4d322464cb873e47e0e15e57c6f68f51d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244304"
---
# <a name="step-5-build-the-eaischemas-project"></a>手順 5:EAISchemas プロジェクトをビルドします。
![手順 5 の 5](../core/media/step-5of5.gif "Step_5of5")  
  
 **所要時間:** 6 分  
  
 **目標:** この手順では、EAISchemas プロジェクトをコンパイルします。  
  
 **目的:** Microsoft BizTalk Server と .NET Framework の最も重要な側面はすべての BizTalk Server アイテムです。マップやスキーマ、オーケストレーション、パイプライン、.NET アセンブリにコンパイルします。 この設計の 2 つの最も重要な意味は、これらのアセンブリが厳密な名前は、必要し、そのため、それらも .NET のバージョン管理の規則に従うことです。 これの主な影響は、別の .NET プロジェクトまたはアセンブリ (BizTalk プロジェクトを含む) の特定のバージョンに対して構築されると、BizTalk プロジェクトは、そのバージョンを使用して、新しいバージョンに対して再構築されるまでは引き続きです。  
  
## <a name="prerequisites"></a>前提条件  
 このステップを開始する前に、以下の要件を確認してください。  
  
-   この手順を開始する前に、次の手順を完了する必要があります。  
  
    -   [ステップ 1: EAISchemas プロジェクトを作成します。](../core/step-1-create-eaischemas-project.md)  
  
    -   [手順 2:在庫要求スキーマを作成します。](../core/step-2-create-the-inventory-request-schema.md) 
  
    -   [ステップ 3:要求拒否スキーマを作成します。](../core/step-3-create-the-request-decline-schema.md)  
  
    -   [手順 4:マップを作成します。](../core/step-4-create-the-map.md)  
  
## <a name="procedures"></a>手順  
  
#### <a name="to-build-the-eaischemas-project"></a>EAISchemas プロジェクトをビルドするには  
  
1.  ソリューション エクスプ ローラーで右クリックして**EAISchemas**、 をクリックし、**ビルド**します。  
  
     画面の下部に表示されます。  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ```  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 この手順では、アセンブリ ファイル (DLL) を生成する EAISchemas プロジェクトをビルドします。  
  
## <a name="next-steps"></a>次の手順  
 承認条件は、在庫補充要求メッセージの内容を評価するビジネス プロセスを作成する[レッスン 2。ビジネス プロセスの定義](../core/lesson-2-define-the-business-process.md)します。  
  
## <a name="see-also"></a>参照  
 [ステップ 1: EAISchemas プロジェクトを作成します。](../core/step-1-create-eaischemas-project.md)   
 [手順 2:在庫要求スキーマを作成します。](../core/step-2-create-the-inventory-request-schema.md)   
 [ステップ 3:要求拒否スキーマを作成します。](../core/step-3-create-the-request-decline-schema.md)   
 [手順 4:マップを作成します。](../core/step-4-create-the-map.md)