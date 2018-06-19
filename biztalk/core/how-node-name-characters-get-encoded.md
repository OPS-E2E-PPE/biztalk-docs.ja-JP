---
title: ノード名における文字エン コードのどの |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6462856b-7a52-40c9-9aff-c0579130eec9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d2c9410e56b2b50a32ec73ce5f49ae59909f59a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247002"
---
# <a name="how-node-name-characters-get-encoded"></a>ノード名の文字エンコードの方法
ノード名で許可されていない文字を使用する場合は、BizTalk エディターが表示されたら、使用できない文字またはエンコード文字を続行するかどうかたずねる (**OK**または**キャンセル**)。 続行した場合 ([OK] をクリック)、禁止文字がそれぞれ次のようにエンコードされます。  
  
-   として使用できない文字がエンコードされます"_xDDDD\_"、"DDDD"は、文字の 4 桁の 16 進 Unicode 表現します。 たとえば、スペース (0x0020) としてエンコード"_x0020\_"です。  
  
-   複数の隣接する禁止文字がエンコードされる場合、文字間にアンダースコア文字が 1 つ挿入されます。 たとえば、3 つのスペースとしてエンコード"_x0020_x0020_x0020\_"ではなく"_x0020\__x0020\__x0020\_"です。  
  
> [!NOTE]
>  ノード名のエンコードを設定して要求するプロンプトを無効にする、**エンコード警告ダイアログの表示**プロパティを**False**の BizTalk エディター フォルダーで、**オプション** ダイアログ ボックス使用できる、**ツール** メニューの または を選択して、**今後このダイアログ ボックスを表示しない**ノード名のエンコード ダイアログ ボックスのチェック ボックスです。 このダイアログ ボックスでオプションの詳細については、次を参照してください。[スキーマ ツリー ビューの管理](../core/how-to-manage-the-schema-tree-view.md)です。  
  
 BizTalk エディターのスキーマ ツリー ビューには、入力された文字を使ってノード名が表示されます。 また、BizTalk マッパーでも、エンコード後の文字ではなく、入力された文字がそのまま表示されます。 BizTalk エディターの XSD ビュー、および XSD ファイル自体には、エンコードされたノード名が使用されます。 たとえば、ノード名として「Purchase Order」を入力した場合、BizTalk エディターおよび BizTalk マッパーのスキーマ ツリーには "Purchase Order" と表示されます。 BizTalk エディターの XSD ビューでは、対応する要素ノードが (最初に挿入されたときに) 次のように表示されます。  
  
```  
<element name="Purchase_x0020_Order" type="xs:string />  
  
```  
  
## <a name="see-also"></a>参照  
 [ノード名プロパティ](../core/node-name-property.md)   
 [ノード名における文字エン コードします。](../core/which-node-name-characters-get-encoded.md)