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
# <a name="advanced-configuration-components-for-adapters"></a>アダプターの高度な構成コンポーネント
BizTalk アダプター フレームワークは、カスタム ドロップダウン エディター、カスタム モーダル ダイアログ エディター、およびカスタム型コンバーターをサポートします。 これらのカスタム デザイン コンポーネントは、ユーザー名やパスワード情報を入力として受け取る場合に特に役に立ちます。  
  
 構成スキーマの特定のデータ フィールド (要素または属性) に対してカスタム エディターやカスタム型コンバーターを呼び出すことができます。 Microsoft」の説明に従って[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ヘルプ、エディターから派生する必要があります**System.Drawing.Design.UITypeEditor**と、型コンバーター **System.ComponentModel.TypeConverter**です。  
  
 エディターが最小限に抑えるよりも優先、 **GetEditStyle**エディターの種類を指定する方法 (**モーダル**ダイアログ ボックスで、**ドロップダウン**コントロール、または**None**上記の) および**EditValue**エディターでは、値を変更するメソッド。  
  
 実行する型コンバーターは通常よりも優先、 **ConvertFrom**、 **CanConvertFrom**、 **ConvertTo**、 **CanConvertTo**、 **GetStandardValues**、 **GetStandardValuesSupported**、および**GetStandardValuesExclusive**.NET Framework クラス ライブラリのメソッドです。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [カスタム アダプター構成デザイナー](../core/custom-adapter-configuration-designer.md)  
  
-   [アダプター構成のカスタム ドロップダウン エディター](../core/custom-drop-down-editor-for-adapter-configuration.md)  
  
-   [アダプター構成のカスタム モデル ダイアログ エディター](../core/custom-modal-dialog-editor-for-adapter-configuration.md)  
  
-   [アダプターの構成のカスタム型コンバーター](../core/custom-type-converter-for-adapter-configuration.md)