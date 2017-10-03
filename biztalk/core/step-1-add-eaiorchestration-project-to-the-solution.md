---
title: "手順 1: EAIOrchestration プロジェクトをソリューションに追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c9aa0d9-2075-4c7e-8baf-1ecd2721859a
caps.latest.revision: "42"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3b8e2b9c197e01ed695311c67bc79cf5056c4d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-add-eaiorchestration-project-to-the-solution"></a>ステップ 1: EAIOrchestration プロジェクトのソリューションへの追加
![4 のステップ 1](../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **所要時間:** 5 分  
  
 **目標:**ここでは、EAI ソリューションに 2 番目のプロジェクトを追加します。 新しいプロジェクトにオーケストレーションを追加します。  
  
 **目的:**オーケストレーションに別のプロジェクトを作成します。 これは、ソリューションの開発に複数のスタッフが携わっている場合に便利です。 このレッスンでは、新しいオーケストレーションを使用してビジネス プロセスを自動化します。  
  
## <a name="prerequisites"></a>前提条件  
 このステップを開始する前に、以下の要件を確認してください。  
  
-   この手順を開始する前に行う必要があります[レッスン 1: 定義のスキーマとマップ](../core/lesson-1-define-schemas-and-a-map.md)です。  
  
## <a name="procedures"></a>手順  
 閉じた場合は、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ウィンドウの Visual Studio プロジェクトを開く"には」の手順に従ってください[手順 2: 在庫要求スキーマの作成](../core/step-2-create-the-inventory-request-schema.md)を開きます。  
  
#### <a name="to-add-another-project-to-your-solution"></a>ソリューションに別のプロジェクトを追加するには、次の操作を行います。  
  
1.  Visual Studio から、上、**ファイル** メニューのをポイント**追加**、順にクリック**新しいプロジェクト**です。  
  
2.  **新しいプロジェクト** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**インストールされたテンプレート**|をクリックして**BizTalk プロジェクト**、クリックして**空の BizTalk Server プロジェクト**です。|  
    |**名前**|「`EAIOrchestration`.|  
    |**場所**|「`C:\BTSTutorials\EAISolution`.|  
  
3.  **[OK]**をクリックします。  
  
#### <a name="to-add-an-orchestration"></a>オーケストレーションを追加するには  
  
1.  ソリューション エクスプ ローラーで右クリック**EAIOrchestration**、 をポイント**追加**、クリックして**新しい項目の**します。  
  
2.  **新しい項目の追加 - EAIOrchestration**  ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**インストールされたテンプレート**|をクリックして**オーケストレーション ファイル**、クリックして**BizTalk オーケストレーション**です。|  
    |**名前**|型**EAIProcess.odx**です。|  
  
3.  **[追加]**をクリックします。  
  
     オーケストレーション デザイナーが開きます。 オーケストレーション デザイナーに EAIProcess オーケストレーションが表示されている状態を次に示します。  
  
     ![新しいオーケストレーション](../core/media/tut1-eaiprocess.gif "Tut1_EAIProcess")  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 このステップでは、EAI ソリューションに 2 番目のプロジェクトを追加します。 新しいプロジェクトにオーケストレーションを追加しました。  
  
## <a name="next-steps"></a>次の手順  
 ビジネス プロセスを定義した[手順 2: ビジネス プロセスの定義](../core/step-2-define-the-business-process.md)です。  
  
## <a name="see-also"></a>参照  
 [手順 2: ビジネス プロセスを定義します。](../core/step-2-define-the-business-process.md)   
 [手順 3: オーケストレーションのポートを追加します。](../core/step-3-add-ports-to-the-orchestration.md)   
 [手順 4: EAIOrchestration プロジェクトをビルドします。](../core/step-4-build-the-eaiorchestration-project.md)