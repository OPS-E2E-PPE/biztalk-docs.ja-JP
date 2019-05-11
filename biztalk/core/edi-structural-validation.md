---
title: EDI 構造検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87086614-5616-441d-915c-2979c63c6e2f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 422449a9720b78a65b4934fbf17d255e84678613
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350223"
---
# <a name="edi-structural-validation"></a>EDI 構造検証
X12 と EDIFACT エンコードの両方の EDI 仕様では、特定の規則と EDI インターチェンジの構造に関する規則を定義します。 EDIReceivePipeline で EDI 逆アセンブラーは、各受信メッセージのエンベロープがこれらの構造上のルールに準拠しているかを確認します。 EDISendPipeline は、これらの規則に従って送信するには、各メッセージを作成し、送信する前に、エンベロープを検証します。  
  
 構造の検証では、必要なヘッダーとトレーラーが存在することを確認します。 セグメントとループの順序を含めるし、数がチェックされます構造的整合性を確認します。 これらのチェックは、ドキュメントの解析または正しくシリアル化することを確認して常に実行されます。 この検証が実行される場合でも、 **EDI 型の検証**や**Extended Validation**オプションが無効になります。 基本的な構造検証に失敗したインターチェンジは中断される場合でも、 **EDI 型の検証**や**Extended Validation**オプションが無効になります。  
  
 ヘッダーとトレーラー、内のデータ要素およびヘッダー/トレーラとデータ要素を区切る方法の値は、契約によって決定されます。 スキーマの検証によって検証されます。  
  
 エンベロープとヘッダーとトレーラーの各セット内の内容の詳細については、次を参照してください。 [EDI メッセージの構造](../core/edi-message-structure.md)します。  
  
## <a name="see-also"></a>参照  
 [EDI メッセージの検証](../core/edi-message-validation.md)