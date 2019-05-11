---
title: アサート Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e91dac06-f909-4fb2-8c87-828a3dfe2c27
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e3f14c05d1d4fd6538c126659c27cdb8b25fe08
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530632"
---
# <a name="assert-functoid"></a>アサート Functoid

## <a name="overview"></a>概要
**Assert** functoid が文字列値を出力またはブール値に基づいて例外をスローします。 この functoid を組み合わせた 1 つまたは複数の場合、**論理**functoid をマップには、条件に関する仮定を効果的にテストできます。 たとえば、特定のしきい値を超えない発注書の金額を必要があるマップがあれば、テストできます発注値を使用して、**より大きい**functoid に接続し、 **Assert**functoid。 論理演算 functoid で返された場合**True**、 **Assert** functoid では、指定した文字列を使用して例外をスローします。  
  
 ![アサート Functoid](../core/media/assertfunctoid.gif "AssertFunctoid")  
  
## <a name="see-also"></a>参照  
 **アサート Functoid リファレンス**と**論理演算 Functoid のリファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]