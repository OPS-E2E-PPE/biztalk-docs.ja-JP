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
# <a name="complex-global-type-derivation"></a><span data-ttu-id="c9370-102">複合グローバル型の派生</span><span class="sxs-lookup"><span data-stu-id="c9370-102">Complex Global Type Derivation</span></span>
<span data-ttu-id="c9370-103">XSD での継承の 2 種類があります。 拡張機能および制限します。</span><span class="sxs-lookup"><span data-stu-id="c9370-103">There are two types of inheritance in XSD: extension and restriction.</span></span> <span data-ttu-id="c9370-104">BizTalk エディターは、次の 2 つを使用して、この XSD 機能へのアクセスを提供します**レコード**ノードのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="c9370-104">BizTalk Editor provides access to this XSD functionality by using the following two **Record** node properties:</span></span>  
  
-   <span data-ttu-id="c9370-105">**基本データ型**します。</span><span class="sxs-lookup"><span data-stu-id="c9370-105">**Base Data Type**.</span></span> <span data-ttu-id="c9370-106">このプロパティは、すべてのグローバル複合型の一覧を提供し、単純な型の使用可能な基本データ型として使用しています。</span><span class="sxs-lookup"><span data-stu-id="c9370-106">This property provides the list of all global complex types and simple types available for use as a base data type.</span></span> <span data-ttu-id="c9370-107">複合グローバル型には、同じスキーマで、またはインポートされたスキーマを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c9370-107">The complex global types can be in the same schema or in any imported schema.</span></span>  
  
-   <span data-ttu-id="c9370-108">**Derived By**します。</span><span class="sxs-lookup"><span data-stu-id="c9370-108">**Derived By**.</span></span> <span data-ttu-id="c9370-109">このプロパティは、制限による拡張による派生を選択に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c9370-109">This property is used to choose between deriving by extension or by restriction.</span></span> <span data-ttu-id="c9370-110">このプロパティが自動的に設定**拡張子**を設定すると、 **Base Data Type**プロパティの一覧で任意の型をします。</span><span class="sxs-lookup"><span data-stu-id="c9370-110">This property is automatically set to **Extension** when you set the **Base Data Type** property to any type in the list.</span></span> <span data-ttu-id="c9370-111">このプロパティを設定する場合 **(既定)**、すべての型、 **Base Data Type**プロパティを削除すると、そのノードの継承を無効にするとします。</span><span class="sxs-lookup"><span data-stu-id="c9370-111">If you set this property to **(Default)**, any type in the **Base Data Type** property is removed, disabling inheritance for the node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9370-112">**コンテンツの種類**プロパティは自動的にも設定**ComplexContent**拡張または制限による派生が使用されている場合。</span><span class="sxs-lookup"><span data-stu-id="c9370-112">The **Content Type** property is also set automatically to **ComplexContent** when derivation by extension or restriction is being used.</span></span>  
  
 <span data-ttu-id="c9370-113">このセクションでは、さらに詳しく、拡張機能と制限のメカニズムを使用して、複合型の派生について説明します。</span><span class="sxs-lookup"><span data-stu-id="c9370-113">This section explains complex type derivation by using the extension and restriction mechanisms in greater detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9370-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c9370-114">In This Section</span></span>  
  
-   [<span data-ttu-id="c9370-115">拡張メカニズムを使用した複合型の派生</span><span class="sxs-lookup"><span data-stu-id="c9370-115">Complex Type Derivation Using the Extension Mechanism</span></span>](../core/complex-type-derivation-using-the-extension-mechanism.md)  
  
-   [<span data-ttu-id="c9370-116">制約メカニズムを使用した複合型の派生</span><span class="sxs-lookup"><span data-stu-id="c9370-116">Complex Type Derivation Using the Restriction Mechanism</span></span>](../core/complex-type-derivation-using-the-restriction-mechanism.md)