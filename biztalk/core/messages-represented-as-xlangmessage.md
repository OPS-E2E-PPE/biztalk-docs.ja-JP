---
title: XLANGMessage として表されるメッセージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aadca870-2f93-4be3-8733-a0cd3815add7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bad45a2bfae38cd38a50ae513f6c2fb336dce42d
ms.sourcegitcommit: bab8f4abca27edc45f9f4601ada6f3fc6a2b87cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2019
ms.locfileid: "67189096"
---
# <a name="messages-represented-as-xlangmessage"></a>XLANGMessage として表されるメッセージ
**XLANGMessage**オブジェクトは、XLANG サービスで宣言されたメッセージ インスタンスを表します。 このオブジェクトは、メソッドの呼び出しでパラメーターとしてメッセージへの参照を渡すことによって取得されます。 **XLANGPart**オブジェクトは、XLANG サービス内のメッセージ インスタンスに含まれるメッセージ部分を表します。 このオブジェクトは、受信側のパラメーター型がメソッドの呼び出しで一部の参照を渡すか取得**XLANGPart**の渡された参照を列挙することによって、または**XLANGMessage**します。  
  
 オーケストレーション メッセージ変数をユーザー コンポーネントに渡され、として受信したことがあります、 **XLANGMessage**オブジェクト。 **XLANGMessage**部分やメッセージ プロパティにアクセスするオブジェクトを使用できます。ユーザーが「保持」、 **XLANGMessage**し、それによって、宣言されたスコープの有効期間を拡張します。 その後、 **XLANGMessage**メソッドから返され、オーケストレーション メッセージ変数に割り当てられている可能性があります。  
  
## <a name="constructing-an-xlangmessage"></a>XLANGMessage の作成  
 構築するときに、 **XLANGMessage**ストリーム型と、ストリームには実装する必要があります**IStreamFactory**でも、 **MemoryStream**します。 次のコード サンプルを構築する方法を示しています、 **XLANGMessage**:  
  
```csharp
public class FileStreamFactory : IStreamFactory  
{  
    string _fname;  
  
    public FileStreamFactory(string fname)  
    {  
        _fname = fname;  
    }  
  
    public Stream CreateStream()  
    {  
        return new FileStream  
        (  
            _fname,  
            FileMode.Open,  
            FileAccess.Read,  
            FileShare.Read  
        );  
    }  
}  
  
public static void AssignStreamFactoryToPart(XLANGMessage msg)  
{  
    IStreamFactory sf = new FileStreamFactory( @”c:\data.xml” );  
    msg[0].LoadFrom( sf );  
}  
```  
  
 送信元メッセージを変換しないで新しいメッセージを作成する場合があります。 型の変数を使用してこれを行う**System.Xml.XmlDocument**読み込みや、それ以外の場合に適切なコンテンツを構築します。 次の例では、文字列から XML を読み込むを使用して、 **LoadXml**メソッドの**XmlDocument**:  
  
```csharp
XmlVariable.LoadXml("<ns0:Root PONumber="047745351122111" xmlns:ns0="http://BTSHTTPSend.SimpleSchema"><MyChildRecord SubAttr1="Simple Attribute " /></ns0:Root>");  
XLANGMessage XmlMsg = XmlVariable;  
  
```  
  
 次の例を使用して、ファイルから XML を読み込んで、**ロード**メソッドの**XmlDocument**:  
  
```csharp
XmlVariable.Load("C:\MyData.xml");  
XLANGMessage XmlMsg = XmlVariable;  
  
```  
  
> [!NOTE]
>  サイズの大きいメッセージを構築する場合は、前のセクションで示したストリーミング メソッドのいずれかを使用または使用を検討して、**変換**オーケストレーション デザイナーで図形。  
  
## <a name="considerations-when-using-xlangmessage-and-xlangpart"></a>XLANGMessage および XLANGPart を使用する場合の考慮事項  
 使用する場合**XLANGMessage**と**XLANGPart**ユーザー コードでは、次を検討してください。  
  
-   メッセージ部分としてを渡さないでください、 **XLANGPart**引数または戻り値の型の値**XLANGPart**します。 渡す必要があります**XLANGPart**部分の型として。 例 :  
  
    ```csharp
    Message String msg;  
    Class.Test(msg);  
    // or you can do the following  
    Messagetype mt  
    {  
         String part;  
    };  
    Message mt msg;  
    Class.Test(msg,part);  
  
    ```  
  
     メッセージ自体を渡すこともできますとして、 **XLANGMessage**を使用して、 **XLANGMessage**添字演算子、関数呼び出しの内側の部分にアクセスします。 配置しないで、ただし、 **XLANGPart**関数呼び出しの有効期間を超えて拡張してその有効期間コレクションでします。 代わりに、配置する必要があります、 **XLANGMessage**コレクション。 以下に例を示します。  
  
    ```csharp
    void Test(XLANGMessage xlm)
    {
         try
         {
             XLANGPart xlp = xlm[0];
             string sval = (string)xlp.RetrieveAs(typeof(string));
         }
         finally
         {
             xlm.Dispose();
         }
    }
    ```  
  
-   としてのオーケストレーション パラメーターを定義しない**XLANGMessage**または**XLANGPart**します。 メッセージを渡す場合は、メッセージを渡すメッセージ型のパラメーターを使用します。 部分を渡す場合は、代わりに、メッセージを渡すし、パーツを使用します。 部分の値のみたい場合は、部分を渡しますパート型を使用します。  
  
-   返されない、 **XLANGMessage**メソッド呼び出しのパラメーター。 値を返す場合、 **XLANGMessage** 、渡されるパラメーターとしを呼び出すことはできません、 **Dispose**メソッド、メソッド呼び出しの内部でパラメーターの直感的に違反している有効期間の想定し、それも例外をスローします。 メッセージを渡すときに、 **XLANGMessage**パラメーターをユーザー コードは、通常への参照されているメッセージを持たない特殊なコンテキストをメッセージを参照します。 このコンテキストの有効期間は、オーケストレーション インスタンスの有効期間です。 これは、BizTalk Server が知らないので、ユーザー コードがメッセージを保持するかどうか。  
  
     オーケストレーション インスタンスが終了すると、そのインスタンスに作成されたすべてのメッセージは無効になります、ため、このようなコレクションの有効期間のインスタンスの有効期間を以下になります。 ただし、メッセージを通じて渡されるときに、ループ内でメッセージの参照を解放する場合、 **XLANGMessage**を呼び出すことができ、オーケストレーション インスタンスと同じ有効期間を持つ引数**XLANGMessage.Dispose**の参照を解放します。 さらに、ユーザー コード メソッドで中、 **XLANGMessage**パラメーターはローカルでのみ使用し、関数呼び出しの呼び出すこともできますでパラメーターの有効期間が含まれる**XLANGMessage.Dispose**ルート コンテキストへの参照を解放し、バックアップ、通常の有効期間動作で、対応するメッセージを提供します。 以下に例を示します。  
  
    ```csharp
    void Test(XLANGMessage xlm)
    {
         try
         {
            //XLANGMessage is only used locally
         }
         finally
         {
            xlm.Dispose();
         }
    }
    ```  
  
     コレクションでは、xlm かどうかは、クラス自体が必要、 **Dispose**のクリーンアップ メソッド。 以下に例を示します。  
  
    ```csharp
    public class A
    {
         Hashtable h = new Hashtable();
         public void Test(XLANGMessage xlm)
         {
             h[xlm] = 1;
         }
         //You can have more methods here
         public void Dispose()
         {
             foreach (XLANGMessage xlm in h.Keys)
             {
                 xlm.Dispose();
             }
         }
    }
    ```  
  
     呼び出しは**A.Dispose**のコレクションが終了したら**XLANGMessages**します。  
  
## <a name="see-also"></a>関連項目  
 [XSD スキーマとして表されるメッセージ](../core/messages-represented-as-xsd-schemas.md)   
 [.NET クラスとして表されるメッセージ](../core/messages-represented-as-net-classes.md)   
 [ユーザー コードでのメッセージの構築](../core/constructing-messages-in-user-code.md)
