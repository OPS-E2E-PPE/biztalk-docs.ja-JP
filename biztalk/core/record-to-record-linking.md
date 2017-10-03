---
title: "レコードのリンク |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a3fa4d7-5689-4f55-af1b-369defa37037
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac6abc3d27ad3ee2f135e3ff5c8c1749fcae5f4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="record-to-record-linking"></a>レコード間のリンク

## <a name="overview"></a>概要
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の BizTalk マッパーを使用すると、送信元スキーマや送信先スキーマの類似する部分間に複数のリンクを同時に作成できます。 BizTalk Server の以前のバージョンでは、個別に (一度に 1 つ) このようなリンクを作成する必要がありました。 レコード間のリンクには、2 つの異なる種類があります。次のように、リンクする送信元 (および送信先) スキーマ レコードの構造の類似性に基づいて、さまざまなシナリオに適切に対応します。  
  
-   **構造リンクします。** 送信元スキーマおよび送信先スキーマでリンクするレコードの構造が同じか非常に似ている場合は、構造リンクを使用します。  
  
-   **名前の一致リンク。** 送信元スキーマおよび送信先スキーマでリンクするレコードの構造が似ており、レコード名とフィールド名が一致しているが、構造リンクを使用するときと比べると、多くの構造上の例外が発生する場合は、名前の一致リンクを使用します。  
  
    > [!NOTE]
    >  レコードのリンク値コピーのリンクのみを使用して構成に適用されます、**送信元のリンク**プロパティです。  
  
## <a name="record-to-record-linking-structure-links"></a>構造リンクのレコードをリンクします。  
 リンク元とコピー先のスキーマでリンクするレコードの構造が同じか、またはほぼ同じ構造を使用します。  
  
 スキーマの構造が完全に同じ場合は、各スキーマのルート ノードに単一のリンクを追加します。 ショートカット メニューで、リンクの目的のモードを選択します。  
  
 スキーマの特定のレコードの構造が完全に同じ場合は、各スキーマの該当するレコード間に単一のリンクを追加します。 ショートカット メニューで、リンクの目的のモードを選択します。  
  
 構造リンクを使用してリンクまたは名前の一致リンクするを参照してレコードを構成する方法について[レコードを自動的にリンク](../core/how-to-link-records-automatically.md)です。  
  
> [!NOTE]
>  構造リンクは、レコード間リンクの既定の種類です。  
  
## <a name="record-to-record-linking-name-matching-links"></a>レコードのリンク: 名前の一致リンク  
 送信元スキーマおよび送信先スキーマでリンクするレコードの構造が非常に似ている (完全に同じではない) 場合は、名前の一致リンクを使用します。 たとえば、送信元スキーマまたは送信先スキーマで、リンクするノード内にある下位のレコードとフィールドが、一方のスキーマと比べると多い場合などです。  
  
 構造がほとんど一致する送信元スキーマおよび送信先スキーマの部分間 (場合によってはスキーマ全体) の名前の一致リンクを作成するには、サブ階層親ノードから始まり別のサブ階層親ノードで終わるリンクを作成します。 ショートカット メニューで、目的のモードを選択します。 ノードをリンクすると、同じ名前で同じ構造を持つ送信元スキーマおよび送信先スキーマの下位のすべてのレコードとフィールドにリンクが自動的に作成されます。  
  
 構造リンクを使用してリンクまたは名前の一致リンクするを参照してレコードを構成する方法について[レコードを自動的にリンク](../core/how-to-link-records-automatically.md)です。  
  
## <a name="see-also"></a>参照  
 [レコードを自動的にリンクします。](../core/how-to-link-records-automatically.md)   
 [リンクのプロパティを編集します。](../core/how-to-edit-link-properties.md)