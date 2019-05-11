---
title: デザイナー機能拡張サンプルのしくみ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f4dc622-28b8-498d-961f-df969cff9dcb
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 963c5ae2f778f193135fa73366d81cc359f5a798
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397118"
---
# <a name="how-the-designer-extensibility-sample-works"></a><span data-ttu-id="3f747-102">デザイナー機能拡張サンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="3f747-102">How the Designer Extensibility Sample Works</span></span>
<span data-ttu-id="3f747-103">デザイナーの機能拡張サンプル内の各プロジェクトに 2 つのクラスが含まれています。**エクステンダー**クラスおよび**拡張機能プロバイダー**クラス。</span><span class="sxs-lookup"><span data-stu-id="3f747-103">Each project in the Designer Extensibility sample contains two classes: an **Extender** class and an **Extension Provider** class.</span></span> <span data-ttu-id="3f747-104">これらのクラスが、機能を拡張し、のプロパティを定義するように設計、 **ItineraryDsl**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="3f747-104">These classes are designed to extend the capabilities and define the properties of the **ItineraryDsl** model elements.</span></span>  
  
 <span data-ttu-id="3f747-105">**拡張機能プロバイダー**クラスから派生、 **ExtensionProviderBase**クラスし、いる、 **ExtensionProviderAttribute**プロパティとそれらに適用します。拡張機能とその目的を特定します。</span><span class="sxs-lookup"><span data-stu-id="3f747-105">The **Extension Provider** classes derive from the **ExtensionProviderBase** class and have the **ExtensionProviderAttribute** applied to them with properties that identify the extension and its purpose.</span></span> <span data-ttu-id="3f747-106">ユーザーが設定されるときにそのこれらの値が、デザイナーでユーザーに表示される、**エクステンダー**モデル要素のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="3f747-106">These values will be displayed to the user in the designer when the user is setting the **Extender** property on a model element.</span></span> <span data-ttu-id="3f747-107">ときに、**拡張機能プロバイダー**のコンス トラクターを呼び出すクラスの初期化、 **ExtensionProviderBase**エクステンダー クラスの型を渡すとします。</span><span class="sxs-lookup"><span data-stu-id="3f747-107">When the **Extension Provider** classes initialize, they call to the constructor for the **ExtensionProviderBase** and pass to it the type of the extender class.</span></span>  
  
 <span data-ttu-id="3f747-108">**エクステンダー**クラスが、 **ObjectExtender** ; に適用される属性、 **ObjectExtender**内のオブジェクトの型を渡される、属性、 **ItineraryDsl**拡張するものです。</span><span class="sxs-lookup"><span data-stu-id="3f747-108">The **Extender** classes have an **ObjectExtender** attribute applied to them; to the **ObjectExtender** attribute, they pass the type of the object in the **ItineraryDsl** that they extend.</span></span> <span data-ttu-id="3f747-109">これらのクラスの基本クラスは、エクステンダーの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="3f747-109">The base class for these classes varies, depending on the type of extender.</span></span> <span data-ttu-id="3f747-110">基本クラスは、競合回避モジュールのエクステンダーの**ObjectExtender\<リゾルバー\>** します。</span><span class="sxs-lookup"><span data-stu-id="3f747-110">For Resolver extenders, the base class is **ObjectExtender\<Resolver\>**.</span></span> <span data-ttu-id="3f747-111">基本クラスは、旅行プラン サービスのエクステンダーの**ItineraryServiceExtenderBase**します。</span><span class="sxs-lookup"><span data-stu-id="3f747-111">For Itinerary Service extenders, the base class is **ItineraryServiceExtenderBase**.</span></span> <span data-ttu-id="3f747-112">**エクステンダー**クラスでは、次の属性がプロパティに適用されます属性プロパティ グリッドで適切に表示するために必要な検証のために、Microsoft Enterprise Library に含まれる属性。適切なシリアル化に必要な属性やプロパティを永続化する方法を決定する属性。</span><span class="sxs-lookup"><span data-stu-id="3f747-112">In the **Extender** classes, the following attributes are applied to the properties: attributes necessary for proper display in a property grid, attributes included in the Microsoft Enterprise Library for validation purposes, attributes necessary for proper serialization, and/or attributes that determine how properties are persisted.</span></span>  
  
 <span data-ttu-id="3f747-113">これらのアセンブリがコンパイルされ、Lib フォルダーに配置の読み込み時と実行時に、デザイナーによってキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="3f747-113">When these assemblies are compiled and placed in the Lib folder, they are loaded and cached by the designer at run time.</span></span> <span data-ttu-id="3f747-114">エクステンダーは、必要に応じて、 **ItineraryDsl**リフレクションを使用してキャッシュからエクスポートされた型とそれらの型の属性を調べることで適用可能なアセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="3f747-114">As extenders are needed, the **ItineraryDsl** uses reflection to load the applicable assemblies from the cache by examining the types exported and the attributes on those types.</span></span>