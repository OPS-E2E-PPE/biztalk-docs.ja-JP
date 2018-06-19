---
title: 受信した EDI メッセージの検証 |Microsoft ドキュメント
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
ms.openlocfilehash: dcc48b343332ea6b402841ec5ed1f5c9af49b2dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288058"
---
# <a name="validation-of-received-edi-messages"></a>受信した EDI メッセージの検証
EDI 受信パイプラインは、受信メッセージを処理するとき、エンベロープとメッセージ データに対して一連の検証を実行します。 これらの処理のうちの一部は常に実行されますが、有効にした場合にのみ実行される処理もあります。 これらの検証には、以下が含まれます。  
  
-   **常に実行される検証は**:  
  
    -   インターチェンジ エンベロープの構造の検証。  
  
    -   取引先アグリーメント (アグリーメントが定義されていない場合はフォールバック アグリーメント) に対するエンベロープの検証。  
  
    -   制御スキーマに対するエンベロープのスキーマ検証。  
  
    -   トランザクション セットのデータ要素のメッセージ スキーマに対するスキーマ検証。  
  
    -   X12 標準によって提供されるトランザクション セットとグループのマッピングに基づく単一グループ内のトランザクション セットの種類の検証。  
  
-   **有効になっている場合にのみ実行される検証は**:  
  
    -   トランザクション セットのデータ要素に対して実行される EDI 検証。 これは、アグリーメントのプロパティで有効になっている場合に実行されます。  
  
    -   トランザクション セットのデータ要素に対して実行される拡張検証。 これは、アグリーメントのプロパティで有効になっている場合に実行されます。  
  
    -   トランザクション セットのデータ要素に対するクロスフィールド検証 (X12 でエンコードされたメッセージのみ)。 これは、ような状況は、メッセージのスキーマで有効になっている場合に実行されます。  
  
## <a name="see-also"></a>参照  
 [EDI 構造検証](../core/edi-structural-validation.md)   
 [アグリーメントのプロパティの検証](../core/agreement-properties-validation.md)   
 [EDI の種類 (データ要素) の検証](../core/edi-type-data-element-validation.md)   
 [拡張 (BTS-XSD) 検証](../core/extended-bts-xsd-validation.md)   
 [スキーマの検証](../core/schema-validation2.md)   
 [クロス フィールド セグメント検証](../core/cross-field-segment-validation.md)