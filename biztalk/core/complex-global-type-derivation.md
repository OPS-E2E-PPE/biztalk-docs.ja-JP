---
title: 複合グローバル型の派生 |Microsoft Docs
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
ms.openlocfilehash: b82c7482204195010cf4d1177c4e6ccad4713df2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356711"
---
# <a name="complex-global-type-derivation"></a>複合グローバル型の派生
XSD での継承の 2 種類があります。 拡張機能および制限します。 BizTalk エディターは、次の 2 つを使用して、この XSD 機能へのアクセスを提供します**レコード**ノードのプロパティ。  
  
-   **基本データ型**します。 このプロパティは、すべてのグローバル複合型の一覧を提供し、単純な型の使用可能な基本データ型として使用しています。 複合グローバル型には、同じスキーマで、またはインポートされたスキーマを指定できます。  
  
-   **Derived By**します。 このプロパティは、制限による拡張による派生を選択に使用されます。 このプロパティが自動的に設定**拡張子**を設定すると、 **Base Data Type**プロパティの一覧で任意の型をします。 このプロパティを設定する場合 **(既定)**、すべての型、 **Base Data Type**プロパティを削除すると、そのノードの継承を無効にするとします。  
  
> [!NOTE]
>  **コンテンツの種類**プロパティは自動的にも設定**ComplexContent**拡張または制限による派生が使用されている場合。  
  
 このセクションでは、さらに詳しく、拡張機能と制限のメカニズムを使用して、複合型の派生について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [拡張メカニズムを使用した複合型の派生](../core/complex-type-derivation-using-the-extension-mechanism.md)  
  
-   [制約メカニズムを使用した複合型の派生](../core/complex-type-derivation-using-the-restriction-mechanism.md)