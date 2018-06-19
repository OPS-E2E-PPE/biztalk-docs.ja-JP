---
title: アダプターの構成のカスタム型コンバーター |Microsoft ドキュメント
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
ms.openlocfilehash: 8f6285cd61fd0738fb97c6192cd52b812d96ede7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238714"
---
# <a name="custom-type-converter-for-adapter-configuration"></a>アダプターの構成のカスタム型コンバーター
カスタムのエディターなど、カスタム型コンバーターよりも優先、 **System.ComponentModel.TypeConverter**の 1 つの子のクラスです。 このとき、コンバーターでは値が保持されるように書式が追加されますが、プロパティ ページには表示されません。 **ConvertFrom**メソッドは文字列値を囲む角かっこを追加し、 **ConvertTo**メソッドでは、それらを削除します。  
  
 次のコードはカスタム型コンバーターのクラス定義です。  
  
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
  
## <a name="see-also"></a>参照  
 [カスタム アダプター構成デザイナー](../core/custom-adapter-configuration-designer.md)   
 [アダプター構成のカスタム ドロップダウン エディター](../core/custom-drop-down-editor-for-adapter-configuration.md)   
 [アダプター構成のカスタム モデル ダイアログ エディター](../core/custom-modal-dialog-editor-for-adapter-configuration.md)   
 [アダプターの高度な構成コンポーネント](../core/advanced-configuration-components-for-adapters.md)