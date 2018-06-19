---
title: XSD 要素グループ |Microsoft ドキュメント
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
ms.openlocfilehash: b850841819ce844a10e407827d02993ce3559bad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289538"
---
# <a name="xsd-element-groups"></a>XSD 要素グループ
スキーマに特定の構造を使用すると、BizTalk マッパーで生成される XSLT (Extensible Stylesheet Language Transformations) にバリエーションが生じる場合があります。  
  
 その一例として、シーケンス、選択肢、または全要素グループを定義するスキーマをマップに含めるような場合が考えられます。 含むスキーマを使用する場合など、**選択肢グループ** ノードの子の 2 つ以上が必要なマップを作成するための可能性が、**選択肢グループ**ノードに表示される出力インスタンスメッセージ。 この場合、マップをコンパイルするときに、BizTalk マッパーから警告が表示されます。 この警告は、実行時の親ループにおける同一の繰り返し処理では、マッピングされた必須フィールドのいずれか 1 つしか、値が挿入されない可能性があることを伝えるものです。 BizTalk マッパーでは、マッピングのロジックに誤りがあることを示すエラー メッセージは生成されません。  
  
 他にも、次の条件が満たされた場合、XSLT にバリエーションが生じる可能性があります。  
  
-   **レコード A**子を持つ**フィールド要素 B**です。  
  
-   **レコード A**と子**フィールド要素 B** 1 回発生します。  
  
-   **レコード A**の一部である、**選択肢グループ**を繰り返します。  
  
 このような場合、BizTalk マッパーは、送信元レコードの複数のバリエーションを処理するための繰り返しロジックを含んだ XSLT を生成します。  
  
> [!NOTE]
>  グループを含んだマッピングは、明示的に指定する必要があります。 たとえば、送信先スキーマが含まれている場合、**グループの選択**子ノード A と B を持つノードが正しくない A に a と B は、その親グループの同一の繰り返し処理で同時に実行します。 BizTalk マッパーには、無効なマッピングの作成を回避するような機能はありません。 そのため、A と B が同時に現れることのできないような論理 Functoid を使用して、マッピングを設定する必要があります。  
  
## <a name="see-also"></a>参照  
 [マップ](../core/maps.md)   
 [BizTalk マッパーを使用してマップを作成します。](../core/creating-maps-using-biztalk-mapper.md)