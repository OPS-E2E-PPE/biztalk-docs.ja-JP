---
title: レコードのリンク |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a3fa4d7-5689-4f55-af1b-369defa37037
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91108b194a186488867ff083c0129570b5fd9477
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398033"
---
# <a name="record-to-record-linking"></a>レコードへのリンク

## <a name="overview"></a>概要
Microsoft で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]同時に元と送信先スキーマの類似する部分の間での複数のリンクを作成する BizTalk マッパーを使用することができます。 BizTalk Server の以前のバージョンで個別に、このようなリンクを作成する必要がある。 1 つずつです。 レコードへのリンクを次のように、リンクされている送信元と送信先スキーマのレコードの構造体の類似性に基づいて別の適切な各シナリオの 2 種類があります。  
  
-   **構造リンクします。** 構造リンクを使用レコードの構造は、元と送信先スキーマでリンクされている場合は、同じまたは非常に似ています。  
  
-   **名前の一致リンク。** 送信元と送信先スキーマでリンクするレコードの構造がまだと同様と一致するレコードとフィールド名が構造的な例外の数が、構造リンクと比べるとよりも名前の一致リンクを使用します。  
  
    > [!NOTE]
    >  レコードのリンク値コピーのリンクを使用して構成されている場合に、のみに適用されます、**ソース リンク**プロパティ。  
  
## <a name="record-to-record-linking-structure-links"></a>--レコードをリンクします。構造リンク  
 構造と、元と送信先スキーマでリンクするレコードの構造が同じかほぼ同じようにリンクを使用します。  
  
 スキーマの構造は、同じでは正確にある場合は、各スキーマのルート ノードでのみ 1 つのリンクを追加する必要があります。 ショートカット メニューで、リンクの目的のモードを選択します。  
  
 スキーマ内の特定のレコードの構造は、同じでは正確にある場合は、各スキーマの該当するレコード間リンクを 1 つのみ追加する必要があります。 ショートカット メニューで、リンクの目的のモードを選択します。  
  
 構造リンクを使用してリンクまたは名前の一致リンクを参照してください - レコードを構成する方法については[レコードを自動的にリンク](../core/how-to-link-records-automatically.md)します。  
  
> [!NOTE]
>  構造リンクは、既定のレコードのリンクの種類です。  
  
## <a name="record-to-record-linking-name-matching-links"></a>--レコードをリンクします。名前の一致リンク  
 リンクを使用して名前の一致、元と送信先スキーマでリンクするレコードの構造が非常に似ていますが、まったく同じです。 たとえば、元または送信先スキーマには、下位レコードまたはその他のスキーマによりもリンクされているノード内のフィールドの詳細があります。  
  
 該当する場合、スキーマ全体をなど、構造がほとんど一致する元と送信先スキーマの部分の間で名前の一致リンクを作成するには、サブ階層親ノードの送信元アドレスと別の終了のリンクを作成します。サブ階層親ノードです。 ショートカット メニューで、目的のモードを選択します。 ノードをリンクした後のすべての下位のレコードと同じ構造をいて、同じ名前が元と送信先スキーマ内のフィールドへのリンクが自動的に作成します。  
  
 構造リンクを使用してリンクまたは名前の一致リンクを参照してください - レコードを構成する方法については[レコードを自動的にリンク](../core/how-to-link-records-automatically.md)します。  
  
## <a name="see-also"></a>参照  
 [レコードを自動的にリンクします。](../core/how-to-link-records-automatically.md)   
 [リンクのプロパティの編集](../core/how-to-edit-link-properties.md)