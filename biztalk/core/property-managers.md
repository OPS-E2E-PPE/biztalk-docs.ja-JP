---
title: プロパティ マネージャー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 823352a0-e397-464a-a163-1dbf8feea8d7
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a8a96ce643c7b7268ea01f5f0313ab9225eeb63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398468"
---
# <a name="property-managers"></a><span data-ttu-id="ff325-102">プロパティ マネージャー</span><span class="sxs-lookup"><span data-stu-id="ff325-102">Property Managers</span></span>
<span data-ttu-id="ff325-103">プロパティ マネージャーは、要素に (通常、XSD 注釈) としてカスタム プロパティを追加する拡張機能を許可して、カスタム プロパティは、[プロパティ] ウィンドウを拡張するほか、スキーマの XSD 表記内の属性に関連付けられている、拡張機能。</span><span class="sxs-lookup"><span data-stu-id="ff325-103">Property Managers allow an extension to add custom properties (generally as XSD annotations) to elements and attributes in the XSD representation of the schema, as well as extending the Properties window to include the custom properties associated with the extension.</span></span>  
  
 <span data-ttu-id="ff325-104">プロパティ マネージャーは、実装するオブジェクト、 **IPropertyManager**される参照は呼び出すことによって取得インターフェイス**IExtension.GetPropertyManager**、渡すと、 **ITreeNode**入力パラメーターとしてオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ff325-104">A Property Manager is an object that implements the **IPropertyManager** interface, a reference to which is obtained by calling **IExtension.GetPropertyManager**, and passing an **ITreeNode** object as the input parameter.</span></span> <span data-ttu-id="ff325-105">1 つが、拡張機能では、通常は**IPropertyManager**オブジェクトごとに**ITreeNode**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ff325-105">Typically the extension provides one **IPropertyManager** object for each **ITreeNode** object.</span></span> <span data-ttu-id="ff325-106">プロパティ マネージャーはそのため、カスタム プロパティのコレクションを**ITreeNode**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ff325-106">The Property Manager is responsible for the collection of custom properties for that **ITreeNode** object.</span></span>  
  
 <span data-ttu-id="ff325-107">によってカスタム プロパティが表される、 **System.ComponentModel.PropertyDescriptor**オブジェクトによって返されるコレクションから取得できますが、 **IPropertyManager.GetProperties**メソッド。</span><span class="sxs-lookup"><span data-stu-id="ff325-107">A custom property is represented by a **System.ComponentModel.PropertyDescriptor** object, which can be obtained from the collection returned by the **IPropertyManager.GetProperties** method.</span></span>  
  
 <span data-ttu-id="ff325-108">使用して**PropertyDescriptor** 、拡張機能に関連付けられているカスタム プロパティを表すオブジェクトには、Microsoft との統合が容易に[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="ff325-108">Using **PropertyDescriptor** objects to represent the custom properties associated with the extension facilitates integration with the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span> <span data-ttu-id="ff325-109">ときに**PropertyDescriptor**オブジェクトを使用して、簡単に BizTalk エディターの拡張機能のカスタム プロパティを一連のプロパティ ウィンドウに既に統合されている標準的なノードのプロパティに統合します。</span><span class="sxs-lookup"><span data-stu-id="ff325-109">When **PropertyDescriptor** objects are used, it is easy for BizTalk Editor to integrate the custom properties of the extension into the set of standard node properties already being integrated into the Properties window.</span></span> <span data-ttu-id="ff325-110">表示名、表示値、コントロールのプロパティの型、プロパティの説明、およびプロパティのカテゴリなどのカスタム プロパティの情報がから取得した、 **PropertyDescriptor**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ff325-110">Custom property information such as the display name, the display value, the type of property control, the property description, and the property category is obtained from the **PropertyDescriptor** object.</span></span>  
  
 <span data-ttu-id="ff325-111">カスタム プロパティは、スキーマ ツリー内の関連ノードに対応する要素の注釈要素内の要素の属性として、スキーマの XSD 表記で格納されます。</span><span class="sxs-lookup"><span data-stu-id="ff325-111">Custom properties are stored in the XSD representation of the schema as attributes of an element within the annotation element within the element corresponding to the relevant node in the schema tree.</span></span> <span data-ttu-id="ff325-112">各カスタム プロパティ スキーマのツリー ノードの一般的な要素の属性に指定できますか、または、それぞれ独自の関連付けられている要素を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="ff325-112">Each custom property of a schema tree node can be an attribute of a common element, or alternatively, each can have its own associated element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff325-113">参照</span><span class="sxs-lookup"><span data-stu-id="ff325-113">See Also</span></span>  
 [<span data-ttu-id="ff325-114">BizTalk エディターの拡張</span><span class="sxs-lookup"><span data-stu-id="ff325-114">Extending BizTalk Editor</span></span>](../core/extending-biztalk-editor.md)