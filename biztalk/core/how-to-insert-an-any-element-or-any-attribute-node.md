---
title: すべての要素または属性の任意のノードを挿入する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4cbfdc04-6c83-4639-82de-169b6f009a2e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c00aa62a118b0da30deba77f7a4ceb2c1cc1cf7e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337097"
---
# <a name="how-to-insert-an-any-element-or-any-attribute-node"></a>すべての要素または属性の任意のノードを挿入する方法
BizTalk エディターでは、任意のノードの 2 つの種類をサポートします。**任意の要素**と**属性**します。 これらのノードを使用すると、対応するインスタンス メッセージ内の場所を不明な表示がある要素または属性に対応する、スキーマ内の場所を作成できます。 これらのノードを解釈する方法の詳細については、インスタンス メッセージを処理するときは、Web 上の XML スキーマ定義 (XSD) 言語に関する情報を直接参照してください。 この情報へのリンクを参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)します。  

## <a name="insert-an-any-element-node-or-an-any-attribute-node"></a>Any 要素ノードまたはすべての属性ノードを挿入します。  

1.  スキーマ ツリー ビューで、選択、**レコード**ノードを挿入する、 **Any 要素**ノードまたは**すべての属性**ノード。  

2.  **BizTalk**メニューで、**スキーマ ノードの挿入**、順にクリックします**Any 要素**または**すべての属性**必要に応じて、します。  

> [!IMPORTANT]
>  設定、 **Process Contents**プロパティを**Lax**の**Any 要素**または**すべての属性**ノードが正常に動作しない可能性があります。 検証に合格する**Any 要素**または**すべての属性**ノードにプロパティを設定する**スキップ**します。  このプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
> 
>  含むマップを作成する**Any 要素**または**すべての属性**ノード、いずれかを使用する必要があります、[一括コピー](mass-copy-functoid.md) functoid、または[Scripting](scripting-functoid.md)(インライン XSLT またはインライン XSLT 呼び出しテンプレートで) 使用する functoid をこのようなノードのマッピングを実行または単にそれらのノードをマップできません。  

## <a name="see-also"></a>参照  
- [スキーマへのノードの挿入](../core/inserting-nodes-into-a-schema.md)
- **Functoid のリファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
