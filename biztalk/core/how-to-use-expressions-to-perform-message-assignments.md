---
title: "式を使用して、メッセージの割り当てを実行する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, distinquished fields
- orchestrations, expressions
- messages, manipulating
- messages, assigning messages
- messages, expressions
- messages, message parts
- orchestrations, messages
- messages, components
ms.assetid: 9989caf5-012c-4fc4-b5d8-981ca9a69f43
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f423e1b797cfff95bae1d9b1dd862d28210cd26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-expressions-to-perform-message-assignments"></a>式を使用して、メッセージの割り当てを実行する方法
式を使用して、さまざまな方法でオーケストレーションのメッセージを操作できます。  
  
## <a name="referring-to-message-fields"></a>メッセージ フィールドの参照  
 次のようにフィールド名をメッセージ名に追加して、メッセージの識別フィールドを参照できます。  
  
```  
MyMsg.Amount  
```  
  
 この例の場合、MyMsg はメッセージを表しています。Amount は、MyMsg の基になるメッセージの種類の識別フィールドとして認識されているフィールドです。  
  
## <a name="assigning-to-messages-and-message-parts"></a>メッセージとメッセージ部分への割り当て  
 メッセージを別のメッセージに (または、メッセージ部分を他のメッセージ部分に) 直接割り当てることができます。  
  
```  
MyMsg=IncomingMsg;  
MyMsg.Invoice=IncomingMsg.Invoice;  
```  
  
 この例の場合、Invoice は、スキーマに基づくメッセージ部分です。  
  
 既に構築されたメッセージのプロパティを変更する場合などが受信されたメッセージなど、メッセージの構築図形で 1 秒に 1 つ目を割り当てることで新しいメッセージの構築および内で新しいメッセージのプロパティを変更する必要があります同じメッセージの構築図形です。  
  
> [!NOTE]
>  メッセージ フィールドを昇格させた場合を除き、MyMsg.Invoice.MyField などのメッセージ フィールドに対する参照や割り当ては行えません。メッセージ全体、メッセージ部分、昇格させたメッセージ プロパティ、または識別フィールドに対する参照および割り当てのみ行えます。  
  
## <a name="adding-message-parts"></a>メッセージ部分の追加  
 使用して既存のマルチパート メッセージに追加部分を追加することができます、 **XLANGs.BaseTypes.XLANGMessage.AddPart**メソッドです。 これを行うには、次の操作を行います。  
  
-   C# プロジェクトを作成しへの参照を追加**Microsoft.XLANGs.BaseTypes**です。  
  
-   次のようなパブリック クラスを実装します。  
  
    ```  
    public class MyAddPartHelper  
    {  
         public static void AddPart(XLANGMessage msg, object part, String partName)  
         {  
              msg.AddPart(part, partName);  
         }  
    }  
    ```  
  
     3 つのオーバー ロードされたメソッドがある**Microsoft.XLANGs.BaseTypes.AddPart**:  
  
    ```  
    public void AddPart(object part, String partName);  
    public void AddPart(XLANGPart part);  
    public void AddPart(XLANGPart part, String partName);  
    ```  
  
-   BizTalk プロジェクトで、パブリック クラスと呼び出しへの参照を追加、 **AddPart**メソッドから、**式**図形の次のように、オーケストレーションで。  
  
    ```  
    MyAddPartHelper.AddPart(myMessage, myStringObject, “StringObject1”);  
    ```  
  
> [!NOTE]
>  メッセージ部分としてシリアル化できないオブジェクトまたはカスタムの書式設定されたオブジェクトを追加することはできません。 すべての静的部分を使用したその他のパーツを追加する前に初期化する必要があります、 **AddPart**メソッドです。 メッセージに任意の部分を追加できるのは、そのメッセージの construct ステートメント内においてのみです。 メッセージの construct ステートメント外では、追加のメッセージ部分の追加はサポートされていません。  
  
## <a name="retrieving-message-parts"></a>メッセージ部分の取得  
 使用して、既存のマルチパート メッセージからメッセージ部分を取得することができます、 **RetrieveAs**メソッドから**Microsoft.XLANGs.BaseTypes**です。 これを行うには、次の操作を行います。  
  
-   C# プロジェクトを作成しへの参照を追加**Microsoft.XLANGs.BaseTypes**です。  
  
-   次のようなパブリック クラスを実装します。  
  
    ```  
    Public class MyAddPartHelper  
    {  
         public static Object GetPart(XLANGMessage msg, string sName, Type t)  
         {  
              XLANGPart p =  msg[sName];  
              return p.RetrieveAs(t);  
         }  
         public static Object GetPart(XLANGMessage msg, int partIndex, Type t)  
         {  
               XLANGPart p = msg[partIndex];  
               return p.RetrieveAs(t);  
          }  
    }  
    ```  
  
    > [!NOTE]
    >  **RetrieveAs**メソッドは、インデックスと名前によって取得中のメッセージ部分をサポートしています。  
  
-   BizTalk プロジェクトで、パブリック クラスと呼び出しへの参照を追加、 **GetPart**メソッドから、**式**図形の次のように、オーケストレーションで。  
  
    ```  
    sPart = (System.String) MyAddPartHelper.GetPart(msg, "StringObject1" , typeof(System.String));  
    //sPart is a type of System.String  
    sPart = (System.String) MyAddPartHelper.GetPart(msg, 1, typeof(System.String));  
    //Retriving the message part with index = 1  
    ```  
  
## <a name="message-part-context-property-access"></a>メッセージ部分のコンテキスト プロパティのアクセス  
 メッセージ部分には、メッセージ コンテキストとは別のコンテキストがあります。 設定すると、スキーマ エディターでのメッセージ部分のコンテキスト プロパティを構築することができます、 **Property Schema Base**に関連付けられている要素のプロパティを**PartContextPropertyBase です。**  
  
 アクセスは、メッセージ プロパティと似ています。次のような式を使用します。  
  
```  
Msg.PartName(myPartContextProperty)  
```  
  
 例:  
  
```  
Str=Msg.PartName(myPartContextProperty); //assumes myPartContextProperty is of type string  
```  
  
## <a name="xlangmessage-context-property-access"></a>XLANGMessage のコンテキスト プロパティのアクセス  
 メッセージ プロパティにアクセスしたい場合、 **XLANGMessage**インターフェイス、コードでは、型のパラメーターとしてメッセージを渡すことができます**Microsoft.XLANGs.BaseTypes.XLANGMessage**メソッド式図形およびしを使用してから、 **Microsoft.XLANGs.BaseTypes.XLANGMessage**メソッド**SetPropertyValue**と**GetPropertyValue**を実現するにはこれ。 これを行うには、次の操作を行います。  
  
-   C# プロジェクトを作成しへの参照を追加**Microsoft.XLANGs.BaseTypes**と**Microsoft.BizTalk.GlobalPropertySchemas**です。  
  
-   次のようなコードを使用して、コンテキスト プロパティにアクセスします。  
  
    ```  
    MyMsg.GetPropertyValue(typeof(BTS.MessageID));  
    MyMsg.SetPropertyValue(typeof(MIME.IsMultipartRelated), true);  
    ```  
  
> [!NOTE]
>  独自のカスタム コンテキスト プロパティを取得または設定するには、C# プロジェクトで、プロパティ スキーマ プロジェクトに参照を追加するか、そのプロパティ スキーマが含まれているアセンブリに参照を追加する必要があります。  
  
## <a name="assigning-to-message-properties"></a>メッセージ プロパティへの割り当て  
 値をメッセージ プロパティに割り当てることができます。  
  
```  
MyMessage(MySchemaNamespace.MyProperty)=True;  
```  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、マルチパート メッセージの MIME プロパティに対して、値の割り当てや参照を行うことができます。  
  
```  
Message_Out.MessagePart_1(MIME.FileName)="document.doc";  
```  
  
> [!NOTE]
>  BizTalk メッセージは、メッセージ コンテキストとメッセージ部分で構成されます。 メッセージ コンテキスト プロパティを取得または設定するには、まずメッセージ部分を初期化する必要があります。初期化をしないと、XLANG コンパイル時にエラーが発生します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションでメッセージの使用](../core/using-messages-in-orchestrations.md)   
 [ユーザー コードでメッセージの構築](../core/constructing-messages-in-user-code.md)   