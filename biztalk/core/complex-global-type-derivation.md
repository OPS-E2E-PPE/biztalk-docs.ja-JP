---
title: 複合グローバル型の派生 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fbf429d0-64f4-4c43-a5f7-e8af050803b9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee4e6235af62b2c08c08382b897632d15e34e0cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231674"
---
# <a name="complex-global-type-derivation"></a>複合グローバル型の派生
XSD での継承の 2 種類があります: 拡張機能および制限します。 BizTalk エディターは、次の 2 つを使用して、この XSD 機能へのアクセスを提供**レコード**ノードのプロパティ。  
  
-   **基本データ型**です。 基本データ型として使用できるグローバルの複合型および単純型のリストを提供します。 複合グローバル型は、同じスキーマの範囲内で定義するだけでなく、他のスキーマをインポートすることによって定義することもできます。  
  
-   **Derived By**です。 拡張による派生と制約による派生を選択できます。 このプロパティに設定が自動的に**拡張子**を設定すると、 **Base Data Type**プロパティ一覧で任意の型をします。 このプロパティを設定する場合 **(既定)**、すべての型、 **Base Data Type**プロパティを削除すると、そのノードの継承を無効にします。  
  
> [!NOTE]
>  **コンテンツ タイプ**でもプロパティが設定に自動的に**ComplexContent**拡張または制限による派生が使用されている場合。  
  
 このセクションでは、拡張と制約のメカニズムを使った複合型の派生について詳しく説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [拡張メカニズムを使用する複合型の派生](../core/complex-type-derivation-using-the-extension-mechanism.md)  
  
-   [制約メカニズムを使用する複合型の派生](../core/complex-type-derivation-using-the-restriction-mechanism.md)