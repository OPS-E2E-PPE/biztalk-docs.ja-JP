---
title: レコードとフィールドの順序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Mapper, sorting
- XSLT, sorting
ms.assetid: 7fa9b5cd-73bc-496f-a081-4a45da3afe42
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bd47208d772489b322d1f23c6b44d7ed552dee2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262612"
---
# <a name="order-of-records-and-fields"></a>レコードとフィールドの順序
BizTalk マッパーで使用する XSLT (Extensible Stylesheet Language Transformations) では、出力要素および属性の出力順が保証されません。 これは、BizTalk マッパーが XSLT を生成するときに、送信先スキーマ構造を調べてからグリッド ページをとおして要素を反映し、送信元スキーマ構造からの値を抽出するためです。 たとえば、BillTo Address レコードを ShipTo Address レコードの前にリストされるように出力を作成するには、送信先スキーマで BillTo Address を ShipTo Address レコードより前に配置する必要があります。  
  
> [!IMPORTANT]
>  出力インスタンス メッセージに要素および属性が表示される順序は、対応する送信先スキーマのレコードおよびフィールドの順序に依存します。  
  
## <a name="see-also"></a>参照  
 [マップ](../core/maps.md)   
 [BizTalk マッパーを使用してマップを作成します。](../core/creating-maps-using-biztalk-mapper.md)