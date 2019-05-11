---
title: 受信した EDI メッセージの検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c56a3c0-042e-4611-8131-d51098064f0f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1af8946cf94747f74db25d1854d2157a36370cbc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292600"
---
# <a name="validation-of-received-edi-messages"></a>受信した EDI メッセージの検証
EDI 受信パイプライン、受信メッセージの処理、エンベロープとメッセージのデータに対して一連の検証を実行します。 これらのプロセスの一部は常に実行します。一部は、それらを有効にした場合にのみ実行されます。 これらの検証を以下に示します。  
  
-   **常に実行される検証は**:  
  
    -   インターチェンジのエンベロープの構造の検証。  
  
    -   取引パートナー契約 (またはアグリーメントが定義されていない場合はフォールバック アグリーメント) に対するエンベロープの検証。  
  
    -   制御スキーマと照らし合わせたエンベロープのスキーマの検証。  
  
    -   メッセージ スキーマと照らし合わせたトランザクション セット データ要素のスキーマの検証。  
  
    -   トランザクションに基づく単一グループ内のトランザクションの種類の検証の設定グループ マッピングは設定されている X12 で提供されている標準です。  
  
-   **有効になっている場合にのみ実行される検証は**:  
  
    -   トランザクション セット データ要素に対して EDI の検証が実行されます。 これは、アグリーメントのプロパティで有効になっている場合に実行されます。  
  
    -   トランザクション セット データ要素に対して実行される拡張検証。 これは、アグリーメントのプロパティで有効になっている場合に実行されます。  
  
    -   クロス フィールド検証トランザクションでは、データ要素 (X12 でエンコードされたメッセージのみ) を設定します。 これは、メッセージのスキーマで有効になっている場合に実行されます。  
  
## <a name="see-also"></a>参照  
 [EDI 構造検証](../core/edi-structural-validation.md)   
 [アグリーメントのプロパティの検証](../core/agreement-properties-validation.md)   
 [EDI の種類 (データ要素) 検証](../core/edi-type-data-element-validation.md)   
 [拡張された (BTS-XSD) 検証](../core/extended-bts-xsd-validation.md)   
 [スキーマの検証](../core/schema-validation2.md)   
 [クロスフィールド/セグメント検証](../core/cross-field-segment-validation.md)