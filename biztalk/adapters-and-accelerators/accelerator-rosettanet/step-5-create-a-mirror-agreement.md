---
title: "手順 5: ミラー アグリーメントの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, mirror agreements
- loopback tutorial, creating mirror agreements
- agreements, mirror agreements
ms.assetid: 6aa70b1e-7d38-49f7-9d5f-f008cbe3df66
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0ddb7c7dcad8bb278b318cdc599640b479baafa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-create-a-mirror-agreement"></a>手順 5: ミラー アグリーメントを作成します。
ここでは、ループバック ユーティリティを使用してミラー アグリーメントを作成します。このミラー アグリーメントは、ホーム組織を構成したコンピューターと同じコンピューターで取引先をシミュレートします。 ループバック ユーティリティは、コマンド ライン ツールです。  
  
### <a name="to-create-a-mirror-agreement-using-the-loopback-utility"></a>ループバック ユーティリティを使用してミラー アグリーメントを作成するには  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  コマンド プロンプトでに移動\<*ドライブ*>: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for rosettanet \sdk です。 次のコマンドを入力し、キーを押します**Enter**:  
  
    ```  
    Loopback /enable HOME  
    ```  
  
3.  手順 2 で実行されるコマンドが完了したら、コマンド プロンプトで次のコマンドを入力し、キーを押します**Enter**:  
  
    ```  
    Loopback /mirror "Trade Agreement"   
    ```  
  
 ループバック ユーティリティによって、ホーム組織 (開始側) 用の送信ポートと、取引先組織用のミラー取引アグリーメントが自動的に作成されます。 パートナーは、この 2 つの新しい送信ポートを使用して、ホーム組織と通信します。  
  
> [!NOTE]
>  元の取引アグリーメントを更新した場合は、その都度取引アグリーメントの再ミラーリングを行う必要があります。  
  
## <a name="see-also"></a>参照  
 [手順 6: オーケストレーションを開始します。](../../adapters-and-accelerators/accelerator-rosettanet/step-6-start-orchestrations.md)