---
title: "EDI 構造検証 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87086614-5616-441d-915c-2979c63c6e2f
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 505b9ac55eff0b6adb249d11788308f03902f1d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="edi-structural-validation"></a>EDI 構造の検証
X12 エンコードと EDIFACT エンコードのどちらの EDI 仕様にも、EDI インターチェンジの構造に固有の規則と規約が定義されています。 EDIReceivePipeline で EDI 逆アセンブラーでは、各受信したメッセージのエンベロープがこれらの構造の規則に準拠していることを確認します。 EDISendPipeline は、送信する各メッセージをこれらの規則に基づいて構築し、送信前にエンベロープを検証します。  
  
 この構造検証では、必要なヘッダーとトレーラーが含まれているかどうかが確認されます。 構造的整合性チェックでは、セグメントとループの順序と数がチェックされます。 これらのチェックは、ドキュメントの解析またはシリアル化が正しく行われるようにするために、必ず実行されます。 この検証が実行される場合でも、 **EDI 型の検証**や**Extended Validation**オプションが無効になります。 基本的な構造検証に失敗したインターチェンジは中断される場合でも、 **EDI 型の検証**や**Extended Validation**オプションが無効になります。  
  
 ヘッダーとトレーラー内のデータ要素の値、およびヘッダー/トレーラーとデータ要素をどのように分離するかは、アグリーメントによって決定されます。 スキーマ検証によって検証されます。  
  
 エンベロープとヘッダーとトレーラーの各セット内の内容の詳細については、次を参照してください。 [EDI メッセージの構造体](../core/edi-message-structure.md)です。  
  
## <a name="see-also"></a>参照  
 [EDI メッセージの検証](../core/edi-message-validation.md)