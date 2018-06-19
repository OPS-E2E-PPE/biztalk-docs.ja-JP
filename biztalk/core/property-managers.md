---
title: プロパティ マネージャー |Microsoft ドキュメント
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
ms.openlocfilehash: 6aff8fc39612ed79e6e9602ed39874d014bb4a11
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269106"
---
# <a name="property-managers"></a><span data-ttu-id="b15d7-102">プロパティ マネージャー</span><span class="sxs-lookup"><span data-stu-id="b15d7-102">Property Managers</span></span>
<span data-ttu-id="b15d7-103">プロパティ マネージャーを使用すると、XSD 表記のスキーマの要素および属性にカスタム プロパティ (通常、XSD 注釈として) を追加できます。[プロパティ] ウィンドウを拡張して、拡張機能に関連付けられているカスタム プロパティを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="b15d7-103">Property Managers allow an extension to add custom properties (generally as XSD annotations) to elements and attributes in the XSD representation of the schema, as well as extending the Properties window to include the custom properties associated with the extension.</span></span>  
  
 <span data-ttu-id="b15d7-104">プロパティ マネージャーを実装するオブジェクト、 **IPropertyManager**インターフェイスを呼び出すことによってこれへの参照を取得**IExtension.GetPropertyManager**を渡すと、 **ITreeNode**入力パラメーターとしてオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b15d7-104">A Property Manager is an object that implements the **IPropertyManager** interface, a reference to which is obtained by calling **IExtension.GetPropertyManager**, and passing an **ITreeNode** object as the input parameter.</span></span> <span data-ttu-id="b15d7-105">通常、拡張機能は、1 つ**IPropertyManager**ごとにオブジェクト**ITreeNode**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b15d7-105">Typically the extension provides one **IPropertyManager** object for each **ITreeNode** object.</span></span> <span data-ttu-id="b15d7-106">プロパティ マネージャーはそのためのカスタム プロパティのコレクションを**ITreeNode**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b15d7-106">The Property Manager is responsible for the collection of custom properties for that **ITreeNode** object.</span></span>  
  
 <span data-ttu-id="b15d7-107">カスタム プロパティで表される、 **System.ComponentModel.PropertyDescriptor**によって返されるコレクションから取得できるオブジェクト、 **IPropertyManager.GetProperties**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="b15d7-107">A custom property is represented by a **System.ComponentModel.PropertyDescriptor** object, which can be obtained from the collection returned by the **IPropertyManager.GetProperties** method.</span></span>  
  
 <span data-ttu-id="b15d7-108">使用して**PropertyDescriptor**拡張機能に関連付けられているカスタム プロパティを表すオブジェクトには、Microsoft との統合が容易になります。[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="b15d7-108">Using **PropertyDescriptor** objects to represent the custom properties associated with the extension facilitates integration with the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span> <span data-ttu-id="b15d7-109">ときに**PropertyDescriptor**オブジェクトを使用して、簡単に BizTalk エディターで、拡張機能のカスタム プロパティを [プロパティ] ウィンドウに既に統合されている標準のノード プロパティのセットに統合します。</span><span class="sxs-lookup"><span data-stu-id="b15d7-109">When **PropertyDescriptor** objects are used, it is easy for BizTalk Editor to integrate the custom properties of the extension into the set of standard node properties already being integrated into the Properties window.</span></span> <span data-ttu-id="b15d7-110">表示名、表示値、コントロールのプロパティの型、プロパティの説明、およびプロパティのカテゴリなどのカスタム プロパティの情報を得た、 **PropertyDescriptor**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b15d7-110">Custom property information such as the display name, the display value, the type of property control, the property description, and the property category is obtained from the **PropertyDescriptor** object.</span></span>  
  
 <span data-ttu-id="b15d7-111">カスタム プロパティは、スキーマ ツリーの関連ノードに対応する要素の注釈要素内の要素の属性として、XSD 表記のスキーマに保存されます。</span><span class="sxs-lookup"><span data-stu-id="b15d7-111">Custom properties are stored in the XSD representation of the schema as attributes of an element within the annotation element within the element corresponding to the relevant node in the schema tree.</span></span> <span data-ttu-id="b15d7-112">スキーマ ツリー ノードの各カスタム プロパティは、一般的な要素の属性に指定できます。また、各カスタム プロパティは、固有の関連付けられた要素を持つこともできます。</span><span class="sxs-lookup"><span data-stu-id="b15d7-112">Each custom property of a schema tree node can be an attribute of a common element, or alternatively, each can have its own associated element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b15d7-113">参照</span><span class="sxs-lookup"><span data-stu-id="b15d7-113">See Also</span></span>  
 [<span data-ttu-id="b15d7-114">BizTalk エディターの拡張</span><span class="sxs-lookup"><span data-stu-id="b15d7-114">Extending BizTalk Editor</span></span>](../core/extending-biztalk-editor.md)