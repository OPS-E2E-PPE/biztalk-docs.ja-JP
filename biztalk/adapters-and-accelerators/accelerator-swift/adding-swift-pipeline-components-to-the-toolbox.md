---
title: "SWIFT パイプライン コンポーネントをツールボックスに追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbox, adding pipelines
- pipelines, adding to toolbox
ms.assetid: 3821c10e-ef9b-4657-b934-cff6d096f654
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aaef345994a1d849e09025d9ad1bb0f133c1b224
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adding-swift-pipeline-components-to-the-toolbox"></a>SWIFT パイプライン コンポーネントをツールボックスに追加します。
SWIFT パイプライン コンポーネントを追加する必要があります、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ツールボックス、これらのコンポーネントを使用してカスタム パイプラインを作成できるようにします。 これは、Message Repair および New Submission または FIN 対応調整のいずれかのパイプラインを作成する必要があります。  
  
 **概要**  
  
 次の SWIFT パイプライン コンポーネントを追加、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ツールボックス。  
  
-   SWIFT アセンブラー (Message Repair および New Submission FIN 対応調整 (FRR) 用)  
  
-   SWIFT の逆アセンブラー (Message Repair および New Submission FRR 用)  
  
-   SWIFT Frr 相関関係の設定 (FRR) の競合回避モジュール  
  
-   SWIFT Frr MQSeries デコーダー (用 FRR)  
  
-   SWIFT Frr MQSeries 送信コンポーネント (FRR)  
  
### <a name="to-add-a4swift-pipeline-components-to-the-toolbox"></a>A4SWIFT パイプライン コンポーネントをツールボックスに追加するには  
  
1.  Visual Studio での**ツール** メニューのをクリックして**ツールボックス アイテムの選択**です。  
  
2.  **ツールボックス アイテムの選択** ダイアログ ボックスで、 **BizTalk パイプライン コンポーネント** タブで  **SWIFT アセンブラー**と**SWIFT 逆アセンブラー**. FIN 対応調整を使用する場合は、選択**SWIFT Frr 相関関係設定の競合回避モジュール**、 **SWIFT Frr MQSeries デコーダー**、および**SWIFT Frr MQSeries の送信コンポーネント**です。  
  
3.  **[OK]**をクリックします。