---
title: 式を使用して、メッセージの割り当てを実行する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acadf37a102cedb9ddc902b4ca854d5e8458fa7c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333445"
---
# <a name="how-to-use-expressions-to-perform-message-assignments"></a>式を使用して、メッセージの割り当てを実行する方法
式を使用して、オーケストレーションでさまざまな方法でメッセージを操作することができます。  
  
## <a name="referring-to-message-fields"></a>メッセージのフィールドを参照します。  
 メッセージ名に次のように、フィールド名を追加して、メッセージの識別フィールドを参照することができます。  
  
```  
MyMsg.Amount  
```  
  
 この例で MyMsg はメッセージと基になる、メッセージの種類を識別フィールドとして識別されているフィールドになります。  
  
## <a name="assigning-to-messages-and-message-parts"></a>メッセージおよびメッセージ部分への割り当てください。  
 別のメッセージまたはメッセージ部分のメッセージ部分に直接メッセージを割り当てることができます。  
  
```  
MyMsg=IncomingMsg;  
MyMsg.Invoice=IncomingMsg.Invoice;  
```  
  
 この例では、請求書は、スキーマに基づくメッセージ部分です。  
  
 既に構築されたメッセージ プロパティを変更する場合: が受信されたメッセージなど、メッセージの構築図形では、2 番目の 1 つ目を割り当てることで新しいメッセージの構築および内で新しいメッセージのプロパティを変更する必要があります同じメッセージの構築図形。  
  
> [!NOTE]
>  参照するか、昇格された; 場合を除き、MyMsg.Invoice.MyField などのメッセージ フィールドに割り当てることはできません。のみ、参照するか、メッセージ全体、メッセージ部分、昇格させたメッセージ プロパティ、または識別フィールドに割り当てることができます。  
  
## <a name="adding-message-parts"></a>メッセージ部分の追加  
 既存のマルチパート メッセージに追加のパーツを追加するにを使用して、 **XLANGs.BaseTypes.XLANGMessage.AddPart**メソッド。 これを行うには、次の操作を行います。  
  
-   作成、C#プロジェクトに参照を追加して**Microsoft.XLANGs.BaseTypes**します。  
  
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
  
-   BizTalk プロジェクトで、パブリック クラスと呼び出しへの参照を追加、 **AddPart**からメソッド、**式**図形の次のように、オーケストレーションで。  
  
    ```  
    MyAddPartHelper.AddPart(myMessage, myStringObject, “StringObject1”);  
    ```  
  
> [!NOTE]
>  メッセージ部分としてシリアル化できないオブジェクト、またはカスタムの書式設定されたオブジェクトを追加することはできません。 使用したその他のパーツを追加する前にすべての静的部分を初期化する必要があります、 **AddPart**メソッド。 ステートメントを作成、メッセージの内部でのみ、メッセージに任意の部分を追加できます。 ステートメントを作成、メッセージの外部で他のパーツを追加することはサポートされません。  
  
## <a name="retrieving-message-parts"></a>メッセージ部分の取得  
 使用して既存のマルチパート メッセージからメッセージ部分を取得することができます、 **RetrieveAs**メソッドから**Microsoft.XLANGs.BaseTypes**します。 これを行うには、次の操作を行います。  
  
-   作成、C#プロジェクトに参照を追加して**Microsoft.XLANGs.BaseTypes**します。  
  
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
    >  **RetrieveAs**メソッドは、名、インデックスを使用してメッセージ部分の取得をサポートしています。  
  
-   BizTalk プロジェクトで、パブリック クラスと呼び出しへの参照を追加、 **GetPart**からメソッド、**式**図形の次のように、オーケストレーションで。  
  
    ```  
    sPart = (System.String) MyAddPartHelper.GetPart(msg, "StringObject1" , typeof(System.String));  
    //sPart is a type of System.String  
    sPart = (System.String) MyAddPartHelper.GetPart(msg, 1, typeof(System.String));  
    //Retriving the message part with index = 1  
    ```  
  
## <a name="message-part-context-property-access"></a>メッセージ部分コンテキスト プロパティのアクセス  
 メッセージ部分には、メッセージ コンテキストから別のコンテキストがあります。 設定すると、スキーマ エディターでのメッセージ部分のコンテキスト プロパティを構築することができます、 **Property Schema Base**プロパティに関連付けられている要素を**PartContextPropertyBase します。**  
  
 アクセスは、ような式からのメッセージ プロパティと同様です。  
  
```  
Msg.PartName(myPartContextProperty)  
```  
  
 以下に例を示します。  
  
```  
Str=Msg.PartName(myPartContextProperty); //assumes myPartContextProperty is of type string  
```  
  
## <a name="xlangmessage-context-property-access"></a>XLANGMessage のコンテキスト プロパティのアクセス  
 メッセージ プロパティにアクセスしたい場合、 **XLANGMessage**インターフェイス、コードでは、型のパラメーターとして、メッセージを渡すことができます**Microsoft.XLANGs.BaseTypes.XLANGMessage**メソッド使用して、式図形から、 **Microsoft.XLANGs.BaseTypes.XLANGMessage**メソッド**SetPropertyValue**と**GetPropertyValue**を実現するにはこれ。 これを行うには、次の操作を行います。  
  
-   作成、C#プロジェクトに参照を追加して**Microsoft.XLANGs.BaseTypes**と**Microsoft.BizTalk.GlobalPropertySchemas**します。  
  
-   ようなコードを使用してコンテキスト プロパティへのアクセスの下。  
  
    ```  
    MyMsg.GetPropertyValue(typeof(BTS.MessageID));  
    MyMsg.SetPropertyValue(typeof(MIME.IsMultipartRelated), true);  
    ```  
  
> [!NOTE]
>  取得または、独自のカスタム コンテキスト プロパティを設定する場合は、アセンブリへの参照には、プロパティ スキーマが含まれていますを追加するか、プロパティ スキーマ プロジェクトへの参照を追加する必要があります、C#プロジェクト。  
  
## <a name="assigning-to-message-properties"></a>メッセージのプロパティへの割り当てください。  
 メッセージ プロパティに値を割り当てることができます。  
  
```  
MyMessage(MySchemaNamespace.MyProperty)=True;  
```  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してくださいし、MIME マルチパート メッセージのプロパティに値を割り当てることができます。  
  
```  
Message_Out.MessagePart_1(MIME.FileName)="document.doc";  
```  
  
> [!NOTE]
>  BizTalk メッセージは、メッセージのコンテキストとメッセージ部分で構成されます。 取得したり、メッセージ コンテキスト プロパティを設定する前にまずメッセージ部分を初期化する必要があります。それ以外の場合、XLANG コンパイル中にエラーが表示されます。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションでメッセージの使用](../core/using-messages-in-orchestrations.md)   
 [ユーザー コードでのメッセージの構築](../core/constructing-messages-in-user-code.md)   