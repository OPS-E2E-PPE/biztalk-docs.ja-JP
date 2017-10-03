---
title: "すべての要素または属性の任意のノードを挿入する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cbfdc04-6c83-4639-82de-169b6f009a2e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 913d7d0c68d61df1c457dd22500a9e4a8d90ec68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-insert-an-any-element-or-any-attribute-node"></a>すべての要素または属性の任意のノードを挿入する方法
BizTalk エディターには、すべてのノードの 2 種類がサポートしています: **Any 要素**と**すべての属性**です。 これらのノードを使用すると、インスタンス メッセージ内の特定の位置にどのような要素または属性が出現するかわからないときに、それらの要素や属性のための場所をスキーマ内で確保できます。 これらのノードがインスタンス メッセージの処理時にどのように解釈されるかについては、Web 上で XSD (XML Schema Definition) 言語に関する情報を参照してください。 この情報へのリンクを参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)です。  
  
## <a name="insert-an-any-element-node-or-an-any-attribute-node"></a>すべての要素ノードまたはすべての属性ノードを挿入します。  
  
1.  スキーマ ツリー ビューで、選択、**レコード**ノードを挿入する、 **Any 要素**ノードまたは**すべての属性**ノード。  
  
2.  **BizTalk**  メニューのをポイント**スキーマ ノードの挿入**、順にクリック**すべての要素**または**すべての属性** をクリックします。  
  
> [!IMPORTANT]
>  設定、 **Process Contents**プロパティを**Lax**の**Any 要素**または**すべての属性**ノードが正常に動作しない可能性があります。 検証に合格する**Any 要素**または**すべての属性**ノード、プロパティを設定します**Skip**です。  このプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
>
>  含むマップを作成する**Any 要素**または**すべての属性**ノード、いずれかを使用する必要があります、[一括コピー](mass-copy-functoid.md) functoid または[スクリプト](scripting-functoid.md)functoid (インライン XSLT またはインライン XSLT 呼び出しテンプレート) をこのようなノードのマッピングを実行または単にそれらのノードをマップされません。  
  
## <a name="see-also"></a>参照  
-  [スキーマにノードを挿入](../core/inserting-nodes-into-a-schema.md)
- **Functoid のリファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]