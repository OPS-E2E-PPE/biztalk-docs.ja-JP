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
# <a name="property-managers"></a>プロパティ マネージャー
プロパティ マネージャーは、要素に (通常、XSD 注釈) としてカスタム プロパティを追加する拡張機能を許可して、カスタム プロパティは、[プロパティ] ウィンドウを拡張するほか、スキーマの XSD 表記内の属性に関連付けられている、拡張機能。  
  
 プロパティ マネージャーは、実装するオブジェクト、 **IPropertyManager**される参照は呼び出すことによって取得インターフェイス**IExtension.GetPropertyManager**、渡すと、 **ITreeNode**入力パラメーターとしてオブジェクト。 1 つが、拡張機能では、通常は**IPropertyManager**オブジェクトごとに**ITreeNode**オブジェクト。 プロパティ マネージャーはそのため、カスタム プロパティのコレクションを**ITreeNode**オブジェクト。  
  
 によってカスタム プロパティが表される、 **System.ComponentModel.PropertyDescriptor**オブジェクトによって返されるコレクションから取得できますが、 **IPropertyManager.GetProperties**メソッド。  
  
 使用して**PropertyDescriptor** 、拡張機能に関連付けられているカスタム プロパティを表すオブジェクトには、Microsoft との統合が容易に[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウ。 ときに**PropertyDescriptor**オブジェクトを使用して、簡単に BizTalk エディターの拡張機能のカスタム プロパティを一連のプロパティ ウィンドウに既に統合されている標準的なノードのプロパティに統合します。 表示名、表示値、コントロールのプロパティの型、プロパティの説明、およびプロパティのカテゴリなどのカスタム プロパティの情報がから取得した、 **PropertyDescriptor**オブジェクト。  
  
 カスタム プロパティは、スキーマ ツリー内の関連ノードに対応する要素の注釈要素内の要素の属性として、スキーマの XSD 表記で格納されます。 各カスタム プロパティ スキーマのツリー ノードの一般的な要素の属性に指定できますか、または、それぞれ独自の関連付けられている要素を持つことができます。  
  
## <a name="see-also"></a>参照  
 [BizTalk エディターの拡張](../core/extending-biztalk-editor.md)