---
title: 式を使用してオブジェクトを作成する方法と、オブジェクトのメソッドを呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, parameters
- Expression shape [Orchestration Designer], calling objects
- Expression shape [Orchestration Designer], parameters
- Expression shape [Orchestration Designer], passing messages
- orchestrations, methods
- Expression shape [Orchestration Designer], calling methods
- orchestrations, objects
- Expression shape [Orchestration Designer], warning
- Use Default Constructor property
- .NET member invocation
ms.assetid: b6af67eb-8ba5-4c95-9b63-26ebb6617af0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adf0be16b7fa0fc78788386159672ce94823bbcc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383440"
---
# <a name="how-to-use-expressions-to-create-objects-and-call-object-methods"></a>式を使用してオブジェクトを作成する方法と、オブジェクトのメソッドを呼び出す
オブジェクトを作成またはメソッドの呼び出し式を使用する必要があります。  
  
## <a name="creating-objects"></a>オブジェクトを作成します。  
 内のオブジェクトを構築する .NET クラスである型を持つ変数を作成する、**式**図形。 .NET クラス変数のプロパティには、コンス トラクターが含まれます。 既定のコンス トラクターを使用する場合、変数を宣言するだけ bool 型または整数のいずれかのように、その他の任意の変数と同様に直接  
  
 キーワードを使用するパラメーターを受け取るコンス トラクターを使用する場合**新しい**、その後にオブジェクトのクラスとパラメーターをかっこで。  
  
```  
new MyClass(myParam1, myParam2)  
```  
  
> [!CAUTION]
>  **既定のコンス トラクターを使用**コンス トラクターを指定することは、実際には、一部のオブジェクト プロパティが表示されません。 この場合、既定のコンス トラクターが自動的に使用して、別のコンス トラクターを使用しようとした場合、エラーが生成されます。  
  
## <a name="invoking-methods"></a>メソッドの呼び出し  
 .NET クラス オブジェクトでメソッドを呼び出すには、パラメーターをかっこで囲まれた後に、オブジェクト参照にピリオドとメソッドの名前を追加します。  
  
```  
MyObject.MyMethod (param1)  
```  
  
## <a name="passing-and-using-messages-as-parameters"></a>渡すと、メッセージをパラメーターとして使用  
 .NET クラスで、メッセージをパラメーターとしてメソッドの呼び出しに渡すするには、は、まずプロジェクト、クラスを定義する Microsoft.XLANGs.BaseTypes.dll に参照を追加し、XLANGMessage メソッド シグネチャでの型を使用しています。  
  
 マルチパート メッセージの種類を参照するには、xlangpart を使用して、メッセージのさまざまな部分にアクセスすることができます。  
  
```  
MyMethod(XLANGMessage myMsg)  
{  
XLANGPart myPart = myMsg["Part1"];  
XmlDocument xmlDoc = (XmlDocument) myPart.RetrieveAs(typeof(XmlDocument));  
}  
```  
  
 呼び出し自体で単純に名前を指定するメッセージのと同様、その他のパラメーター。  
  
```  
MyObject.MyMethod(myMessage)  
```  
  
 Xlangpart としてメッセージ部分を渡すこともできます。  
  
## <a name="net-member-invocation"></a>.NET メンバーの呼び出し  
 メッセージ部分のメンバーに直接アクセスする場合を除くパブリック メンバーにアクセスできます。 メッセージ部分のメンバーに直接アクセスを識別フィールドとして昇格する必要があります。  
  
## <a name="comcom-component-invocation"></a>COM と COM + コンポーネントの呼び出し  
 XLANGs 生成C#コード。 すべてのユーザーが宣言した XLANGs 変数として生成C#変数。 アトミック トランザクションの場合を除く特別な動作はありません。 サービス コンポーネント (実装するクラスのインスタンスである、 **System.EnterpriseServices.ServicedComponent**) だけに、アトミックのスコープで宣言された、XLANGs を生成し、実際の COM + DTC トランザクションを使用します。  
  
 左辺値として変数が参照されているかどうか (つまりに書き込まれます) でアトミックのスコープが外側のスコープで宣言は、ロールバックをサポートするために、変数のクローンを作成します。 ただし、オブジェクト (など、 **XmlDocument**) でのパラメーターとして渡されるときに、.NET 関数呼び出しの内部での修正、およびに書き込まれたオブジェクトをこれはロールバックしない正しく XLANGs を見逃すためです。 回避策は、この場合、ref パラメーターとしてこのようなオブジェクトを渡すには。  
  
 一番下の行が他のようにコンポーネントが動作する必要があるC#プログラム。  
  
## <a name="see-also"></a>参照  
 [BizTalk メッセージ コンテキストのプロパティについて](../core/about-biztalk-message-context-properties.md)