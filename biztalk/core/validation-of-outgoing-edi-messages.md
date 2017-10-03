---
title: "送信 EDI メッセージの検証 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 491303c0-b585-409e-a289-a2f6f9f82469
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 946e90eb58c9b81e0cd7fa9bf2c02cc49af021ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="validation-of-outgoing-edi-messages"></a>送信 EDI メッセージの検証
EDI 送信パイプラインは、送信対象のメッセージを処理するとき、エンベロープとメッセージ データに対して一連の検証を実行します。 これらの処理のうちの一部は常に実行されますが、有効にした場合にのみ実行される処理もあります。 これらの検証には、以下が含まれます。  
  
-   トランザクション セットのデータ要素のメッセージ スキーマに対するスキーマ検証。 これは常に実行されます。  
  
-   トランザクション セットのデータ要素に対するクロスフィールド検証 (X12 でエンコードされたメッセージのみ)。 これは、メッセージ スキーマで有効になっている場合に実行されます。  
  
-   トランザクション セットのデータ要素に対して実行される EDI 検証。 これは、ような状況は、アグリーメントでプロパティが有効な場合に実行されます。  
  
-   トランザクション セットのデータ要素に対して実行される拡張検証。 これは、ような状況は、アグリーメントでプロパティが有効な場合に実行されます。  
  
-   X12 標準に準拠した、トランザクション セットとグループのマッピングに基づく、単一のグループ内のトランザクション セットの検証。 これは、実行される場合にのみ、**受信バッチ処理オプション**プロパティに設定されている**インターチェンジの保存 - エラーでインターチェンジを中断**または**インターチェンジのトランザクションを中断エラーの設定**です。  
  
## <a name="see-also"></a>参照  
 [EDI 構造検証](../core/edi-structural-validation.md)   
 [アグリーメントのプロパティの検証](../core/agreement-properties-validation.md)   
 [EDI の種類 (データ要素) の検証](../core/edi-type-data-element-validation.md)   
 [拡張 (BTS-XSD) 検証](../core/extended-bts-xsd-validation.md)   
 [スキーマの検証](../core/schema-validation2.md)   
 [クロス フィールド セグメント検証](../core/cross-field-segment-validation.md)