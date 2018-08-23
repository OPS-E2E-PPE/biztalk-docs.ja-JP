---
title: '手順 1: EAIOrchestration プロジェクトをソリューションに追加する |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c9aa0d9-2075-4c7e-8baf-1ecd2721859a
caps.latest.revision: 42
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3b8e2b9c197e01ed695311c67bc79cf5056c4d1
ms.sourcegitcommit: 9b93ee2a019bef8d482626cf5525a6b95509b135
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2018
ms.locfileid: "22276866"
---
# <a name="step-1-add-eaiorchestration-project-to-the-solution"></a>ステップ 1: EAIOrchestration プロジェクトのソリューションへの追加
![手順 4 の 1](../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **所要時間:** 5 分  
  
 **目標:** では、EAI ソリューションに 2 つ目のプロジェクトを追加します。 新しいプロジェクトにオーケストレーションを追加します。  
  
 **目的:** オーケストレーション用に別のプロジェクトを作成します。 これは、ソリューションの開発に複数のスタッフが携わっている場合に便利です。 このレッスンでは、新しいオーケストレーションを使用してビジネス プロセスを自動化します。  
  
## <a name="prerequisites"></a>Prerequisites  
 このステップを開始する前に、以下の要件を確認してください。  
  
-   この手順を開始する前に行う必要があります[レッスン 1: スキーマの定義およびマップ](../core/lesson-1-define-schemas-and-a-map.md)します。  
  
## <a name="procedures"></a>手順  
 閉じた場合は、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ウィンドウでの Visual Studio プロジェクトを開く"には」の手順に従ってください[手順 2: 在庫要求スキーマの作成](../core/step-2-create-the-inventory-request-schema.md)を開きます。  
  
#### <a name="to-add-another-project-to-your-solution"></a>ソリューションに別のプロジェクトを追加するには、次の操作を行います。  
  
1.  Visual Studio からの**ファイル**メニューで、**追加**、順にクリックします**新しいプロジェクト**します。  
  
2.  **新しいプロジェクト** ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**インストール済みテンプレート**|クリックして**BizTalk プロジェクト**、 をクリックし、**空の BizTalk Server プロジェクト**します。|  
    |**名前**|「`EAIOrchestration`.|  
    |**場所**|「`C:\BTSTutorials\EAISolution`.|  
  
3.  **[OK]** をクリックします。  
  
#### <a name="to-add-an-orchestration"></a>オーケストレーションを追加するには  
  
1.  ソリューション エクスプ ローラーで右クリック**EAIOrchestration**、 をポイント**追加**、 をクリックし、**新しい項目の**します。  
  
2.  **新しい項目の追加 - EAIOrchestration**  ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**インストール済みテンプレート**|クリックして**オーケストレーション ファイル**、 をクリックし、 **BizTalk オーケストレーション**します。|  
    |**名前**|型**EAIProcess.odx**します。|  
  
3.  **[追加]** をクリックします。  
  
     オーケストレーション デザイナーが開きます。 オーケストレーション デザイナーに EAIProcess オーケストレーションが表示されている状態を次に示します。  
  
     ![新しいオーケストレーション](../core/media/tut1-eaiprocess.gif "Tut1_EAIProcess")  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 この手順では、EAI ソリューションに 2 番目のプロジェクトを追加します。 新しいプロジェクトにオーケストレーションを追加しました。  
  
## <a name="next-steps"></a>次の手順  
 ビジネス プロセスを定義した[手順 2: ビジネス プロセスの定義](../core/step-2-define-the-business-process.md)します。  
  
## <a name="see-also"></a>参照  
 [手順 2: ビジネス プロセスを定義します。](../core/step-2-define-the-business-process.md)   
 [手順 3: オーケストレーションのポートを追加します。](../core/step-3-add-ports-to-the-orchestration.md)   
 [手順 4: EAIOrchestration プロジェクトのビルド](../core/step-4-build-the-eaiorchestration-project.md)