---
title: ツールボックスに SWIFT パイプライン コンポーネントの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- toolbox, adding pipelines
- pipelines, adding to toolbox
ms.assetid: 3821c10e-ef9b-4657-b934-cff6d096f654
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4594b3ed3ca1c348a9d903217d165f8f9d2380d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378641"
---
# <a name="adding-swift-pipeline-components-to-the-toolbox"></a>ツールボックスに SWIFT パイプライン コンポーネントの追加
SWIFT パイプライン コンポーネントを追加する必要があります、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ツールボックス、これらのコンポーネントを使用してカスタムのパイプラインを作成できるようにします。 これは、Message Repair および New Submission または FIN Response Reconciliation のいずれかのパイプラインの作成に必要です。  
  
 **まとめ**  
  
 次の SWIFT パイプライン コンポーネントの追加、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ツールボックス。  
  
-   SWIFT アセンブラー (Message Repair および New Submission FIN Response Reconciliation (FRR) 用)  
  
-   (Message Repair および New Submission または FRR) 用に SWIFT 逆アセンブラー  
  
-   SWIFT Frr 相関関係の設定 (用として FRR) 競合回避モジュール  
  
-   SWIFT Frr MQSeries のデコーダー (用として FRR)  
  
-   SWIFT の Frr MQSeries の送信コンポーネント (用として FRR)  
  
### <a name="to-add-a4swift-pipeline-components-to-the-toolbox"></a>A4SWIFT パイプライン コンポーネントをツールボックスに追加するには  
  
1.  Visual Studio での**ツール**] メニューのをクリックして **[ツールボックス アイテムの**します。  
  
2.  **ツールボックス アイテムの選択** ダイアログ ボックスで、 **BizTalk パイプライン コンポーネント** タブで  **SWIFT アセンブラー**と**SWIFT 逆アセンブラー**. FIN Response Reconciliation を使用する場合は選択**SWIFT Frr 相関設定リゾルバー**、 **SWIFT Frr MQSeries デコーダー**、および**SWIFT Frr MQSeries の送信コンポーネント**します。  
  
3.  **[OK]** をクリックします。