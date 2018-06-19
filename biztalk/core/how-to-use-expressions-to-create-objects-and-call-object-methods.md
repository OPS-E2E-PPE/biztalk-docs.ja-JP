---
title: 式を使用してオブジェクトを作成する方法およびオブジェクトのメソッドを呼び出す |Microsoft ドキュメント
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
ms.openlocfilehash: b56cfa46098569863106485fef204f72b23a4ef5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256610"
---
# <a name="how-to-use-expressions-to-create-objects-and-call-object-methods"></a>オブジェクトを作成する式とオブジェクトのメソッドを呼び出す式の使用方法
オブジェクトの作成またはメソッドの呼び出しには、式を使用する必要があります。  
  
## <a name="creating-objects"></a>オブジェクトの作成  
 内のオブジェクトを構築する .NET クラスである型を持つ変数を作成する、**式**図形です。 .NET クラス変数のプロパティには、コンストラクターが含まれます。 既定のコンストラクターを使用する場合は、他の bool 型や int 型のような変数と同様に、変数を直接宣言するだけでかまいません。  
  
 キーワードを使用するパラメーターを受け取るコンス トラクターを使用する場合**新しい**オブジェクト クラス、およびパラメーターをかっこでと、その後。  
  
```  
new MyClass(myParam1, myParam2)  
```  
  
> [!CAUTION]
>  **既定のコンス トラクターを使用**コンス トラクターが存在するためには、実際には、一部のオブジェクトのプロパティが表示されません。 この場合、既定のコンストラクターが自動的に使用されます。別のコンストラクターを使用すると、エラーが発生する可能性があります。  
  
## <a name="invoking-methods"></a>メソッドの呼び出し  
 .NET クラス オブジェクトでメソッドを呼び出すには、オブジェクト参照にピリオド (.) とメソッドの名前を追加して、その後にパラメーターをかっこで囲んで続けます。  
  
```  
MyObject.MyMethod (param1)  
```  
  
## <a name="passing-and-using-messages-as-parameters"></a>パラメーターとしてのメッセージの引き渡しと使用  
 .NET クラスのメソッド呼び出しに対してパラメーターとしてメッセージを渡すには、まず、プロジェクト内のクラスを定義する Microsoft.XLANGs.BaseTypes.dll に参照を追加します。次に、XLANGMessage をメソッド シグネチャに使用します。  
  
 マルチパート メッセージの種類を参照すると、XLANGPart を使用してメッセージのさまざまな部分にアクセスできます。  
  
```  
MyMethod(XLANGMessage myMsg)  
{  
XLANGPart myPart = myMsg["Part1"];  
XmlDocument xmlDoc = (XmlDocument) myPart.RetrieveAs(typeof(XmlDocument));  
}  
```  
  
 呼び出し自体には、他のパラメーターと同じようにメッセージの名前を指定します。  
  
```  
MyObject.MyMethod(myMessage)  
```  
  
 XLANGPart としてメッセージの部分を渡すこともできます。  
  
## <a name="net-member-invocation"></a>.NET メンバーの呼び出し  
 パブリック メンバーにアクセスできます。ただし、メッセージ部分のメンバーへの直接アクセスはできません。 メッセージ部分のメンバーに直接アクセスするには、そのメンバーが、識別フィールドとして昇格されている必要があります。  
  
## <a name="comcom-component-invocation"></a>COM/COM+ コンポーネントの呼び出し  
 XLANGs は C# コードを生成します。 ユーザーが宣言した XLANGs 変数はすべて C# 変数として生成されます。 アトミック トランザクションの場合を除いて特別な動作はありません。 ときにサービス コンポーネント (を実装するクラスのインスタンスである、 **System.EnterpriseServices.ServicedComponent**) し、のみアトミックのスコープで宣言されて、XLANGs を生成し、実際の COM + DTC トランザクションを使用します。  
  
 アトミック スコープで左辺値として参照される変数 (値が書き込まれる変数) が外側のスコープで宣言された場合、ロールバックをサポートするためにその変数のクローンが作成されます。 ただし、オブジェクト (など、 **XmlDocument**)、.NET 関数呼び出しで、パラメーターとして渡されるときに内部で変更されることができ、オブジェクトに書き込まれています、これがロールバックされない正しく XLANGs が見逃したためです。 この場合の回避策は、このようなオブジェクトを参照パラメーターとして渡すことです。  
  
 つまり、コンポーネントは、他の C# プログラム内のコンポーネントと同様に動作する必要があります。  
  
## <a name="see-also"></a>参照  
 [BizTalk メッセージ コンテキストのプロパティについて](../core/about-biztalk-message-context-properties.md)