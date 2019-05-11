---
title: その他のスキーマを使用するスキーマを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff0bcd9a-6c66-4c3b-bd41-64047a7c8392
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 729e956fc2598fb8c3bd75d2d2d8a9613e1e96ac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385445"
---
# <a name="how-to-create-schemas-that-use-other-schemas"></a>その他のスキーマを使用するスキーマを作成する方法
XML スキーマ定義 (XSD) 言語は、別のスキーマ内の 1 つのスキーマを使用するために、3 つの異なるが、関連するメカニズムを提供します。 これらのメカニズムは、スキーマ、スキーマのインクルード、およびスキーマを再定義をインポートしています。 これらのメカニズムとどのように異なるかの簡単な概要を参照してください。[使用その他のスキーマを](../core/schemas-that-use-other-schemas.md)します。 詳細については、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)XSD 入門と仕様へのリンク。  
  
 このトピックでは、インポート、インクルード、および再定義するその他のスキーマを開発するのに必要な手順について説明します。  
  
### <a name="to-import-include-or-redefine-one-schema-within-another-schema"></a>インポート、インクルード、または別のスキーマ内の 1 つのスキーマを再定義するには  
  
1. BizTalk エディターでは、インポート、インクルード、または別のスキーマを再定義するスキーマを開きます。 ソリューション エクスプ ローラーでダブルクリックして、スキーマを開くことができます。  
  
2. 選択、**スキーマ**スキーマ ツリー ビューの上部にあるノード。  
  
3. 必要に応じて F4 キーを押し、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のプロパティ ウィンドウを開きます。  
  
4. プロパティ ウィンドウで、 **詳細設定**  カテゴリの値の部分で、 **Imports**プロパティ、省略記号をクリックします (**...**) ボタンをクリックします。  
  
5. **Imports** ] ダイアログ ボックスで、**として新しいスキーマのインポート**一覧で、[ **XSD のインポート**、 **XSD Include**、または**XSD再定義**し、必要に応じて、クリックして**追加**します。  
  
6. **BizTalk 型の選択** ダイアログ ボックスで、展開、**スキーマ**、プロジェクト ツリー内のノードは、インポート、インクルード、または再定義、および をクリックするスキーマを選択します。 **OK**。  
  
7. **インポート**ダイアログ ボックスで、をクリックして**OK**。  
  
    インポートするを実装するために適切な XSD ディレクティブがインクルード、または操作を再定義に追加されます、**スキーマ**要素など、新しい XSD ビューで**インポート**、 **を含める**、または**redefine**に応じての要素。  
  
> [!IMPORTANT]
>  名前空間の要件に関しての違いなど、これらの 3 つのメカニズムのさまざまな目的を理解しておいてください。 常に以前にインポートされた、含まれる、または再定義されたスキーマを削除して、その他の 2 つのメカニズムのいずれかがによってどの程度そのスキーマを参照している場合、それに応じて、スキーマを再作成する必要があります。  
  
> [!IMPORTANT]
>  インポート、インクルード、およびインポートへの参照によって別のスキーマの動作内の 1 つのスキーマを再定義する XSD のメカニズムは含まれている場合、またはスキーマを再定義します。 つまり変更を行う場合、インポート、または再定義されたスキーマに変更をインポートを含むスキーマに反映されます包含、または参照を再定義します。  
  
## <a name="see-also"></a>参照  
 [プロジェクト内のスキーマを管理します。](../core/managing-schemas-within-projects.md)   
 [別のノードまたは種類への参照を作成する方法](../core/how-to-create-references-to-another-node-or-type.md)