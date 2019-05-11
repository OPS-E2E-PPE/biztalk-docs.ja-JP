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
# <a name="custom-type-converter-for-adapter-configuration"></a>アダプターの構成のカスタム型コンバーター
カスタム型コンバーターをオーバーライドしてカスタム エディターをなど、 **System.ComponentModel.TypeConverter**その子のいずれかのクラス。 ここでは、コンバーターを追加する永続化する値の書式設定が [プロパティ] ページは表示されません。 **ConvertFrom**メソッドは文字列値を囲む角かっこを追加し、 **ConvertTo**メソッドがそれらを削除します。  
  
 次のコードでは、カスタム型コンバーターのクラス定義を示します。  
  
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
 [アダプターの詳細構成コンポーネント](../core/advanced-configuration-components-for-adapters.md)