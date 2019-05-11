---
title: 送信 EDI メッセージの検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 491303c0-b585-409e-a289-a2f6f9f82469
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01e0afed109f3ea03e863e2813ca4f58d289eaa0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295654"
---
# <a name="validation-of-outgoing-edi-messages"></a>送信 EDI メッセージの検証
EDI 送信パイプラインが送信されるメッセージを処理するとき、エンベロープとメッセージ データに対して一連の検証を実行します。 これらのプロセスの一部は常に実行します。一部は、それらを有効にした場合にのみ実行されます。 これらの検証を以下に示します。  
  
-   メッセージ スキーマと照らし合わせたトランザクション セット データ要素のスキーマの検証。 これは常に実行します。  
  
-   クロス フィールド検証トランザクションでは、データ要素 (X12 でエンコードされたメッセージのみ) を設定します。 これは、メッセージのスキーマで有効になっている場合に実行されます。  
  
-   トランザクション セット データ要素に対して EDI の検証が実行されます。 これは、アグリーメントでプロパティを有効にした場合に実行されます。  
  
-   トランザクション セット データ要素に対して実行される拡張検証。 これは、アグリーメントでプロパティを有効にした場合に実行されます。  
  
-   トランザクションの検証の設定グループのマッピングに x12 トランザクション セットに基づく単一グループ内の標準です。 これを行う場合にのみ、**受信バッチ処理オプション**プロパティに設定されて**インターチェンジの保存 - エラーでインターチェンジを中断**または**インターチェンジの保存 - トランザクションを中断エラーの設定**します。  
  
## <a name="see-also"></a>参照  
 [EDI 構造検証](../core/edi-structural-validation.md)   
 [アグリーメントのプロパティの検証](../core/agreement-properties-validation.md)   
 [EDI の種類 (データ要素) 検証](../core/edi-type-data-element-validation.md)   
 [拡張された (BTS-XSD) 検証](../core/extended-bts-xsd-validation.md)   
 [スキーマの検証](../core/schema-validation2.md)   
 [クロスフィールド/セグメント検証](../core/cross-field-segment-validation.md)