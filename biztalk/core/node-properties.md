---
title: ノードのプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 366080f0-c21a-467d-8051-fd280264c5c3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec003c92f374489d59986bb5324f66100adf9e63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323538"
---
# <a name="node-properties"></a>ノードのプロパティ

## <a name="overview"></a>概要
BizTalk エディターでは、するを調べるし、Visual Studio プロパティ ウィンドウでノードのプロパティを設定します。 スキーマ ツリー ビューでさまざまな種類のノードを選択すると、異なるプロパティのセットは、[プロパティ] ウィンドウに表示されます。 Standard は[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、カテゴリ、またはそのカテゴリが示されないアルファベット順に、これらのプロパティを表示できます。 [プロパティ] ウィンドウの上部にある標準のボタンを使用して、この設定を切り替えます。  
  
 特にが既定値以外の値に設定すると、ノードのプロパティは、属性として、XML スキーマ定義 (XSD) 言語で表される通常と属性の対応する要素に関連付けられている値。 たとえば、プロパティ設定されている場合の**Min Occurs**と**Max Occurs**のプロパティは、いくつかの別のノードの種類、設定されている値で使用できますが、の値として使用される**minOccurs**と**maxOccurs**属性はそれぞれ、対象のノードが表す要素に関連付けられた、 **Min Occurs**と**Max発生した**プロパティが設定されています。  

## <a name="property-types"></a>プロパティの型
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]開発者向けリファレンスには、カテゴリ別およびアルファベット順に編成された、さまざまなノード型のプロパティのリファレンス セクションが含まれています。 次に、各ノードの種類に関連付けられているプロパティをまとめたものです。  
  
-   スキーマのノード プロパティ
  
-   レコード ノードのプロパティ
  
-   [フィールド要素] ノード プロパティ
  
-   [フィールド属性] ノード プロパティ
  
-   シーケンス グループ ノードのプロパティ
  
-   グループの選択 ノードのプロパティ 
  
-   すべてのグループ ノードのプロパティ
  
-   属性グループ ノードのプロパティ
  
-   すべての要素ノードのプロパティ
  
-   すべての属性ノードのプロパティ
  
-   等価のノード プロパティ
  
-   [Equivalent Child] ノードのプロパティ

これらのプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
 **ノードのプロパティ-アルファベット**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]すべてのノードの各プロパティのさまざまな種類のノードに適用うちいくつか個々 の参照トピックが含まれています。 個々 の参照トピックは、すべての種類のスキーマに適用される基本的なプロパティまたはフラット ファイル拡張機能など、スキーマ エディタ拡張機能に関連付けられている特殊なプロパティは分類されます。 これらのカテゴリ内でこれらがアルファベット順の一覧します。  
  
 BizTalk エディターを使用して、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウを使用すると、確認し、スキーマ ツリーで、ノードのプロパティを設定します。 このセクションの特別な考慮事項を含め、プロパティ ウィンドウでプロパティの操作の一部の特性を説明します、**ノード名**プロパティ間の相互依存関係の説明、プロパティとプロパティまたはプロパティの型については、最大の長さが特定の許可。  
  
 このセクションの残りの部分では、特定、特殊なノードのプロパティに関する追加情報およびノードのプロパティに通常適用されるその他の情報を提供します。  
  
## <a name="next-steps"></a>次のステップ
  
-   [ノード名プロパティ](../core/node-name-property.md)  
  
-   [プロパティの相互依存性](../core/property-interdependencies.md)  
  
-   [追加のフラット ファイル プロパティ](../core/additional-flat-file-properties.md)