---
title: "アダプターの構成コンポーネントを高度な |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cb31b996-6959-4b5a-9a9f-f48fd91a6180
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8307f54caffec269466dcd9398a9d911fdc83715
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="advanced-configuration-components-for-adapters"></a><span data-ttu-id="5819f-102">アダプターの高度な構成コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5819f-102">Advanced Configuration Components for Adapters</span></span>
<span data-ttu-id="5819f-103">BizTalk アダプター フレームワークは、カスタム ドロップダウン エディター、カスタム モーダル ダイアログ エディター、およびカスタム型コンバーターをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5819f-103">The BizTalk Adapter Framework supports a custom drop-down editor, a custom modal dialog editor, and a custom type converter.</span></span> <span data-ttu-id="5819f-104">これらのカスタム デザイン コンポーネントは、ユーザー名やパスワード情報を入力として受け取る場合に特に役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="5819f-104">These custom design components are especially useful when taking user name and password information as input.</span></span>  
  
 <span data-ttu-id="5819f-105">構成スキーマの特定のデータ フィールド (要素または属性) に対してカスタム エディターやカスタム型コンバーターを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="5819f-105">You can invoke a custom editor or type converter for a specific data field (element or attribute) in the configuration schema.</span></span> <span data-ttu-id="5819f-106">Microsoft」の説明に従って[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ヘルプ、エディターから派生する必要があります**System.Drawing.Design.UITypeEditor**と、型コンバーター **System.ComponentModel.TypeConverter**です。</span><span class="sxs-lookup"><span data-stu-id="5819f-106">As described in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help, the editor must be derived from **System.Drawing.Design.UITypeEditor** and the type converter from **System.ComponentModel.TypeConverter**.</span></span>  
  
 <span data-ttu-id="5819f-107">エディターが最小限に抑えるよりも優先、 **GetEditStyle**エディターの種類を指定する方法 (**モーダル**ダイアログ ボックスで、**ドロップダウン**コントロール、または**None**上記の) および**EditValue**エディターでは、値を変更するメソッド。</span><span class="sxs-lookup"><span data-stu-id="5819f-107">An editor minimally overrides the **GetEditStyle** method to specify the kind of editor (**Modal** dialog, **DropDown** control, or **None** of the above) and the **EditValue** method to change the value with the editor.</span></span>  
  
 <span data-ttu-id="5819f-108">実行する型コンバーターは通常よりも優先、 **ConvertFrom**、 **CanConvertFrom**、 **ConvertTo**、 **CanConvertTo**、 **GetStandardValues**、 **GetStandardValuesSupported**、および**GetStandardValuesExclusive**.NET Framework クラス ライブラリのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="5819f-108">A type converter typically overrides the **ConvertFrom**, **CanConvertFrom**, **ConvertTo**, **CanConvertTo**, **GetStandardValues**, **GetStandardValuesSupported**, and **GetStandardValuesExclusive**methods of the .NET Framework Class Library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5819f-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5819f-109">In This Section</span></span>  
  
-   [<span data-ttu-id="5819f-110">カスタム アダプター構成デザイナー</span><span class="sxs-lookup"><span data-stu-id="5819f-110">Custom Adapter Configuration Designer</span></span>](../core/custom-adapter-configuration-designer.md)  
  
-   [<span data-ttu-id="5819f-111">アダプター構成のカスタム ドロップダウン エディター</span><span class="sxs-lookup"><span data-stu-id="5819f-111">Custom Drop-Down Editor for Adapter Configuration</span></span>](../core/custom-drop-down-editor-for-adapter-configuration.md)  
  
-   [<span data-ttu-id="5819f-112">アダプター構成のカスタム モデル ダイアログ エディター</span><span class="sxs-lookup"><span data-stu-id="5819f-112">Custom Modal Dialog Editor for Adapter Configuration</span></span>](../core/custom-modal-dialog-editor-for-adapter-configuration.md)  
  
-   [<span data-ttu-id="5819f-113">アダプターの構成のカスタム型コンバーター</span><span class="sxs-lookup"><span data-stu-id="5819f-113">Custom Type Converter for Adapter Configuration</span></span>](../core/custom-type-converter-for-adapter-configuration.md)