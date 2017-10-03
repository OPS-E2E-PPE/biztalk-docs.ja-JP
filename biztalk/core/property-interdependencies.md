---
title: "プロパティの相互依存性 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ed5b75e-db1c-43d4-a287-fc4cd1c529f5
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15e1a02d82d294c63a33c0682e77585a7934b8ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="property-interdependencies"></a>プロパティの相互依存性

## <a name="overview"></a>概要
BizTalk エディター ([!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のプロパティ ウィンドウ) でプロパティの値を操作していると、プロパティとプロパティの間にはさまざまな依存関係があることがわかります。 あるプロパティに対して特定の設定を行うと、他のプロパティが自動的にクリアされたり、有効と無効が切り替わったり、あるいは、[プロパティ] ウィンドウから消えてしまうこともあります。 こうした相互依存は広範囲に及ぶため、ここですべてを説明することはできません。 

このセクションでは、一般的な例をいくつか示して、相互依存の機能について説明します。  
  
-   プロパティを設定するときに、**フィールド要素**ノードまたは**フィールド属性**対象のデータ型はから派生している単純型の新しいカテゴリ全体、制限メカニズムを使用してノードプロパティが使用可能になります:**制限**です。 さらに、この新しいカテゴリのプロパティは、基本データ型が文字列型であるか数値型であるかに応じて、有効または無効になります。 この形式の単純型の派生の詳細については、次を参照してください。[単純型の派生を使用して制約メカニズム](../core/simple-type-derivation-using-the-restriction-mechanism.md)です。  
  
-   プロパティを設定するときに、**フィールド要素**ノードまたは**フィールド属性**対象のデータ型はから派生している単純型リストまたはユニオンのメカニズムのいずれかを使用して、ノード、**ベースデータ型**プロパティがいずれかに変更された、**項目の種類**プロパティまたは**Member Types**プロパティ、それぞれします。 後者の場合、対応するドロップダウン リストには、チェック ボックスが追加され、複数の型から選択できるようになります。 これらの形式の単純型の派生の詳細については、次を参照してください。[単純型の派生を使用してリスト メカニズム](../core/simple-type-derivation-using-the-list-mechanism.md)と[単純型の派生メカニズムを使用して、共用体](../core/simple-type-derivation-using-the-union-mechanism.md)です。  
  
-   フラット ファイル スキーマに関連付けられたプロパティを公開するために設定する必要があります、**スキーマ エディター拡張機能**のプロパティ、**スキーマ**含めるノード、**フラット ファイル拡張子**. EDI 拡張機能などの他のエディター拡張機能に関連付けられているカスタム プロパティと同じ方法で公開されます。 対応する拡張機能を使用して、を選択して、**スキーマ エディター拡張機能**プロパティです。  
  
 ここでは、[プロパティ] ウィンドウで確認できるプロパティの相互依存性について、いくつかの例を取り上げました。ただしプロパティの相互依存性をすべて網羅しているものではない点に注意してください。  
  
## <a name="see-also"></a>参照  
-  [ノードのプロパティ](../core/node-properties.md)   
-  次のプロパティ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
    -  ノードのプロパティのアルファベット順
    -  すべてのスキーマのノード プロパティ 
    -  Schema Editor Extensions