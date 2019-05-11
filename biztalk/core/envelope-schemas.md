---
title: エンベロープ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af296c30-95dc-4fef-9aa3-bea2f2cd8caf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d4637bbe0fcfecea0bf4c6e134eb131935315c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349522"
---
# <a name="envelope-schemas"></a>エンベロープ スキーマ

## <a name="overview"></a>概要
すべてのビジネス ドキュメントの XML スキーマを作成する同じ方法では、エンベロープ スキーマを作成できます。 スキーマを作成するには、整形式の XML エンベロープ インスタンス メッセージから、またはドキュメント型定義 (DTD) または Xml-data reduced (XDR) エンベロープ スキーマ表現。 または、かどうかは、他のスキーマと組み合わせて、新しいスキーマを作成できます。 エンベロープ スキーマは一般にはるかに小さいため、ほとんどのビジネス ドキュメント スキーマよりも複雑な少なく新しいエンベロープ スキーマの作成は、通常、利用可能な方法です。  
  
 エンベロープ スキーマとしてスキーマを定義するには、設定する必要があります、**エンベロープ**のプロパティ、**スキーマ**ノード値に**はい**します。 エンベロープ スキーマを定義するときに、エンベロープをポイントする必要があります**ボディ XPath**のみを含む親ノードに、\<任意\>子要素。 XML アセンブラーのエンベロープを使用するためには、親ノードは、他の要素を含めないでください。  
  
 設定すると**エンベロープ**プロパティを**はい**、(メッセージの本文と呼ばれます)、XML インスタンス メッセージの実際のメッセージの内容が、ルート中のどこかに存在することを意味**レコード**で指定したとおり、このスキーマのノード、**ボディ XPath**そのノードのプロパティ。 そのため、さまざまな条件に基づいて追加のプロパティを設定することも必要があります。  
  
-   設定する必要があるエンベロープ スキーマの単一のルートにある場合、**ボディ XPath**そのルートのプロパティ。  
  
-   エンベロープ スキーマに複数のルートがある場合、**ルート参照**プロパティが設定されていない、設定する必要があります、**ボディ XPath**のすべてのルートのプロパティ。  
  
-   エンベロープ スキーマに複数のルートがある場合、**ルート参照**プロパティの設定は、設定する必要があります、**ボディ XPath**プロパティの対応するルート**レコード**ノード。 必要に応じて設定することができます、**ボディ XPath**残りのルートのプロパティ。  
  
-   エンベロープ スキーマにルートを 1 つまたは複数のルートの設定のかどうかに関係なく、 **[ルート参照**プロパティは必要ありません。  

これらのプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
## <a name="see-also"></a>参照  
 [さまざまな種類の BizTalk スキーマ](../core/different-types-of-biztalk-schemas.md)   
 [エンベロープ用スキーマの作成方法](../core/how-to-create-schemas-for-envelopes.md)