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
# <a name="complex-global-type-derivation"></a><span data-ttu-id="3d66d-102">複合グローバル型の派生</span><span class="sxs-lookup"><span data-stu-id="3d66d-102">Complex Global Type Derivation</span></span>
<span data-ttu-id="3d66d-103">XSD での継承の 2 種類があります: 拡張機能および制限します。</span><span class="sxs-lookup"><span data-stu-id="3d66d-103">There are two types of inheritance in XSD: extension and restriction.</span></span> <span data-ttu-id="3d66d-104">BizTalk エディターは、次の 2 つを使用して、この XSD 機能へのアクセスを提供**レコード**ノードのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="3d66d-104">BizTalk Editor provides access to this XSD functionality by using the following two **Record** node properties:</span></span>  
  
-   <span data-ttu-id="3d66d-105">**基本データ型**です。</span><span class="sxs-lookup"><span data-stu-id="3d66d-105">**Base Data Type**.</span></span> <span data-ttu-id="3d66d-106">基本データ型として使用できるグローバルの複合型および単純型のリストを提供します。</span><span class="sxs-lookup"><span data-stu-id="3d66d-106">This property provides the list of all global complex types and simple types available for use as a base data type.</span></span> <span data-ttu-id="3d66d-107">複合グローバル型は、同じスキーマの範囲内で定義するだけでなく、他のスキーマをインポートすることによって定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="3d66d-107">The complex global types can be in the same schema or in any imported schema.</span></span>  
  
-   <span data-ttu-id="3d66d-108">**Derived By**です。</span><span class="sxs-lookup"><span data-stu-id="3d66d-108">**Derived By**.</span></span> <span data-ttu-id="3d66d-109">拡張による派生と制約による派生を選択できます。</span><span class="sxs-lookup"><span data-stu-id="3d66d-109">This property is used to choose between deriving by extension or by restriction.</span></span> <span data-ttu-id="3d66d-110">このプロパティに設定が自動的に**拡張子**を設定すると、 **Base Data Type**プロパティ一覧で任意の型をします。</span><span class="sxs-lookup"><span data-stu-id="3d66d-110">This property is automatically set to **Extension** when you set the **Base Data Type** property to any type in the list.</span></span> <span data-ttu-id="3d66d-111">このプロパティを設定する場合 **(既定)**、すべての型、 **Base Data Type**プロパティを削除すると、そのノードの継承を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3d66d-111">If you set this property to **(Default)**, any type in the **Base Data Type** property is removed, disabling inheritance for the node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d66d-112">**コンテンツ タイプ**でもプロパティが設定に自動的に**ComplexContent**拡張または制限による派生が使用されている場合。</span><span class="sxs-lookup"><span data-stu-id="3d66d-112">The **Content Type** property is also set automatically to **ComplexContent** when derivation by extension or restriction is being used.</span></span>  
  
 <span data-ttu-id="3d66d-113">このセクションでは、拡張と制約のメカニズムを使った複合型の派生について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="3d66d-113">This section explains complex type derivation by using the extension and restriction mechanisms in greater detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3d66d-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3d66d-114">In This Section</span></span>  
  
-   [<span data-ttu-id="3d66d-115">拡張メカニズムを使用する複合型の派生</span><span class="sxs-lookup"><span data-stu-id="3d66d-115">Complex Type Derivation Using the Extension Mechanism</span></span>](../core/complex-type-derivation-using-the-extension-mechanism.md)  
  
-   [<span data-ttu-id="3d66d-116">制約メカニズムを使用する複合型の派生</span><span class="sxs-lookup"><span data-stu-id="3d66d-116">Complex Type Derivation Using the Restriction Mechanism</span></span>](../core/complex-type-derivation-using-the-restriction-mechanism.md)