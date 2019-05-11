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
# <a name="advanced-configuration-components-for-adapters"></a>アダプターの高度な構成コンポーネント
BizTalk アダプター フレームワークには、カスタム ドロップダウン エディターやカスタムのモーダル ダイアログ エディター、カスタム型コンバーターがサポートしています。 これらのカスタム デザイン コンポーネントは、入力としてユーザー名とパスワードの情報を作成する際に特に便利です。  
  
 カスタム エディターか、構成スキーマで特定のデータ フィールド (要素または属性) の型コンバーターを呼び出すことができます。 Microsoft」の説明に従って[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ヘルプについては、エディターから派生する必要があります**System.Drawing.Design.UITypeEditor**から型コンバーターと**System.ComponentModel.TypeConverter**します。  
  
 エディターの最低限のオーバーライド、 **GetEditStyle**エディターの種類を指定するメソッド (**モーダル**ダイアログ ボックスで、**ドロップダウン**コントロール、または**None**上記の) および**EditValue**エディターを使用して値を変更するメソッド。  
  
 型コンバーターは通常よりも優先、 **ConvertFrom**、 **CanConvertFrom**、 **ConvertTo**、 **CanConvertTo**、 **GetStandardValues**、 **GetStandardValuesSupported**、および**GetStandardValuesExclusive**.NET Framework クラス ライブラリのメソッド。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [カスタム アダプター構成デザイナー](../core/custom-adapter-configuration-designer.md)  
  
-   [アダプター構成のカスタム ドロップダウン エディター](../core/custom-drop-down-editor-for-adapter-configuration.md)  
  
-   [アダプター構成のカスタム モデル ダイアログ エディター](../core/custom-modal-dialog-editor-for-adapter-configuration.md)  
  
-   [アダプター構成のカスタム型コンバーター](../core/custom-type-converter-for-adapter-configuration.md)