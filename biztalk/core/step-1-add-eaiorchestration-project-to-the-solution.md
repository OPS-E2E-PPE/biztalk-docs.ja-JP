---
title: 手順 1:EAIOrchestration プロジェクトをソリューションに追加します |。Microsoft Docs
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
ms.openlocfilehash: df384829c19f24b71bec1726a260f185ea583463
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392940"
---
# <a name="step-1-add-eaiorchestration-project-to-the-solution"></a>手順 1:EAIOrchestration プロジェクトをソリューションに追加します。
![手順 4 の 1](../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **所要時間:** 5 分  
  
 **目標:** この手順では、EAI ソリューションに 2 つ目のプロジェクトを追加します。 新しいプロジェクトにオーケストレーションを追加します。  
  
 **目的:** オーケストレーションの別のプロジェクトを作成します。 これは、機能は、1 つのソリューションで作業する複数の異なるユーザーがある場合に便利です。 このレッスンでは、ビジネス プロセスを自動化するのにには、新しいオーケストレーションを使用します。  
  
## <a name="prerequisites"></a>前提条件  
 このステップを開始する前に、以下の要件を確認してください。  
  
-   この手順を開始する前に行う必要があります[レッスン 1。スキーマおよびマップの定義](../core/lesson-1-define-schemas-and-a-map.md)します。  
  
## <a name="procedures"></a>手順  
 閉じた場合は、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]  ウィンドウで、Visual Studio プロジェクトを開く"には」の手順に従います[手順 2。在庫要求スキーマの作成](../core/step-2-create-the-inventory-request-schema.md)を開きます。  
  
#### <a name="to-add-another-project-to-your-solution"></a>別のプロジェクトをソリューションに追加するには  
  
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
  
     オーケストレーション デザイナーが開きます。 次の図は、オーケストレーション デザイナーに EAIProcess オーケストレーションを示します。  
  
     ![新しいオーケストレーション](../core/media/tut1-eaiprocess.gif "Tut1_EAIProcess")  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 この手順では、EAI ソリューションに 2 番目のプロジェクトを追加します。 新しいプロジェクトには、オーケストレーションを追加します。  
  
## <a name="next-steps"></a>次の手順  
 ビジネス プロセスを定義した[手順 2。ビジネス プロセスの定義](../core/step-2-define-the-business-process.md)します。  
  
## <a name="see-also"></a>参照  
 [手順 2:ビジネス プロセスを定義します。](../core/step-2-define-the-business-process.md)   
 [ステップ 3:ポートをオーケストレーションに追加します。](../core/step-3-add-ports-to-the-orchestration.md)   
 [手順 4:EAIOrchestration プロジェクトをビルドします。](../core/step-4-build-the-eaiorchestration-project.md)