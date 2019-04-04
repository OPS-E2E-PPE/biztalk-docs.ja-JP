---
title: レコードを自動的にリンクする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc2926c7-07c2-45d1-afde-d3f894f6b88d
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77d4c703a890398516ccbb9a9b4d1fafff22a8f5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018165"
---
# <a name="how-to-link-records-automatically"></a>レコードを自動的にリンクする方法
BizTalk マッパーでは、ショートカットを使用して、送信元スキーマと送信先スキーマの 2 つのレコード要素間のリンクを効率的に作成することができます。 このトピックでは、ショートカット メニューを使用してリンク操作を実行する方法について説明します。  
  
 レコード間のリンクは、次の方法で自動的に作成できます。  
  
- **直接リンクします。** この方法を使用すると、BizTalk マッパーは送信元スキーマのレコードを送信先スキーマの選択されたレコードにリンクします。  
  
- **構造によるリンク。** この手法を使用して、一致すると、BizTalk マッパー、**レコード**と**フィールド**内のノード、**レコード**それらの構造に従って、リンクされているノード**レコード**構造内の対応するノードの名前に関係なく、ノード。  
  
- **名前によるリンク。** この手法を使用して、一致すると、BizTalk マッパー、**レコード**と**フィールド**内のノード、**レコード**ノードの名前に従って、リンクする、内で、その構造に関係なく、ノードを対応する、**レコード**リンクされているノード。  
  
- **一括コピーします。** **一括コピー**により、マップが含まれるスキーマを使用して、functoid**任意**と**anyAttribute**要素。 BizTalk マッパーで使用できる functoid については、[Functoid 作成複雑なマッピングを使用した](../core/using-functoids-to-create-more-complex-mappings.md)を参照してください。  
  
  ショートカット メニューを使用するには、リンクがサブ階層親ノードから開始され、別のサブ階層親ノードで終了する必要があります。 ショートカット メニューを使用すると、2 つのスキーマ ノード間でどの種類のリンクを作成すべきかがわかります。 次に、ショートカット メニューで使用できるオプションの一覧を示します。  
  
|マップ元|マップ先|リンク動作|  
|--------------|------------|-------------------|  
|フィールド|フィールド|直接リンク|  
|レコード|フィールド|直接リンク|  
|フィールド|レコード|直接リンク|  
|レコード|レコード|ショートカット メニューが表示される|  
  
## <a name="prerequisites"></a>前提条件  
 これらの操作では、BizTalk マッパーが実行されている必要があります。  
  
### <a name="to-link-the-record-elements-directly"></a>レコード要素を直接リンクするには  
  
1.  ソース スキーマのサブ階層の親ノードからマウスをドラッグし、ターゲット スキーマのサブ階層の親ノードのところでドロップします。  
  
2.  ショートカット メニューで、**の直接リンク**します。 次の図に、選択した送信元ノードからターゲット ノードへの直接リンクを示します。  
  
     ![送信元ノードからターゲット ノードへの直接リンク](../core/media/linkrecordelements-directly.gif "Linkrecordelements_directly")  
  
    > [!IMPORTANT]
    >  直接リンクは、送信元スキーマのサブ階層親ノードからターゲット スキーマの非サブ階層親ノードに適用できます。 次の図に、送信元スキーマの親ノードである "Root" からターゲット スキーマの "Root" の子ノードである "Record1" への直接リンクを示します。  
  
     ![レコード要素の直接リンク](../core/media/linkrecordelements-directly2.gif "Linkrecordelements_directly2")  
  
### <a name="to-link-the-record-elements-by-structure"></a>レコード要素を構造によってリンクするには  
  
1.  ソース スキーマのサブ階層の親ノードからマウスをドラッグし、ターゲット スキーマのサブ階層の親ノードのところでドロップします。  
  
2.  ショートカット メニューで、**構造によるリンク**します。 BizTalk マッパーが一致する、**レコード**と**フィールド**内のノード、**レコード**ノードの構造に従って、リンクする**レコード**構造内の対応するノードの名前に関係なく、ノード。  
  
     ![レコード要素をリンク&#95;構造体によって](../core/media/linkrecordelements-bystructure.gif "Linkrecordelements_bystructure")  
  
    > [!IMPORTANT]
    >  送信元スキーマのサブ階層親ノードからターゲット スキーマの非サブ階層親ノードを、構造によってリンクすると、BizTalk マッパーは送信元の親ノードの子ノードをターゲットの親ノードの子ノードにそれぞれマップします。 次の図に、構造によるリンクを示します。  
  
     ![構造によるレコード要素のリンク](../core/media/linkrecordelements-bystructure2.gif "Linkrecordelements_bystructure2")  
  
### <a name="to-link-the-record-elements-by-name"></a>レコード要素を名前によってリンクするには  
  
1.  ソース スキーマのサブ階層の親ノードからマウスをドラッグし、ターゲット スキーマのサブ階層の親ノードのところでドロップします。  
  
2.  ショートカット メニューで、**名前によるリンク**します。 BizTalk マッパーが一致するように、**レコード**と**フィールド**内のノード、**レコード**に関係なく、対応するノードの名前に従ってリンクされているノードその構造内で、**レコード**リンクしているノード。  
  
     ![名前によるレコード要素のリンク](../core/media/linkrecordelements-byname.gif "Linkrecordelements_byname")  
  
    > [!IMPORTANT]
    >  名前によるリンクは、送信元スキーマのサブ階層親ノードからターゲット スキーマの非サブ階層親ノードに適用できます。 BizTalk マッパーは、送信元ノードの子ノードの名前とターゲット ノードの子ノードの名前を照合します。 一致する子ノードが検出されると、それぞれの子ノード間にリンクが確立されます。 次の図に、この概念を示します。  
  
## <a name="to-link-using-a-mass-copy-functoid"></a>一括コピー Functoid を使用してリンクするには  
 **一括コピー**により、マップが含まれるスキーマを使用して、functoid**任意**と**anyAttribute**要素。 これらの要素は、基本的に XML スキーマ定義言語に提供されているワイルドカードで、不明な構造や属性に一致します。  
  
 不明な構造を使用してデータを処理できることに加えて、**一括コピー** functoid では、スキーマ開発を簡略化することができます: 処理されるスキーマの部分のみが詳細で指定する必要があります。  
  
 ![一括コピー functoid によるレコード要素のリンク](../core/media/linkrecordelements-masscopyfunctoid.gif "Linkrecordelements_MassCopyfunctoid")  
  
 詳細については、**一括コピー** functoid を参照してください[一括コピー Functoid](../core/mass-copy-functoid.md)します。  
  
## <a name="see-also"></a>参照  
 [リンクを使用してレコードを指定して、フィールド マッピング](../core/using-links-to-specify-record-and-field-mappings.md)   
 [マップに一括コピー Functoid を追加する方法](../core/how-to-add-mass-copy-functoids-to-a-map.md)