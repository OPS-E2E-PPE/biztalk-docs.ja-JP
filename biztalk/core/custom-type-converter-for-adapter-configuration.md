---
title: アダプターの構成のカスタム型コンバーター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60e94dde-d29d-43ff-84b0-b2ba86851151
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc107422d7bb2033d68c96c27df4850acda74a09
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390066"
---
# <a name="custom-type-converter-for-adapter-configuration"></a><span data-ttu-id="c7db9-102">アダプターの構成のカスタム型コンバーター</span><span class="sxs-lookup"><span data-stu-id="c7db9-102">Custom Type Converter for Adapter Configuration</span></span>
<span data-ttu-id="c7db9-103">カスタム型コンバーターをオーバーライドしてカスタム エディターをなど、 **System.ComponentModel.TypeConverter**その子のいずれかのクラス。</span><span class="sxs-lookup"><span data-stu-id="c7db9-103">Like the custom editor, the custom type converter overrides the **System.ComponentModel.TypeConverter** class of one of its children.</span></span> <span data-ttu-id="c7db9-104">ここでは、コンバーターを追加する永続化する値の書式設定が [プロパティ] ページは表示されません。</span><span class="sxs-lookup"><span data-stu-id="c7db9-104">Here, the converter adds formatting to the value to be persisted but does not appear on the property page.</span></span> <span data-ttu-id="c7db9-105">**ConvertFrom**メソッドは文字列値を囲む角かっこを追加し、 **ConvertTo**メソッドがそれらを削除します。</span><span class="sxs-lookup"><span data-stu-id="c7db9-105">The **ConvertFrom** method adds square brackets around the string value and the **ConvertTo** method removes them.</span></span>  
  
 <span data-ttu-id="c7db9-106">次のコードでは、カスタム型コンバーターのクラス定義を示します。</span><span class="sxs-lookup"><span data-stu-id="c7db9-106">The following code is the class definition for the custom type converter:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c7db9-107">参照</span><span class="sxs-lookup"><span data-stu-id="c7db9-107">See Also</span></span>  
 <span data-ttu-id="c7db9-108">[カスタム アダプター構成デザイナー](../core/custom-adapter-configuration-designer.md) </span><span class="sxs-lookup"><span data-stu-id="c7db9-108">[Custom Adapter Configuration Designer](../core/custom-adapter-configuration-designer.md) </span></span>  
 <span data-ttu-id="c7db9-109">[アダプター構成のカスタム ドロップダウン エディター](../core/custom-drop-down-editor-for-adapter-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="c7db9-109">[Custom Drop-Down Editor for Adapter Configuration](../core/custom-drop-down-editor-for-adapter-configuration.md) </span></span>  
 <span data-ttu-id="c7db9-110">[アダプター構成のカスタム モデル ダイアログ エディター](../core/custom-modal-dialog-editor-for-adapter-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="c7db9-110">[Custom Modal Dialog Editor for Adapter Configuration](../core/custom-modal-dialog-editor-for-adapter-configuration.md) </span></span>  
 [<span data-ttu-id="c7db9-111">アダプターの詳細構成コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c7db9-111">Advanced Configuration Components for Adapters</span></span>](../core/advanced-configuration-components-for-adapters.md)