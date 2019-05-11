---
title: XSD 要素グループ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XSLT, XSLT variations
- BizTalk Mapper, XSLT variations
- maps, groups
- Choice Group node
- XSD element groups
- XSLT, warnings
ms.assetid: a6ea22cb-6066-480e-8a2a-75fade3e5970
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2090d300259949b8d5e26f2fa48cc416beba3ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401543"
---
# <a name="xsd-element-groups"></a>XSD 要素グループ
スキーマ内の特定の構造の使用で、XSLT Extensible Stylesheet Language Transformations () BizTalk マッパーによって生成されるバリエーションを作成できます。  
  
 これは、シーケンス、choice、またはすべての要素グループを定義する、マップにスキーマを含める場合に発生します。 含むスキーマを使用する場合など、**グループの選択**ノードの子の 2 つ以上が必要なマップを作成することは、**グループの選択**ノードに表示される出力インスタンスメッセージ。 この場合、BizTalk マッパーでは、マップをコンパイルするときに警告が表示されます。 この警告は、マップして、必要なフィールドの 1 つだけが実行時に同じ親ループのイテレーションで設定することを指示します。 BizTalk マッパーは提供されませんが、マッピングのロジックが正しいことを示すエラー メッセージ。  
  
 別の状況では、XSLT にバリエーションを生成する可能性がありますは、次の条件が満たされたときに。  
  
- **レコード A**が子**フィールド要素 B**します。  
  
- **レコード A**と子**フィールド要素 B** 1 回出現します。  
  
- **レコード A**の一部である、**グループの選択**繰り返されています。  
  
  このような状況では、BizTalk マッパーは、基になるレコードの多くのバリエーションの可能性を処理するために反復処理ロジックを含む XSLT を生成します。  
  
> [!NOTE]
>  グループを含んだマッピング明示的に指定する必要があります。 たとえば、送信先スキーマが含まれている場合、**グループの選択**A と B の子ノードを持つノード、ことはできませんと、親グループの同一の繰り返し処理で同時に B。 BizTalk マッパーができない無効なマッピングを作成します。 そのため、論理演算 functoid を使用して、マッピングを A と B 決して発生する可能性が同時に設定する必要があります。  
  
## <a name="see-also"></a>参照  
 [マップ](../core/maps.md)   
 [BizTalk マッパーを使用してマップを作成します。](../core/creating-maps-using-biztalk-mapper.md)