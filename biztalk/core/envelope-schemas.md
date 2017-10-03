---
title: "エンベロープ スキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af296c30-95dc-4fef-9aa3-bea2f2cd8caf
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03c44f1a5d9797ec09cc164789148287c98b4399
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="envelope-schemas"></a>エンベロープ スキーマ

## <a name="overview"></a>概要
エンベロープ スキーマは、ビジネス ドキュメントの XML スキーマを作成するときとまったく同じように作成できます。 スキーマは、整形式 XML のエンベロープ インスタンス メッセージから作成することも、ドキュメント型定義 (DTD) または XDR (XML-Data Reduced) 形式のエンベロープ スキーマから作成することもできます。 あるいは、他のスキーマと組み合わせて新しいスキーマを作成したり、まったく新しいスキーマを一から作成することもできます。 一般に、エンベロープ スキーマは、ビジネス ドキュメント スキーマよりも小規模かつ単純であるため、新しいエンベロープ スキーマを作成してもそれほど手間はかかりません。  
  
 エンベロープ スキーマとしてスキーマを定義するには、設定する必要があります、**エンベロープ**のプロパティ、**スキーマ**値ノード**はい**です。 エンベロープ スキーマを定義するときは、エンベロープをポイントする必要があります**ボディ XPath**のみを含む親ノードに、\<任意 > 子要素です。 親ノードに他の要素が含まれていると、XML アセンブラーがそのエンベロープを使用できなくなります。  
  
 設定すると**エンベロープ**プロパティを**はい**、(メッセージの本文と呼ばれます)、XML インスタンス メッセージの実際のメッセージの内容が、ルート内のどこかに存在することを意味**レコード**で指定したとおり、このスキーマのノード、**ボディ XPath**そのノードのプロパティです。 したがって、さまざまな条件に基づいて、追加のプロパティを設定する必要があります。  
  
-   設定する必要があります、エンベロープ スキーマに単一のルートがある場合、**ボディ XPath**そのルートのプロパティです。  
  
-   エンベロープ スキーマに複数のルートがある場合、**ルート参照**プロパティが設定されていない、設定する必要があります、**ボディ XPath**のすべてのルートのプロパティです。  
  
-   エンベロープ スキーマに複数のルートがある場合、**ルート参照**プロパティが設定されて、設定する必要があります、**ボディ XPath** 、対応するルートのプロパティ**レコード**ノード。 必要に応じて設定することができます、**ボディ XPath**残りのルートのプロパティです。  
  
-   エンベロープ スキーマが単一のルートまたは複数のルートの設定にあるかどうかに関係なく、 **[ルート参照**プロパティは必要ありません。  

これらのプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="see-also"></a>参照  
 [BizTalk スキーマの種類](../core/different-types-of-biztalk-schemas.md)   
 [エンベロープ用スキーマを作成する方法](../core/how-to-create-schemas-for-envelopes.md)