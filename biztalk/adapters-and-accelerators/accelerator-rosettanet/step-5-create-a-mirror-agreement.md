---
title: 手順 5:ミラー アグリーメントの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, mirror agreements
- loopback tutorial, creating mirror agreements
- agreements, mirror agreements
ms.assetid: 6aa70b1e-7d38-49f7-9d5f-f008cbe3df66
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79cc7fb9d8eb54e45f2e4e86b36b12017ebf3c57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280903"
---
# <a name="step-5-create-a-mirror-agreement"></a>手順 5:ミラー アグリーメントを作成します。
この手順では、Loopback ユーティリティを使用して、ホーム組織が構成されている同じコンピューター上で取引をシミュレートするミラー アグリーメントを作成します。 Loopback ユーティリティは、コマンド ライン ツールです。  
  
### <a name="to-create-a-mirror-agreement-using-the-loopback-utility"></a>Loopback ユーティリティを使用してミラー アグリーメントを作成するには  
  
1. をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
2. コマンド プロンプトに移動します。 \<*ドライブ*\>: \Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk します。 次のコマンドを入力し、キーを押します**Enter**:  
  
   ```  
   Loopback /enable HOME  
   ```  
  
3. 手順 2 で実行されるコマンドが完了すると、コマンド プロンプトで次のコマンドを入力し、キーを押します**Enter**:  
  
   ```  
   Loopback /mirror "Trade Agreement"   
   ```  
  
   Loopback ユーティリティは、ホーム組織 (開始側) の送信ポートと取引先組織のミラー取引アグリーメントを自動的に作成します。 パートナーは、2 つの新しいホーム組織との通信にポートを送信します。  
  
> [!NOTE]
>  元の取引アグリーメントを更新するたびに再、取引先アグリーメントをミラー化する必要があります。  
  
## <a name="see-also"></a>参照  
 [手順 6:オーケストレーションの開始](../../adapters-and-accelerators/accelerator-rosettanet/step-6-start-orchestrations.md)
