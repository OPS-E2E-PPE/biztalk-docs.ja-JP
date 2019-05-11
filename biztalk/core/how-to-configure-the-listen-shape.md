---
title: 待ち受け図形を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Listen shape [Orchestration Designer], about Listen shape
- Listen shape [Orchestration Designer], configuring
- Listen shape [Orchestration Designer]
- Listen shape [Orchestration Designer], branching
- configuring [Orchestration Designer], Listen shapes
ms.assetid: 4765dc0a-a30e-4515-83bc-72b4f37268cf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55a717c45e5c40b4022c38d2b668cae4c615f248
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386051"
---
# <a name="how-to-configure-the-listen-shape"></a>待ち受け図形を構成する方法
待ち受けアクションを使用するアプリケーションのいずれか 1 つまたは複数のポートでのいくつかのメッセージを待機する、または指定されたタイムアウト間隔、および結果に基づいて分岐の後に待機を停止します。  
  
 ![](../core/media/ebiz-orch-listen.gif "ebiz_orch_listen")  
待ち受け図形  
  
 好きなように、多数の分岐を追加することができます。 初期の下の他の任意の図形を配置する**受信**または**遅延**図形。  
  
 ライセンス認証を使用することがで受信を**リッスン**図形。 場合の 1 つの分岐、**リッスン**図形には、アクティブ化が含まれているすべての分岐を含める必要がありますが、表示されるライセンス認証を受信して、タイムアウトは使用できません。 アクティブ化する必要がありますが表示される各分岐の最初のアクションがあります。  
  
 使用することができます、**リッスン**の 1 つまたは複数のイベントの発生に基づいてオーケストレーション フローを分岐図形。 各分岐の最初の図形はいずれかである必要があります、**遅延**または**受信**図形。 その条件を満たす最初の分岐 — のタイムアウトの発生を**遅延**図形または受信確認のメッセージの**受信**図形 — が実行されます。 必要な場合は、分岐を追加できます。  
  
### <a name="to-configure-a-listen-shape"></a>待ち受け図形を構成するには  
  
1.  ブランチを選択します。  
  
2.  プロパティ ウィンドウで、指定、**分岐の種類**プロパティ。  
  
     - または -  
  
     ドラッグ、**遅延**または**受信**図形を分岐にします。  
  
### <a name="to-add-a-branch-to-a-listen-shape"></a>待ち受け図形に分岐を追加するには  
  
-   右クリックし、**リッスン**図形をクリックして**新しい待ち受け分岐**します。  
  
    > [!NOTE]
    >  分岐を削除する、**リッスン**図形を削除するをクリックする分岐を右クリックして**削除**します。