---
title: "デザイナーの機能拡張のサンプルの動作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f4dc622-28b8-498d-961f-df969cff9dcb
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f78e5ab2c8a274b53b3cc580b37842772924af94
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-the-designer-extensibility-sample-works"></a><span data-ttu-id="c0b34-102">デザイナーの機能拡張のサンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="c0b34-102">How the Designer Extensibility Sample Works</span></span>
<span data-ttu-id="c0b34-103">デザイナーの機能拡張のサンプルでは、各プロジェクトには、2 つのクラスが含まれています。 **Extender**クラスおよび**拡張プロバイダー**クラスです。</span><span class="sxs-lookup"><span data-stu-id="c0b34-103">Each project in the Designer Extensibility sample contains two classes: an **Extender** class and an **Extension Provider** class.</span></span> <span data-ttu-id="c0b34-104">これらのクラスが、機能を拡張しのプロパティを定義するように設計、 **ItineraryDsl**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="c0b34-104">These classes are designed to extend the capabilities and define the properties of the **ItineraryDsl** model elements.</span></span>  
  
 <span data-ttu-id="c0b34-105">**拡張プロバイダー**クラスから派生し、 **ExtensionProviderBase**クラスし、いる、 **ExtensionProviderAttribute**プロパティを持つそれらに適用します。拡張機能とその目的を識別します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-105">The **Extension Provider** classes derive from the **ExtensionProviderBase** class and have the **ExtensionProviderAttribute** applied to them with properties that identify the extension and its purpose.</span></span> <span data-ttu-id="c0b34-106">これらの値が表示されます、デザイナー内のユーザーにユーザーを設定するときに、 **Extender**モデル要素のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="c0b34-106">These values will be displayed to the user in the designer when the user is setting the **Extender** property on a model element.</span></span> <span data-ttu-id="c0b34-107">ときに、**拡張プロバイダー**のコンス トラクターを呼び出すクラスの初期化、 **ExtensionProviderBase** extender クラスの型を渡す。</span><span class="sxs-lookup"><span data-stu-id="c0b34-107">When the **Extension Provider** classes initialize, they call to the constructor for the **ExtensionProviderBase** and pass to it the type of the extender class.</span></span>  
  
 <span data-ttu-id="c0b34-108">**Extender**クラスがある、 **ObjectExtender**属性はそれらへの適用、 **ObjectExtender**内のオブジェクトの種類を通過するとき、属性、 **ItineraryDsl**拡張します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-108">The **Extender** classes have an **ObjectExtender** attribute applied to them; to the **ObjectExtender** attribute, they pass the type of the object in the **ItineraryDsl** that they extend.</span></span> <span data-ttu-id="c0b34-109">これらのクラスの基底クラスは、extender の種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c0b34-109">The base class for these classes varies, depending on the type of extender.</span></span> <span data-ttu-id="c0b34-110">基本クラスは、競合回避モジュールのエクステンダーの**ObjectExtender\<リゾルバー\>**です。</span><span class="sxs-lookup"><span data-stu-id="c0b34-110">For Resolver extenders, the base class is **ObjectExtender\<Resolver\>**.</span></span> <span data-ttu-id="c0b34-111">基本クラスは、行程サービス エクステンダーの**ItineraryServiceExtenderBase**です。</span><span class="sxs-lookup"><span data-stu-id="c0b34-111">For Itinerary Service extenders, the base class is **ItineraryServiceExtenderBase**.</span></span> <span data-ttu-id="c0b34-112">**Extender**クラス、次の属性は、プロパティに適用されます属性、プロパティ グリッドで適切な表示に必要な検証のために、Microsoft Enterprise Library に含まれる属性。適切なシリアル化に必要な属性やプロパティを永続化する方法を決定する属性。</span><span class="sxs-lookup"><span data-stu-id="c0b34-112">In the **Extender** classes, the following attributes are applied to the properties: attributes necessary for proper display in a property grid, attributes included in the Microsoft Enterprise Library for validation purposes, attributes necessary for proper serialization, and/or attributes that determine how properties are persisted.</span></span>  
  
 <span data-ttu-id="c0b34-113">これらのアセンブリでは、コンパイルされ、Lib フォルダーに配置することが、ときに、読み込まれ、デザイナーによって実行時にキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="c0b34-113">When these assemblies are compiled and placed in the Lib folder, they are loaded and cached by the designer at run time.</span></span> <span data-ttu-id="c0b34-114">Extender は、必要に応じて、 **ItineraryDsl**アセンブリを読み込む、適用可能なキャッシュからエクスポートされた型とそれらの型の属性を調べることでリフレクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-114">As extenders are needed, the **ItineraryDsl** uses reflection to load the applicable assemblies from the cache by examining the types exported and the attributes on those types.</span></span>