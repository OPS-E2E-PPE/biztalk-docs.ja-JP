---
title: "受信バッチを断片化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, fragmenting messages
- messages, fragmenting
- fragmenting messages
ms.assetid: 5844710e-f662-48a3-bf1a-bc1ba91e678a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0807bbe83ea2f477a7e1625488ebbecf578f3adc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="fragmented-inbound-batch"></a>受信バッチの断片化
構成することができます[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]メッセージ バッチを受信するには、バッチからメッセージを抽出し、送信先システムに個々 のメッセージをルーティングします。 受信のバッチが個別のメッセージにフラグメントの断片化を有効にした場合それ以外の場合、バッチが処理され、1 つのバッチまたはインターチェンジとしてルーティングします。 バッチ処理を有効にするのにには、BTAHL7 構成エクスプ ローラーを使用します。 バッチ処理を有効にする方法の詳細については、次を参照してください。[バッチ処理構成](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)です。  
  
 次に、断片化された受信バッチを一般的なシナリオについて説明します。  
  
1.  A、システムで実行されている、基幹業務アプリケーションは、BTAHL7 をメッセージのバッチを送信します。  
  
     バッチのメッセージは、次の 2 つの異なる形式で指定できます。 BTAHL7 では、次の形式を処理できます。  
  
    -   形式 1:、1 つのファイルのヘッダーとトレーラー (FHS/FTS) の組み合わせと 1 つまたは複数バッチ ヘッダーとトレーラー (BHS/BTS) が含まれています。  
  
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
  
    -   形式 2: HL7 が定義されているファイルとバッチのラッパーが含まれていないと、一連の中断がストリーム内のメッセージ。  
  
        ```  
        MSH  
        .......  
        MSH  
        ........  
        MSH  
        .........  
        ```  
  
2.  BTAHL7 では、バッチから個々 のメッセージを作成し、適切なスキーマに対して個別のメッセージを確認します。  
  
3.  BTAHL7 では、バッチから抽出されたメッセージごとにシステムを別の受信確認メッセージを送信します。  
  
4.  BTAHL7 では、メッセージ バッチ ヘッダーではなく、個々 のメッセージのルーティング情報に基づいて、送信先システムに個々 のメッセージをルーティングします。  
  
    > [!NOTE]
    >  BTAHL7 では、バッチとファイルのヘッダー/トレーラーは検証されないときに、 **FHS3**フィールド (送信元パーティ) には、断片化が有効になっている取引先が含まれています。  
  
## <a name="see-also"></a>参照  
 [バッチ処理の構成](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)