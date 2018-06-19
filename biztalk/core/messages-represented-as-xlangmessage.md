---
title: XLANGMessage として表されるメッセージ |Microsoft ドキュメント
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
ms.openlocfilehash: 345c0bbc2eae3289976738d25e76a8a377f86ea7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972272"
---
# <a name="messages-represented-as-xlangmessage"></a>XLANGMessage として表されるメッセージ
**XLANGMessage**オブジェクト、XLANG サービスで宣言されたメッセージ インスタンスを表します。 このオブジェクトを取得するには、メソッド呼び出しのパラメーターとしてメッセージに参照を渡します。 **XLANGPart**オブジェクトは、XLANG サービス内のメッセージ インスタンスに含まれるメッセージ部分を表します。 このオブジェクトは取得を受信側のパラメーター型がメソッドの呼び出しで一部の参照を渡すか**XLANGPart**の渡された参照を列挙することによって、または**XLANGMessage**です。  
  
 オーケストレーション メッセージ変数をユーザー コンポーネントに渡され、として受信した可能性があります、 **XLANGMessage**オブジェクト。 **XLANGMessage**オブジェクトは、部分やメッセージ プロパティへのアクセスを許可します。ユーザーが「保持」、 **XLANGMessage**し、それによって、宣言されたスコープの有効期間を拡張します。 その後、 **XLANGMessage**メソッドから返され、オーケストレーション内のメッセージ変数に割り当てられている可能性があります。  
  
## <a name="constructing-an-xlangmessage"></a>XLANGMessage の作成  
 構築するときに、 **XLANGMessage**ストリームの種類と、ストリームにはいずれかを実装する必要があります**IStreamFactory**するか、 **MemoryStream**です。 次のコード サンプルを構築する方法を示しています、 **XLANGMessage**:  
  
```  
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
  
 送信元メッセージを変換しないで新しいメッセージを作成することが必要な場合もあります。 型の変数を使用してこれを行う**System.Xml.XmlDocument**読み込みや、それ以外の場合に適切なコンテンツを構築します。 次の例では、文字列から XML を読み込むを使用して、 **LoadXml**メソッドの**XmlDocument**:  
  
```  
XmlVariable.LoadXml("<ns0:Root PONumber="047745351122111" xmlns:ns0="http://BTSHTTPSend.SimpleSchema"><MyChildRecord SubAttr1="Simple Attribute " /></ns0:Root>");  
XLANGMessage XmlMsg = XmlVariable;  
  
```  
  
 次の例を使用して、ファイルから XML を読み込んで、**ロード**メソッドの**XmlDocument**:  
  
```  
XmlVariable.Load("C:\MyData.xml");  
XLANGMessage XmlMsg = XmlVariable;  
  
```  
  
> [!NOTE]
>  サイズの大きいメッセージを構築する場合は、前のセクションで示したストリーミング メソッドのいずれかを使用または使用を検討して、**変換**オーケストレーション デザイナーでの図形です。  
  
## <a name="considerations-when-using-xlangmessage-and-xlangpart"></a>XLANGMessage および XLANGPart を使用する際の考慮事項  
 使用する場合**XLANGMessage**と**XLANGPart**ユーザー コードでは、次を検討してください。  
  
-   メッセージの一部としては渡さないように、 **XLANGPart**引数または戻り値の型の値**XLANGPart**です。 渡す必要があります**XLANGPart**部分の型として。 例:  
  
    ```  
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
  
     メッセージ自体を渡すこともできますとして、 **XLANGMessage**を使用して、 **XLANGMessage**添字演算子、関数呼び出しの内部で部分にアクセスします。 ただし、移動しないようにすれば、 **XLANGPart**関数呼び出しの有効期間を超えて拡張してその有効期間、コレクション内です。 代わりに、配置する必要があります、 **XLANGMessage**コレクション内で。 例:  
  
    ```  
    Void Test(XLANGMessage xlm)  
    {  
         try  
         {  
          XLANGPart xlp = xlm[0];  
          String sval = (String) xlp.RetrieveAs(typeof(string));  
         }  
         finally  
         {  
          Xlm.Dispose();  
         }  
    }  
    ```  
  
-   オーケストレーション パラメーターとして定義していない**XLANGMessage**または**XLANGPart**です。 メッセージを渡す必要がある場合は、メッセージの型のパラメーターを使用します。 部分を渡す必要がある場合は、代わりにメッセージを渡してから、部分を使用します。 部分の値だけが必要な場合は、部分の型を使用して部分を渡します。  
  
-   戻ることはありません、 **XLANGMessage**メソッド呼び出しのパラメーターです。 返す場合、 **XLANGMessage**に渡されるパラメーターとしを呼び出すことはできません、 **Dispose**メソッドで、パラメーター、メソッドの呼び出しの内部では、直感的に違反している有効期間の前提条件とそのも例外をスローします。 メッセージを渡すときに、 **XLANGMessage**パラメーターをユーザー コードは、メッセージを正常に参照されているメッセージがない特殊なコンテキストを参照します。 このコンテキストの有効期間は、オーケストレーション インスタンスの有効期間です。 これは、BizTalk Server からは、ユーザー コードがメッセージを保持しているかどうかがわからないためです。  
  
     オーケストレーション インスタンスが存在する場合、そのインスタンスで作成されたメッセージは有効ではないので、そのようなコレクションの有効期間は、インスタンスの有効期間以下でなければなりません。 ただし、を介して、メッセージが渡されるときに、ループ内でメッセージ参照を解放する場合、 **XLANGMessage**を呼び出すことができますし、オーケストレーション インスタンスと同じ有効期間を持つ引数**XLANGMessage.Dispose**参照を解放します。 さらに、ユーザー コード メソッドの内部場合は、 **XLANGMessage**パラメーターはローカルでのみ使用され、パラメーターの有効期間に含まれる関数呼び出しの呼び出すこともできます**XLANGMessage.Dispose**ルート コンテキストへの参照を解放しをもたらすため、対応するメッセージに、通常の有効期間動作します。 例:  
  
    ```  
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
  
     コレクションでは、xlm を配置するかどうかは、クラス自体がいる必要があります、 **Dispose**クリーンアップの方法です。 例:  
  
    ```  
    Public class A  
    {  
         Hashtable h = new Hashtable();  
         Public Test(XLANGMessage xlm)  
         {  
          h[xlm] = 1;  
         }  
         //You can have more methods here  
         Public Dispose()  
         {  
          foreach (XLANGMessage xlm in h.Keys)  
           Xlm.Dispose();  
         }  
    }  
    ```  
  
     呼び出して**A.Dispose**のコレクションを使用が終了したら**XLANGMessages**です。  
  
## <a name="see-also"></a>参照  
 [XSD スキーマとして表されるメッセージ](../core/messages-represented-as-xsd-schemas.md)   
 [.NET クラスとして表されるメッセージ](../core/messages-represented-as-net-classes.md)   
 [ユーザー コードでのメッセージの構築](../core/constructing-messages-in-user-code.md)