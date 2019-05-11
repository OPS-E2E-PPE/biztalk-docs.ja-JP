---
title: アダプターの構成コンポーネントを高度な |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb31b996-6959-4b5a-9a9f-f48fd91a6180
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33509a64a80aa27d241a3b2634e89026cecfe0c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360667"
---
# <a name="advanced-configuration-components-for-adapters"></a><span data-ttu-id="44418-102">アダプターの高度な構成コンポーネント</span><span class="sxs-lookup"><span data-stu-id="44418-102">Advanced Configuration Components for Adapters</span></span>
<span data-ttu-id="44418-103">BizTalk アダプター フレームワークには、カスタム ドロップダウン エディターやカスタムのモーダル ダイアログ エディター、カスタム型コンバーターがサポートしています。</span><span class="sxs-lookup"><span data-stu-id="44418-103">The BizTalk Adapter Framework supports a custom drop-down editor, a custom modal dialog editor, and a custom type converter.</span></span> <span data-ttu-id="44418-104">これらのカスタム デザイン コンポーネントは、入力としてユーザー名とパスワードの情報を作成する際に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="44418-104">These custom design components are especially useful when taking user name and password information as input.</span></span>  
  
 <span data-ttu-id="44418-105">カスタム エディターか、構成スキーマで特定のデータ フィールド (要素または属性) の型コンバーターを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="44418-105">You can invoke a custom editor or type converter for a specific data field (element or attribute) in the configuration schema.</span></span> <span data-ttu-id="44418-106">Microsoft」の説明に従って[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ヘルプについては、エディターから派生する必要があります**System.Drawing.Design.UITypeEditor**から型コンバーターと**System.ComponentModel.TypeConverter**します。</span><span class="sxs-lookup"><span data-stu-id="44418-106">As described in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help, the editor must be derived from **System.Drawing.Design.UITypeEditor** and the type converter from **System.ComponentModel.TypeConverter**.</span></span>  
  
 <span data-ttu-id="44418-107">エディターの最低限のオーバーライド、 **GetEditStyle**エディターの種類を指定するメソッド (**モーダル**ダイアログ ボックスで、**ドロップダウン**コントロール、または**None**上記の) および**EditValue**エディターを使用して値を変更するメソッド。</span><span class="sxs-lookup"><span data-stu-id="44418-107">An editor minimally overrides the **GetEditStyle** method to specify the kind of editor (**Modal** dialog, **DropDown** control, or **None** of the above) and the **EditValue** method to change the value with the editor.</span></span>  
  
 <span data-ttu-id="44418-108">型コンバーターは通常よりも優先、 **ConvertFrom**、 **CanConvertFrom**、 **ConvertTo**、 **CanConvertTo**、 **GetStandardValues**、 **GetStandardValuesSupported**、および**GetStandardValuesExclusive**.NET Framework クラス ライブラリのメソッド。</span><span class="sxs-lookup"><span data-stu-id="44418-108">A type converter typically overrides the **ConvertFrom**, **CanConvertFrom**, **ConvertTo**, **CanConvertTo**, **GetStandardValues**, **GetStandardValuesSupported**, and **GetStandardValuesExclusive**methods of the .NET Framework Class Library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="44418-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="44418-109">In This Section</span></span>  
  
-   [<span data-ttu-id="44418-110">カスタム アダプター構成デザイナー</span><span class="sxs-lookup"><span data-stu-id="44418-110">Custom Adapter Configuration Designer</span></span>](../core/custom-adapter-configuration-designer.md)  
  
-   [<span data-ttu-id="44418-111">アダプター構成のカスタム ドロップダウン エディター</span><span class="sxs-lookup"><span data-stu-id="44418-111">Custom Drop-Down Editor for Adapter Configuration</span></span>](../core/custom-drop-down-editor-for-adapter-configuration.md)  
  
-   [<span data-ttu-id="44418-112">アダプター構成のカスタム モデル ダイアログ エディター</span><span class="sxs-lookup"><span data-stu-id="44418-112">Custom Modal Dialog Editor for Adapter Configuration</span></span>](../core/custom-modal-dialog-editor-for-adapter-configuration.md)  
  
-   [<span data-ttu-id="44418-113">アダプター構成のカスタム型コンバーター</span><span class="sxs-lookup"><span data-stu-id="44418-113">Custom Type Converter for Adapter Configuration</span></span>](../core/custom-type-converter-for-adapter-configuration.md)