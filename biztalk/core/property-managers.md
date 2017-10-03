---
title: "プロパティ マネージャー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 823352a0-e397-464a-a163-1dbf8feea8d7
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6aff8fc39612ed79e6e9602ed39874d014bb4a11
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="property-managers"></a>プロパティ マネージャー
プロパティ マネージャーを使用すると、XSD 表記のスキーマの要素および属性にカスタム プロパティ (通常、XSD 注釈として) を追加できます。[プロパティ] ウィンドウを拡張して、拡張機能に関連付けられているカスタム プロパティを含めることもできます。  
  
 プロパティ マネージャーを実装するオブジェクト、 **IPropertyManager**インターフェイスを呼び出すことによってこれへの参照を取得**IExtension.GetPropertyManager**を渡すと、 **ITreeNode**入力パラメーターとしてオブジェクト。 通常、拡張機能は、1 つ**IPropertyManager**ごとにオブジェクト**ITreeNode**オブジェクト。 プロパティ マネージャーはそのためのカスタム プロパティのコレクションを**ITreeNode**オブジェクト。  
  
 カスタム プロパティで表される、 **System.ComponentModel.PropertyDescriptor**によって返されるコレクションから取得できるオブジェクト、 **IPropertyManager.GetProperties**メソッドです。  
  
 使用して**PropertyDescriptor**拡張機能に関連付けられているカスタム プロパティを表すオブジェクトには、Microsoft との統合が容易になります。[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウ。 ときに**PropertyDescriptor**オブジェクトを使用して、簡単に BizTalk エディターで、拡張機能のカスタム プロパティを [プロパティ] ウィンドウに既に統合されている標準のノード プロパティのセットに統合します。 表示名、表示値、コントロールのプロパティの型、プロパティの説明、およびプロパティのカテゴリなどのカスタム プロパティの情報を得た、 **PropertyDescriptor**オブジェクト。  
  
 カスタム プロパティは、スキーマ ツリーの関連ノードに対応する要素の注釈要素内の要素の属性として、XSD 表記のスキーマに保存されます。 スキーマ ツリー ノードの各カスタム プロパティは、一般的な要素の属性に指定できます。また、各カスタム プロパティは、固有の関連付けられた要素を持つこともできます。  
  
## <a name="see-also"></a>参照  
 [BizTalk エディターの拡張](../core/extending-biztalk-editor.md)