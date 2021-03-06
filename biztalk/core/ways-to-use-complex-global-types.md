---
title: 複合グローバル型を使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ddea1c7b-eb0e-4521-8576-0ea6f9460847
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bf40f80a1c1353dc56b11c8e84e8d7d395beb37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393614"
---
# <a name="ways-to-use-complex-global-types"></a>複合グローバル型の使用方法
複合型を複合グローバル型に変換した後、スキーマ内の他の場所で再利用可能になります。 複合型を定義して、グローバルな複合型への変換の詳細については、次を参照してください。[複合グローバル型の定義と名前付け](../core/complex-global-type-definition-and-naming.md)します。  
  
 最初に、新しい挿入**レコード**ノード。 挿入されたノードを選択し、それぞれ異なる効果を [プロパティ] ウィンドウで、次の 2 つのノード プロパティのいずれかの設定。  
  
-   **Data Structure Type プロパティ**します。 をまったく変更せず、複合グローバル型を使用する場合は、このプロパティを設定がドロップダウン リストの選択肢として利用可能な複合グローバル型に対して指定した型名にします。 スキーマ ツリーで選択されたグローバル ノード構造が新しい場所にグラフィカルに複製し、スキーマ ツリーでその場所のいずれかでノードの構造が変更されたは、その複合グローバル型を使用するすべての場所に自動的にされます.  
  
-   **Base Data Type プロパティ**します。 複合グローバル型のバリエーションの 1 つを使用するには、何らかの方法での制限または拡張することは設定がドロップダウン リストの選択肢として利用可能な複合グローバル型に対して指定した型名をこのプロパティを表示します。 このプロパティを設定するときに、 **Derived By**ノードのプロパティに対する変更を**拡張子**(と**コンテンツの種類**プロパティに対する変更を**ComplexContent**)、既定の派生型が複合グローバル型を拡張することを示します。 変更することができます**制限**変更内容がその性質である場合。 派生する基本の複合グローバル型への変更は、派生型では、自動的に反映されますが、基本データ型の派生型の変更が反映されることはありません。  
  
> [!NOTE]
>  これらのプロパティのいずれかが自動的に設定すると、既存の設定を削除して、もう 1 つ。 さらに、その他の自動の設定など、関連するプロパティ間の相互作用が表示されます、 **Derived By**プロパティを **(既定)** から既存の設定を削除、**ベースデータ型**プロパティ。  
  
> [!NOTE]
>  テストのスキーマを作成し、XSD ビューの変更を観察し、これらのプロパティの異なる値を使用できます。  
  
 このセクションでは、このトピックで説明されているプロパティの設定で制御されるとを拡張して、それらを制限することによっての両方に、複合グローバル型を使用について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [複合グローバル型の再利用](../core/complex-global-type-re-use.md)  
  
-   [複合グローバル型の派生](../core/complex-global-type-derivation.md)