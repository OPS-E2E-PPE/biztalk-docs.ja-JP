---
title: ノード名における文字エン コードの方法 |Microsoft Docs
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
ms.openlocfilehash: 9f374f9ebdfabfff1cc123fe2ad2f9d05a2b3c63
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994059"
---
# <a name="how-node-name-characters-get-encoded"></a>ノード名の文字エンコードの方法
BizTalk エディターが使用できない文字またはエンコードされた文字を続行するかを確認するように求められますノード名で許可されていない文字を使用する場合 (**OK**または**キャンセル**)。 続行した場合 ([OK] をクリック)、禁止文字がそれぞれ次のようにエンコードされます。  
  
- 許可されない文字としてエンコードされます"*xDDDD\\*"ここ"DDDD"には、文字の 4 桁の 16 進数 Unicode 表現。 たとえば、スペース (0x0020) としてエンコード"*x0020\\*"。  
  
- 複数の隣接する禁止文字がエンコードされる場合、文字間にアンダースコア文字が 1 つ挿入されます。 たとえば、3 つのスペースとしてエンコード"*x0020_x0020_x0020\\*「なく」*x0020\__x0020\__x0020\\*"。  
  
> [!NOTE]
>  設定してノード名のエンコードのプロンプトを無効にした、**エンコード警告ダイアログを表示する**プロパティを**False**の BizTalk エディター フォルダーで、**オプション**ダイアログ ボックスで、使用できる、**ツール**メニュー、またはを選択して、 **、今後このダイアログ ボックスを表示しない**ノード名のエンコード ダイアログ ボックスのチェック ボックス。 このダイアログ ボックスでオプションの詳細については、次を参照してください。[スキーマ ツリー ビューの管理](../core/how-to-manage-the-schema-tree-view.md)します。  
  
 BizTalk エディターのスキーマ ツリー ビューには、入力された文字を使ってノード名が表示されます。 また、BizTalk マッパーでも、エンコード後の文字ではなく、入力された文字がそのまま表示されます。 BizTalk エディターの XSD ビュー、および XSD ファイル自体には、エンコードされたノード名が使用されます。 たとえば、ノード名として「Purchase Order」を入力した場合、BizTalk エディターおよび BizTalk マッパーのスキーマ ツリーには "Purchase Order" と表示されます。 BizTalk エディターの XSD ビューでは、対応する要素ノードが (最初に挿入されたときに) 次のように表示されます。  
  
```  
<element name="Purchase_x0020_Order" type="xs:string />  
  
```  
  
## <a name="see-also"></a>参照  
 [ノード名プロパティ](../core/node-name-property.md)   
 [ノード名における文字エンコード](../core/which-node-name-characters-get-encoded.md)