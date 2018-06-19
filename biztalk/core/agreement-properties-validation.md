---
title: アグリーメントのプロパティの検証 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d565c26-37ef-4aee-aebb-3152880242a1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20c01ec281005cbeaffda6dcd2349c1153a531b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22229874"
---
# <a name="agreement-properties-validation"></a>アグリーメントのプロパティの検証
アグリーメントのプロパティには、インターチェンジ、グループ、またはトランザクション セットの重複した制御番号のチェックが含まれます。 EDI 受信パイプラインは、アグリーメントのプロパティで有効になっている場合にのみ、それらの検証を実行します。 次のような検証が行われます。  
  
-   重複したインターチェンジ制御番号のチェック (X12 では ISA13、EDIFACT では UNB5)。 時間の値を日数で入力し、このチェックの有効な時間範囲を確立します。  
  
-   インターチェンジ内の重複したグループ制御番号のチェック (X12 では GS6、EDIFACT では UNB5)。  
  
-   機能グループ内の重複したトランザクション セット制御番号のチェック (X12 では ST2、EDIFACT では UNH1)  
  
## <a name="see-also"></a>参照  
 [EDI メッセージの検証](../core/edi-message-validation.md)