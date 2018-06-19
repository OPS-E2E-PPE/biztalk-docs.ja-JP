---
title: 他のスキーマを使用するスキーマを作成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: f427e5cd8e3f82e57dc8926c6e00889e1c97afe9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249418"
---
# <a name="how-to-create-schemas-that-use-other-schemas"></a>他のスキーマを使用するスキーマを作成する方法
XSD (XML Schema Definition) 言語には、あるスキーマを他のスキーマで使用するためのメカニズムが 3 つあります。 スキーマのインポート、スキーマのインクルード、および、スキーマの再定義です。 これらのメカニズムと違いの簡単な要約を参照してください。[スキーマを使用して他のスキーマを](../core/schemas-that-use-other-schemas.md)です。 詳細については、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)XSD 入門および仕様へのリンク用です。  
  
 このトピックでは、作成中のスキーマ内で他のスキーマをインポート、インクルード、および再定義する手順について説明します。  
  
### <a name="to-import-include-or-redefine-one-schema-within-another-schema"></a>スキーマ内で他のスキーマをインポート、インクルードまたは再定義するには  
  
1.  BizTalk エディターで、他のスキーマをインポート、インクルード、または再定義するスキーマを開きます。 スキーマを開くには、ソリューション エクスプローラーで、目的のスキーマをダブルクリックします。  
  
2.  選択、**スキーマ**スキーマ ツリー ビューの上部にあるノード。  
  
3.  必要に応じて F4 キーを押し、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のプロパティ ウィンドウを開きます。  
  
4.  プロパティ ウィンドウでの**詳細設定**  カテゴリの値の部分で、 **Imports**プロパティ、省略記号ボタンをクリックして (**...**) ボタンをクリックします。  
  
5.  **Imports** ] ダイアログ ボックスで、**として新しいスキーマのインポート**一覧で、[ **XSD のインポート**、 **XSD Include**、または**XSD再定義**、必要に応じて、をクリックして**追加**です。  
  
6.  **BizTalk 型の選択** ダイアログ ボックスで、展開、**スキーマ**プロジェクト ツリー内のノードは、インポート、インクルード、または再定義、およびをクリックするスキーマを選択**OK**です。  
  
7.  **Imports**ダイアログ ボックスで、をクリックして**OK**です。  
  
     インポートを実装する適切な XSD ディレクティブは、包含、または操作を再定義に追加されます、**スキーマ**XSD ビューで、たとえば、新しい要素**インポート**、 **を含める**、または**redefine**に応じての要素。  
  
> [!IMPORTANT]
>  これら 3 つのメカニズムの目的について、それぞれの相違点 (名前空間の要件に関連した動作上の違いなど) を理解しておく必要があります。 既にインポート、インクルード、または再定義されているスキーマはいつでも削除し、他のメカニズムのいずれかに切り替えることができます。ただし、スキーマを参照している範囲によっては、それに応じた修正をスキーマに対して行わなければならない場合もあります。  
  
> [!IMPORTANT]
>  あるスキーマを別のスキーマ内でインポート、インクルード、または再定義する XSD のメカニズムは、インポート、インクルード、または再定義されているスキーマを参照することによって機能します。 つまり、インポート、インクルード、または再定義されたスキーマに変更を加えた場合、それを参照しているスキーマにも反映されます。  
  
## <a name="see-also"></a>参照  
 [プロジェクト内のスキーマを管理します。](../core/managing-schemas-within-projects.md)   
 [別のノードまたは種類への参照を作成する方法](../core/how-to-create-references-to-another-node-or-type.md)