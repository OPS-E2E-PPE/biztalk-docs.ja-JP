---
title: レコードおよびフィールドの順序 |Microsoft ドキュメント
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
ms.openlocfilehash: 5826d46fef73400a5d54e2d1154a1647af85294e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263858"
---
# <a name="order-of-records-and-fields"></a>レコードとフィールドの順序
BizTalk マッパーで使用する XSLT (Extensible Stylesheet Language Transformations) では、出力要素および属性の出力順が保証されません。 これは、BizTalk マッパーが XSLT を生成するときに、送信先スキーマ構造を調べてからグリッド ページをとおして要素を反映し、送信元スキーマ構造からの値を抽出するためです。 たとえば、BillTo Address レコードを ShipTo Address レコードの前にリストされるように出力を作成するには、送信先スキーマで BillTo Address を ShipTo Address レコードより前に配置する必要があります。  
  
> [!IMPORTANT]
>  出力インスタンス メッセージに要素および属性が表示される順序は、対応する送信先スキーマのレコードおよびフィールドの順序に依存します。  
  
## <a name="see-also"></a>参照  
 [マップ](../core/maps.md)   
 [BizTalk マッパーを使用してマップを作成します。](../core/creating-maps-using-biztalk-mapper.md)