---
title: "ノードのプロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 366080f0-c21a-467d-8051-fd280264c5c3
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d41f0f3b0fe0b302a763629b8777669b54f6cc86
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="node-properties"></a>ノードのプロパティ

## <a name="overview"></a>概要
BizTalk エディターでノードのプロパティを調べたり設定したりする場合は、Visual Studio の [プロパティ] ウィンドウを使用します。 スキーマ ツリー ビューで別の種類のノードを選択すると、それに応じたプロパティが [プロパティ] ウィンドウに表示されます。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] では、これらのプロパティをカテゴリ別またはアルファベット順に表示できます。アルファベット順に表示した場合、カテゴリは表示されません。 この設定は、[プロパティ] ウィンドウの上部にあるボタンを使って切り替えることができます。  
  
 通常、ノードのプロパティは、XSD (XML Schema Definition) 言語では、対応する要素に関連付けられた属性および属性値として表されます (特にノードのプロパティが既定値以外に設定されている場合)。 たとえば、プロパティ設定されている場合の**Min Occurs**と**Max Occurs**プロパティで、いくつかの別のノード型、設定されている値に対して使用できる、の値として使用されます**minOccurs**と**maxOccurs**属性はそれぞれ、対象のノードが表す要素に関連付けられている、 **Min Occurs**と**Max発生**プロパティが設定されています。  

## <a name="property-types"></a>プロパティの種類
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]開発者向けリファレンスには、さまざまなノード型をカテゴリ別およびアルファベット順に整理されているプロパティのリファレンス セクションが含まれています。 次の例は、各ノードの種類に関連付けられたプロパティをまとめています。  
  
-   スキーマ ノードのプロパティ
  
-   [レコード] ノードのプロパティ
  
-   [フィールド要素] ノードのプロパティ
  
-   [フィールド属性] ノードのプロパティ
  
-   [シーケンス グループ] ノードのプロパティ
  
-   [グループの選択] ノードのプロパティ 
  
-   [すべてのグループ] ノードのプロパティ
  
-   [属性グループ] ノードのプロパティ
  
-   [すべての要素] ノードのプロパティ
  
-   [すべての属性] ノードのプロパティ
  
-   [Equivalent] ノードのプロパティ
  
-   [Equivalent Child] ノードのプロパティ

これらのプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
 **ノードのプロパティ-アルファベット順**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]のすべてのさまざまな種類のノードに適用するいくつかのノードの各プロパティの個別の参照トピックが含まれています。 各リファレンス トピックは、すべての種類のスキーマに適用される基本的なプロパティであるか、スキーマ エディター拡張機能 (フラット ファイル拡張機能など) に関連した特別なプロパティであるかによって分類されています。 カテゴリ内では、各トピックがアルファベット順に記載されています。  
  
 BizTalk エディターでは、スキーマ ツリーに含まれるノードのプロパティを、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のプロパティ ウィンドウで確認または設定できます。 ここには、いくつかの特性などの特別な考慮事項 [プロパティ] ウィンドウでプロパティの操作がについて説明します、**ノード名**プロパティ間の依存関係の説明、プロパティとについての最大長は許可されている特定のプロパティまたはプロパティの型。  
  
 また、特殊なノード プロパティに関する補足情報や、ノードのプロパティ全般に関連するその他の情報についても説明しています。  
  
## <a name="next-steps"></a>次の手順
  
-   [ノード名プロパティ](../core/node-name-property.md)  
  
-   [プロパティの相互依存性](../core/property-interdependencies.md)  
  
-   [追加のフラット ファイル プロパティ](../core/additional-flat-file-properties.md)