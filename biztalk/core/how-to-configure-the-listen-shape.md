---
title: 待ち受け図形を構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 5bd8f8bbcc08d41430b95a9d177aeb06a5288be4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247898"
---
# <a name="how-to-configure-the-listen-shape"></a>待ち受け図形を構成する方法
アプリケーションは、待ち受けアクションを実行して、1 つ以上のポートで複数のメッセージの 1 つを待機するか、指定されたタイムアウト間隔後に待機を停止して、結果に基づいて分岐することができます。  
  
 ![](../core/media/ebiz-orch-listen.gif "ebiz_orch_listen")  
待ち受け図形  
  
 好きなように、多数の分岐を追加することができます。 初期の下の他の任意の図形を配置する**受信**または**遅延**図形です。  
  
 アクティブ化を使用して行うことがで受信、**リッスン**図形です。 場合 1 つの分岐、**リッスン**図形にはアクティブ化が含まれていますが、すべての分岐を含める必要がありますのアクティブ化は、次の受信、およびタイムアウトは使用できません。 アクティベーション受信は、各分岐の最初のアクションである必要があります。  
  
 使用することができます、**リッスン**1 つまたは複数のイベントの発生に基づいてオーケストレーション フローの分岐に図形です。 各分岐の最初の図形はいずれかである必要があります、**遅延**または**受信**図形です。 その条件を満たす最初の分岐 — のタイムアウトの発生、**遅延**または図形のメッセージの受信、**受信**図形 — が実行されます。 必要に応じて分岐を追加できます。  
  
### <a name="to-configure-a-listen-shape"></a>待ち受け図形を構成するには  
  
1.  分岐を選択します。  
  
2.  [プロパティ] ウィンドウで指定、**分岐の種類**プロパティです。  
  
     - または -  
  
     ドラッグ、**遅延**または**受信**図形に分岐します。  
  
### <a name="to-add-a-branch-to-a-listen-shape"></a>待ち受け図形に分岐を追加するには  
  
-   右クリックし、**リッスン**図形をクリックして**新しい待ち受け分岐**です。  
  
    > [!NOTE]
    >  分岐を削除する、**リッスン**図形をクリックして、削除する分岐を右クリックして**削除**です。