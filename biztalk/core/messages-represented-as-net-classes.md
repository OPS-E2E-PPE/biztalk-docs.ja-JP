---
title: メッセージは、.NET クラスとして表される |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, expressions
- orchestrations, filters
ms.assetid: cdbea200-552e-4734-a370-2f93da07ea81
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a01e0c5834e117a16541f8dee45218285f05e0f4
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531183"
---
# <a name="messages-represented-as-net-classes"></a>.NET クラスとして表されるメッセージ
このアプローチでは、最初、メッセージの種類を定義する .NET クラスを作成する必要があります。 クラスに既定のコンス トラクターが必要か、それを使用して、オーケストレーションはコンパイルされません。 このようなクラスの単純な例を次に示します。  
  
```  
using System;  
using Microsoft.XLANGs.BaseTypes;  
Using PropertyNamespace;  
  
namespace NetClass  
{  
   [Serializable]  
   public class MsgClass  
   {  
      public MsgClass()  
      {  
         StrField = "OK";  
         IntField = 1;  
         ShortField = 1;  
      }  
  
      [PropertyNamespace.ShortPropertyName]  
      public Int16 ShortField;  
  
      [PropertyAttribute(typeof(PropertyNamespace.StringPropertyName)]  
      [DistinguishedFieldAttribute()]  
      public String StrField;  
  
      [DistinguishedFieldAttribute()]  
      public int IntField;  
   }  
}  
```  
  
 上記の例では、shortfield と同じになります PropertyNamespace.ShortPropertyName 型のプロパティとプロパティの基になる型が型である Int16 する必要があります。 StrField は、識別フィールドおよび PropertyNamespace.StringPropertyName 型のプロパティの両方には、プロパティの基になる型が文字列、StrField の型の型を指定する必要があります。 通常 PropertyNamespace.StringPropertyName と PropertyNamespace.ShortPropertyName は BizTalk スキーマ エディターを使用として作成、スキーマのプロパティと、C#プロジェクト。  
  
> [!NOTE]
>  C#プログラミング言語、属性名の属性の終了は省略可能で、属性の終わりを省略して DistinguishedField"や"プロパティの代わりに使用できるようにします。 例を次に示します。  
  
```  
[Property(typeof(PropertyNamespace.StringPropertyName))]  
[DistinguishedField]  
public string StrField;  
```  
  
 メッセージの種類を定義すると後、は、非常に簡単にこの型の新しいメッセージを作成するオーケストレーションでコードを記述します。 内で、**メッセージの構築**図形、単純な式を記述するは新しいメッセージを作成する、 **MsgClass** 、上記の種類し、Distinguished となるフィールドに値を割り当てるフィールド (既定値を上書きする場合)。 MyMsg はオーケストレーション メッセージ変数の種類は NetClass.MsgClass であることに注意してください。  
  
```  
MyMsg = new NetClass.MsgClass();  
MyMsg.StrField = "Changed Value";  
MyMsg.IntField = 15;  
```  
  
## <a name="see-also"></a>参照  
 [XSD スキーマとして表されるメッセージ](../core/messages-represented-as-xsd-schemas.md)   
 [XLANGMessage として表されるメッセージ](../core/messages-represented-as-xlangmessage.md)   
 [ユーザー コードでのメッセージの構築](../core/constructing-messages-in-user-code.md)