---
title: "アダプターの構成のカスタム型コンバーター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60e94dde-d29d-43ff-84b0-b2ba86851151
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f6285cd61fd0738fb97c6192cd52b812d96ede7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="custom-type-converter-for-adapter-configuration"></a><span data-ttu-id="96a73-102">アダプターの構成のカスタム型コンバーター</span><span class="sxs-lookup"><span data-stu-id="96a73-102">Custom Type Converter for Adapter Configuration</span></span>
<span data-ttu-id="96a73-103">カスタムのエディターなど、カスタム型コンバーターよりも優先、 **System.ComponentModel.TypeConverter**の 1 つの子のクラスです。</span><span class="sxs-lookup"><span data-stu-id="96a73-103">Like the custom editor, the custom type converter overrides the **System.ComponentModel.TypeConverter** class of one of its children.</span></span> <span data-ttu-id="96a73-104">このとき、コンバーターでは値が保持されるように書式が追加されますが、プロパティ ページには表示されません。</span><span class="sxs-lookup"><span data-stu-id="96a73-104">Here, the converter adds formatting to the value to be persisted but does not appear on the property page.</span></span> <span data-ttu-id="96a73-105">**ConvertFrom**メソッドは文字列値を囲む角かっこを追加し、 **ConvertTo**メソッドでは、それらを削除します。</span><span class="sxs-lookup"><span data-stu-id="96a73-105">The **ConvertFrom** method adds square brackets around the string value and the **ConvertTo** method removes them.</span></span>  
  
 <span data-ttu-id="96a73-106">次のコードはカスタム型コンバーターのクラス定義です。</span><span class="sxs-lookup"><span data-stu-id="96a73-106">The following code is the class definition for the custom type converter:</span></span>  
  
```  
using System;  
using System.ComponentModel;  
  
namespace AdapterManagement.ComponentModel {  
  
   public class DesignerTypeConverter : StringConverter {  
  
      public override bool CanConvertTo(ITypeDescriptorContext context, Type destinationType) {  
         return (typeof(String) == destinationType) || base.CanConvertTo (context, destinationType);  
      }  
  
      public override object ConvertTo(ITypeDescriptorContext context, System.Globalization.CultureInfo culture, object value, Type destinationType) {  
         if (typeof(String) == destinationType && value is String) {  
            return ((String)value).TrimStart('[').TrimEnd(']');  
         }  
         return base.ConvertTo (context, culture, value, destinationType);  
      }  
  
      public override bool CanConvertFrom(ITypeDescriptorContext context, Type sourceType) {  
         return (typeof(String) == sourceType) || base.CanConvertFrom (context, sourceType);  
      }  
  
      public override object ConvertFrom(ITypeDescriptorContext context, System.Globalization.CultureInfo culture, object value) {  
         if (value is String) {  
            return "["+(String)value+"]";  
         }  
         return base.ConvertFrom (context, culture, value);  
      }  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="96a73-107">参照</span><span class="sxs-lookup"><span data-stu-id="96a73-107">See Also</span></span>  
 <span data-ttu-id="96a73-108">[カスタム アダプター構成デザイナー](../core/custom-adapter-configuration-designer.md) </span><span class="sxs-lookup"><span data-stu-id="96a73-108">[Custom Adapter Configuration Designer](../core/custom-adapter-configuration-designer.md) </span></span>  
 <span data-ttu-id="96a73-109">[アダプター構成のカスタム ドロップダウン エディター](../core/custom-drop-down-editor-for-adapter-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="96a73-109">[Custom Drop-Down Editor for Adapter Configuration](../core/custom-drop-down-editor-for-adapter-configuration.md) </span></span>  
 <span data-ttu-id="96a73-110">[アダプター構成のカスタム モデル ダイアログ エディター](../core/custom-modal-dialog-editor-for-adapter-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="96a73-110">[Custom Modal Dialog Editor for Adapter Configuration](../core/custom-modal-dialog-editor-for-adapter-configuration.md) </span></span>  
 [<span data-ttu-id="96a73-111">アダプターの高度な構成コンポーネント</span><span class="sxs-lookup"><span data-stu-id="96a73-111">Advanced Configuration Components for Adapters</span></span>](../core/advanced-configuration-components-for-adapters.md)