---
title: .NET クラスとして表されるメッセージ |Microsoft ドキュメント
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
ms.openlocfilehash: 16f0ea95f02de6e9fda411fa0183569dc0779033
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263394"
---
# <a name="messages-represented-as-net-classes"></a>.NET クラスとして表されるメッセージ
この方法ではまず、メッセージの種類を定義する .NET クラスを作成します。 このクラスには、既定のコンストラクターを指定する必要があります。指定しなかった場合、それを使用するオーケストレーションがコンパイルされません。 このようなクラスの簡単な例を次に示します。  
  
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
  
 上の例の ShortField は PropertyNamespace.ShortPropertyName 型のプロパティとなります。このプロパティの基になる型は、ShortField と同じ Int16 型である必要があります。 StrField は、識別フィールド、および PropertyNamespace.StringPropertyName 型のプロパティとなります。このプロパティの基になる型は、StrField と同じ String 型である必要があります。 通常、PropertyNamespace.StringPropertyName と PropertyNamespace.ShortPropertyName は、BizTalk スキーマ エディターを使用してスキーマ プロパティとして作成されます。C# プロジェクトでは、これらのスキーマ プロパティが含まれているアセンブリを参照する必要があります。  
  
> [!NOTE]
>  C# プログラミング言語では、属性名の末尾の "Attribute" は省略可能です。したがって、末尾の "Attribute" を省略した "DistinguishedField" や "Property" を代わりに使用できます。 例を次に示します。  
  
```  
[Property(typeof(PropertyNamespace.StringPropertyName))]  
[DistinguishedField]  
public string StrField;  
```  
  
 メッセージの種類をいったん定義したら、この種類のメッセージを新規作成するコードをオーケストレーションに記述するのは非常に簡単です。 内で、**メッセージの構築**図形、単純な式を記述するの新しいメッセージを作成、 **MsgClass** 、上記のように入力し、Distinguished となるフィールドに値を割り当てます(既定値をオーバーライドする場合) のフィールドです。 MyMsg はオーケストレーション メッセージ変数で、種類は NetClass.MsgClass です。  
  
```  
MyMsg = new NetClass.MsgClass();  
MyMsg.StrField = "Changed Value";  
MyMsg.IntField = 15;  
```  
  
## <a name="see-also"></a>参照  
 [XSD スキーマとして表されるメッセージ](../core/messages-represented-as-xsd-schemas.md)   
 [XLANGMessage として表されるメッセージ](../core/messages-represented-as-xlangmessage.md)   
 [ユーザー コードでメッセージの構築](../core/constructing-messages-in-user-code.md)