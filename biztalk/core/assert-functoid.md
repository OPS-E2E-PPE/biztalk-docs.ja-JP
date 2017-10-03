---
title: "アサート Functoid |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e91dac06-f909-4fb2-8c87-828a3dfe2c27
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03237c27e0e35642be197b549c8b0102d9350702
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="assert-functoid"></a>アサート Functoid

## <a name="overview"></a>概要
**Assert** functoid か、文字列値を出力するか、ブール値に基づく例外をスローします。 この functoid を 1 つ以上のとを組み合わせる場合、**論理**functoid をマップには、条件に関する仮定を効率的にテストできます。 たとえば、発注量が特定のしきい値を超えないものと想定するマップがあれば、テストできます発注値を使用して、**より大きい**functoid に接続し、 **Assert**functoid です。 論理演算 functoid を返す場合**True**、 **Assert** functoid が指定した文字列を使用して例外がスローされます。  
  
 ![アサート Functoid](../core/media/assertfunctoid.gif "AssertFunctoid")  
  
## <a name="see-also"></a>参照  
 **アサート Functoid リファレンス**と**論理演算 Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]