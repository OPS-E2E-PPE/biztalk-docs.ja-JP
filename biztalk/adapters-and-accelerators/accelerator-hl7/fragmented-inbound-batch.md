---
title: 受信バッチを断片化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, fragmenting messages
- messages, fragmenting
- fragmenting messages
ms.assetid: 5844710e-f662-48a3-bf1a-bc1ba91e678a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac8e0d99bfa9ea8696a7cd9f6eeed8a6be16006d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267817"
---
# <a name="fragmented-inbound-batch"></a>断片化した受信バッチ
構成できる[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]メッセージ バッチを受信する、バッチからのメッセージを抽出し、送信先システムに、個々 のメッセージをルーティングします。 受信のバッチが個別のメッセージにフラグメントの断片化を有効にした場合それ以外の場合、バッチが処理され、1 つのバッチまたはインターチェンジとしてルーティングします。 バッチ処理を有効にするのにには、BTAHL7 構成エクスプ ローラーを使用します。 バッチ処理を有効にする方法の詳細については、次を参照してください。[バッチ処理構成](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)します。  
  
 一般的な断片化した受信バッチのシナリオを次に示します。  
  
1.  システム A で実行されている、基幹業務アプリケーションでは、BTAHL7 をメッセージのバッチを送信します。  
  
     バッチのメッセージは、2 つの異なる形式で指定できます。 BTAHL7 では、次の形式を処理できます。  
  
    -   形式 1:1 つのファイルのヘッダーとトレーラー (FHS/FTS) の組み合わせと 1 つまたは複数バッチ ヘッダーとトレーラー (BHS/BTS) が含まれています。  
  
        ```  
        FHS  
        BHS  
        MSH  
        .............  
        MSH  
        ...........  
        BTS  
        BHS  
        MSH  
        ..............  
        MSH  
        ...............  
        BTS  
        FTS  
        ```  
  
    -   形式 2:HL7 の定義ファイルとバッチのラッパーが含まれていないと、一連の中断がストリーム内のメッセージ。  
  
        ```  
        MSH  
        .......  
        MSH  
        ........  
        MSH  
        .........  
        ```  
  
2.  BTAHL7 では、バッチから個々 のメッセージを作成し、適切なスキーマに対して、個々 のメッセージを確認します。  
  
3.  BTAHL7 では、バッチから抽出された各メッセージをシステム A に、個別の受信確認メッセージを送信します。  
  
4.  BTAHL7 では、メッセージ バッチのヘッダーではなく、個々 のメッセージのルーティング情報に基づいて、送信先システムに、個々 のメッセージをルーティングします。  
  
    > [!NOTE]
    >  BTAHL7 がバッチとファイルのヘッダー/トレーラーを検証していないときに、 **FHS3**フィールド (送信元パーティ) を持つ断片化が有効になっている取引先が含まれています。  
  
## <a name="see-also"></a>参照  
 [バッチ処理の構成](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)