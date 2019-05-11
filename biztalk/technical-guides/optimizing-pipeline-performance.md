---
title: パイプラインのパフォーマンスの最適化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5137747-0dcf-4c96-90a7-01afb92f56a6
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34d83aad4a393df0cc0532545d5518fff9e0f8e5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291352"
---
# <a name="optimizing-pipeline-performance"></a>パイプラインのパフォーマンスを最適化します。
このトピックでは、パイプラインでのパフォーマンスを最適化するためのガイドラインを説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション。  
  
## <a name="best-practices-for-optimizing-performance-of-biztalk-server-pipelines"></a>BizTalk Server パイプラインのパフォーマンスを最適化するためのベスト プラクティス  
  
1. パイプライン コンポーネントは、パフォーマンスに大きな影響を与えるため、(たとえば、パススルー パイプライン コンポーネントは XML アセンブラ/逆アセンブラ パイプライン コンポーネントをより最大 30% を実行します)、カスタム パイプライン コンポーネントが実行を確認最適に実装する前に、展開でします。 BizTalk アプリケーションの全体的なパフォーマンスを最大化したい場合は、カスタム パイプラインのパイプライン コンポーネントの数を最小限に抑えます。  
  
2. パフォーマンスを向上できます全体的なパイプライン コンポーネントでメッセージの永続化の頻度を減らすことで、冗長性を最小化するコンポーネントをコーディングしています。 すべてのカスタム アセンブリ具体的には、カスタムの追跡のコンポーネントと同様のパフォーマンスに悪影響を及ぼす可能性があるアーティファクト テストするくださいとは別に、システムが最大能力で作業する場合、その動作を観察して、検索の高負荷条件下で任意のボトルネックの可能性。  
  
3. パイプライン コンポーネント内で受信メッセージを確認する必要がある場合にメモリを使用してドキュメント全体を読み込みを避けるため、 **XmlDocument**オブジェクト。 インスタンスで必要な領域の量、 **XmlDocument**を読み込むし、XML ドキュメントのメモリ内表現を作成するクラスは、最大 10 倍の実際のメッセージ サイズ。 メッセージを読み取るために使用する必要があります、 **XmlTextReader**オブジェクトと共に、次のクラスのインスタンス。  
  
   -   **VirtualStream (Microsoft.BizTalk.Streaming.dll)** -このクラスのソース コードが次のように、パイプラインの SDK の下の 2 つの場所にあります。\Samples\pipelines\arbitraryxpathpropertyhandler および \samples\pipelines\schemaresolvercomponent\schemaresolverflatfiledasm します。  
  
   -   **ReadOnlySeekableStream (Microsoft.BizTalk.Streaming.dll)** します。  
  
   -   **SeekAbleReadOnlyStream** -このクラスのソース コードが次のように、パイプラインの SDK の下の 2 つの場所にあります。\Samples\pipelines\arbitraryxpathpropertyhandler および \samples\pipelines\schemaresolvercomponent\schemaresolverflatfiledasm します。  
  
4. PassThruReceive パイプラインおよび可能な限り PassThruTransmit 標準パイプラインを使用します。 任意のパイプライン コンポーネントが含まれていないされ、メッセージの処理を実行しないでください。 このため、受信または送信メッセージの最大のパフォーマンスを支えます。 バイナリ メッセージを送信する必要がある場合は、バイナリのドキュメントを BizTalk メッセージ ボックスと送信ポートで PassThruTransmit パイプラインに発行する必要がある場合は、受信場所で PassThruReceive パイプラインを使用できます。 PassThruTransmit パイプラインで、メッセージは、フォーマットされているし、送信する準備ができている場合、オーケストレーションにバインドする物理送信ポートを使用することもできます。 次の操作のいずれかを実行する必要がある場合に、別のアプローチを使用する必要があります。  
  
   - 受信 XML またはフラット ファイル メッセージのコンテキストのプロパティを昇格させます。  
  
   - 受信場所内でマップを適用します。  
  
   - メッセージにサブスクライブするオーケストレーションでマップを適用します。  
  
   - メッセージをサブスクライブする送信ポートでマップを適用します。  
  
     これらの操作を行うためには、プローブし受信パイプライン内のドキュメントの種類を検出し、MessageType のコンテキスト プロパティに (名前空間 #root 名の) 値を代入する必要があります。 この操作は、通常、Xml 逆アセンブラー コンポーネント (XmlDasmComp) などの逆アセンブラー コンポーネントまたはフラット ファイル逆アセンブラー コンポーネント (FFDasmComp) して行います。 この場合は、標準 (たとえば、XmlReceive パイプライン) または標準またはカスタム逆アセンブラー コンポーネントを含むカスタム パイプラインを使用する必要があります。  
  
5. できる限り遅くリソースを取得し、できるだけ早期にリリースします。 たとえば、データをデータベースにアクセスする必要がある場合は、できるだけ遅く接続を開くして、できるだけ早く閉じます。 C# のステートメントを使用して、破棄可能なオブジェクトを暗黙的にリリースを使用して、または、オブジェクトを明示的に破棄するには、try – catch – finally ステートメントの最後にブロックします。 すると、コンポーネントをデバッグする単純なソース コードをインストルメント化します。  
  
6. 厳密に、メッセージの処理を高速化する必要はありませんが、パイプラインからコンポーネントを削除します。  
  
7. 受信パイプラインでは、内部で (オーケストレーション、送信ポート) のメッセージのルーティング、メッセージ コンテキスト プロパティ (送信ポート) の下位変換の必要な場合にのみメッセージ コンテキストに項目を昇格する必要があります。  
  
8. メッセージを表示してメタデータを含める必要があると、ルーティングまたは降格のための使用をメタデータを使用しない場合、 **IBaseMessageContext.Write**メソッドの代わりに、 **IBaseMessageContext.Promote**メソッド。  
  
9. XPath 式を使用してメッセージから情報を抽出する必要がある場合にメモリを使用してドキュメント全体を読み込みを避けるため、 **XmlDocument**のみを使用するオブジェクト、 **SelectNodes**または**SelectSingleNode**メソッド。 説明する手法を使用して、または、[ストリーミングでのメモリ使用量の最適化](../technical-guides/optimizing-memory-usage-with-streaming.md)します。  
  
## <a name="use-streaming-to-minimize-the-memory-footprint-required-when-loading-messages-in-pipelines"></a>ストリーミングを使ってパイプラインでメッセージを読み込むときに必要なメモリのフット プリントを最小限にするには  
 次の手法では、パイプラインにメッセージを読み込む場合は、メッセージのメモリ使用量を最小限に抑える方法について説明します。  
  
### <a name="use-readonlyseekablestream-and-virtualstream-to-process-a-message-from-a-pipeline-component"></a>ReadOnlySeekableStream と VirtualStream を使用して、パイプライン コンポーネントからのメッセージを処理するには  
 パイプライン コンポーネントの内部でメモリへのメッセージ全体の読み込みを回避するために、ベスト プラクティスと見なされます。 お勧めの方法は、カスタム ストリームの実装では、使用し、要求が行われた読み取りとして、受信ストリームをラップする、カスタム ストリームの実装は、基になる、ラップされたストリームを読み取り、(純粋なストリーミング方法) で読み取られると、データを処理します。 これは、実装が非常に困難にすることができ、可能であれば、に応じて、ストリームを使用して行うに必要なことができない可能性があります。 ここでは、使用して、 **ReadOnlySeekableStream**と**VirtualStream** Microsoft.BizTalk.Streaming.dll によって公開されるクラス。 これらの実装でも提供[任意の XPath プロパティ ハンドラ (BizTalk Server サンプル)](http://go.microsoft.com/fwlink/?LinkId=160069) (http://go.microsoft.com/fwlink/?LinkId=160069) BizTalk SDK に含まれています **。ReadOnlySeekableStream**により、カーソルは、ストリームの先頭に移動できます。 **VirtualStream**サイズが指定のしきい値を超えていない限り、MemoryStream を内部で、使用する場合、ストリーム、ファイル システムに書き込まれます。 これら 2 つのストリームを組み合わせての使用 (を使用して**VirtualStream**の永続的なストレージとして、 **ReadOnlySeekableStream**)"seekability"と「オーバーフロー ファイル システムに」機能の両方を提供します。 これには、メッセージ全体をメモリに読み込むことがなくサイズの大きいメッセージの処理が対応しています。 次のコードは、この機能を実装するパイプライン コンポーネントで使用可能性があります。  
  
```  
int bufferSize = 0x280;  
int thresholdSize = 0x100000;  
Stream vStream = new VirtualStream(bufferSize, thresholdSize);  
Stream seekStream = new ReadOnlySeekableStream(inboundStream, vStream, bufferSize);  
```  
  
 このコードは、bufferSize を公開することで「オーバーフローしきい値」を提供し、各 thresholdSize 変数は、受信場所または送信ポートの構成。 開発者や管理者のさまざまなメッセージの種類と (32 ビットとなどのさまざまな構成によって、このオーバーフローしきい値を調整し、ことができます。64 ビット)。  
  
### <a name="using-xpathreader-and-xpathcollection-to-extract-a-given-ibasemessage-object-from-within-a-custom-pipeline-component"></a>XPathReader と XPathCollection を使用して、カスタム パイプライン コンポーネント内から指定した IBaseMessage オブジェクトを抽出します。  
 特定の値を使用する代わりに、XML ドキュメントからプルする必要がある場合、 **SelectNodes**と**SelectSingleNode** XPathReader クラスのインスタンスを使用して、XmlDocument クラスによって公開されるメソッド次のコード例に示すように、Microsoft.BizTalk.XPathReader.dll アセンブリによって提供されます。  
  
> [!NOTE]  
>  XPathReader を使用してより優れたパフォーマンスを提供 SelectNodes または SelectSingleNode で XmlDocument を使用する可能性がありますが、XPathReader では、アプリケーションのフラットなメモリのプロファイルを保持できます。 特に、小さいメッセージ。  
  
 XPathReader と XPathCollection を使用して、抽出する方法を示します、指定された**IBaseMessage**からカスタム パイプライン コンポーネント内のオブジェクトします。  
  
```  
public IBaseMessage Execute(IPipelineContext context, IBaseMessage message)  
{  
    try  
    {  
        ...  
        IBaseMessageContext messageContext = message.Context;  
        if (string.IsNullOrEmpty(xPath) && string.IsNullOrEmpty(propertyValue))  
        {  
            throw new ArgumentException(...);  
        }  
        IBaseMessagePart bodyPart = message.BodyPart;  
        Stream inboundStream = bodyPart.GetOriginalDataStream();  
        VirtualStream virtualStream = new VirtualStream(bufferSize, thresholdSize);  
        ReadOnlySeekableStream readOnlySeekableStream = new ReadOnlySeekableStream(inboundStream, virtualStream, bufferSize);  
        XmlTextReader xmlTextReader = new XmlTextReader(readOnlySeekableStream);  
        XPathCollection xPathCollection = new XPathCollection();  
        XPathReader xPathReader = new XPathReader(xmlTextReader, xPathCollection);  
        xPathCollection.Add(xPath);  
        bool ok = false;  
        while (xPathReader.ReadUntilMatch())  
        {  
            if (xPathReader.Match(0) && !ok)  
            {  
                propertyValue = xPathReader.ReadString();  
                messageContext.Promote(propertyName, propertyNamespace, propertyValue);  
                ok = true;  
            }  
        }  
        readOnlySeekableStream.Position = 0;  
        bodyPart.Data = readOnlySeekableStream;  
    }  
    catch (Exception ex)  
    {  
        if (message != null)  
        {  
            message.SetErrorInfo(ex);  
        }  
        ...  
        throw ex;  
    }  
    return message;  
}  
```  
  
## <a name="use-xmlreader-and-xmlwriter-with-xmltranslatorstream-to-process-a-message-from-a-pipeline-component"></a>パイプライン コンポーネントからのメッセージを処理する XMLTranslatorStream と XMLReader および XMLWriter を使用して、  
 ストリーミングの手法を使用するカスタム パイプライン コンポーネントを実装するためのもう 1 つのメソッドは、.NET を使用する**XmlReader**と**XmlWriter**クラスと組み合わせて、 **XmlTranslatorStream** BizTalk Server によって提供されるクラス。 たとえば、 **NamespaceTranslatorStream** Microsoft.BizTalk.Pipeline.Components アセンブリに含まれるクラスから継承**XmlTranslatorStream**古い名前空間を置換するために使用できますストリームに含まれる XML ドキュメントに新しいものです。 新しいインスタンスをメッセージのボディ パーツの元のデータ ストリームをラップするカスタム パイプライン コンポーネント内でこの機能を使用するには、 **NamespaceTranslatorStream**クラスし、後者を返します。 この方法で、受信メッセージがない読み取り、処理ではなく、パイプライン コンポーネントでは、内部ストリームが同じパイプラインに後続のコンポーネントによって読み取られたか、ドキュメントを BizTalk Server に発行する前に、メッセージ エージェントによって最後に使用された場合にのみメッセージ ボックス。  
  
 次の例では、この機能を使用する方法を示します。  
  
```  
public IBaseMessage Execute(IPipelineContext context, IBaseMessage message)  
{  
   IBaseMessage outboundMessage = message;  
   try  
   {  
      if (context == null)  
      {  
         throw new ArgumentException(Resources.ContextIsNullMessage);  
      }  
      if (message == null)  
      {  
         throw new ArgumentException(Resources.InboundMessageIsNullMessage);  
      }  
  
      IBaseMessagePart bodyPart = message.BodyPart;  
      Stream stream = new NamespaceTranslatorStream(context,   
                                                    bodyPart.GetOriginalDataStream(),   
                                                    oldNamespace,   
                                                    newNamespace);  
      context.ResourceTracker.AddResource(stream);  
      bodyPart.Data = stream;  
   }  
   catch (Exception ex)  
   {  
      if (message != null)  
      {  
         message.SetErrorInfo(ex);  
      }  
  
      throw ex;  
   }  
   return outboundMessage;  
}  
```  
  
## <a name="using-resourcetracker-in-custom-pipeline-components"></a>カスタム パイプライン コンポーネントで ResourceTracker を使用します。  
 パイプライン コンポーネントは、作成オブジェクトの有効期間を管理して、これらのオブジェクトが不要とすぐに、ガベージ コレクションを実行する必要があります。  場合は、パイプライン コンポーネントには、このようなオブジェクトをパイプラインのコンテキストから、パイプラインをフェッチがリソースの追跡ツールに追加する必要がありますし、最後のパイプラインの実行が終わるまでオブジェクトの有効期間が希望しています。  
  
 リソースの追跡ツールは、次の種類のオブジェクトに使用されます。  
  
- Stream オブジェクト  
  
- COM オブジェクト  
  
- IDisposable オブジェクト  
  
  メッセージ エンジンによりが成功または失敗したかどうかに関係なく、パイプラインは完全に実行した後、適切なタイミングでリソースの追跡ツールに追加されるすべてのネイティブ リソースが解放されるようになります。 リソースの追跡ツールのインスタンスとそれを追跡しているオブジェクトの有効期間は、パイプラインのコンテキスト オブジェクトによって管理されます。 IPipelineContext インターフェイスを実装するオブジェクトをパイプライン コンポーネントのすべての種類に利用可能になってパイプライン コンテキスト。  
  
  たとえば、次のコード スニペットは、カスタム パイプライン コンポーネントで ResourceTracker プロパティを使用する方法を示すサンプルです。 コード スニペットを ResourceTracker プロパティを使用するには、次のパラメーターを使用して`IPipelineContext.ResourceTracker.AddResource`します。 このパラメーターには。  
  
- IPipelineContext インターフェイスは、すべてのドキュメント処理に固有のインターフェイスへのアクセスに使用するメソッドを定義します。  
  
- ResourceTracker プロパティは、IPipelineContext を参照し、パイプライン処理の最後に明示的に破棄されたオブジェクトを追跡するために使用します。  
  
- ResourceTracker.AddResource メソッドが COM オブジェクト、破棄可能なオブジェクトおよびストリームを追跡するために使用し、明示的に閉じる (ストリーム)、(IDisposable オブジェクト) を破棄またはこれら (COM オブジェクト) のリリースにカスタム パイプライン コンポーネント内で常に使用します。BizTalk メッセージ ボックスに、メッセージが発行されると、リソースの種類。  
  
```  
public IBaseMessage Execute(IPipelineContext pContext, IBaseMessage pInMsg)  
  
{  
      IBaseMessage outMessage = pContext.GetMessageFactory().CreateMessage();  
  
      IBaseMessagePart outMsgBodyPart = pContext.GetMessageFactory().CreateMessagePart();  
  
      outMsgBodyPart.Charset = Encoding.UTF8.WebName;   
  
      outMsgBodyPart.ContentType = "text/xml";  
  
//Code to load message content in the MemoryStream object//  
  
      MemoryStream messageData = new MemoryStream();  
  
   //The MemoryStream needs to be closed after the whole pipeline has executed, thus adding it into ResourceTracker//  
  
      pContext.ResourceTracker.AddResource(messageData);  
  
//Custom pipeline code to load message data into xmlPayload//  
  
      XmlDocument xmlPayLoad = new XmlDocument();  
  
      xmlPayLoad.Save(messageData);  
  
      messageData.Seek(0, SeekOrigin.Begin);  
  
//The new stream is assigned to the message part’s data//  
  
      outMsgBodyPart.Data = messageData;  
  
// Pipeline component logic here//  
  
      return outMessage;  
  
}  
```  
  
## <a name="comparison-of-loading-messages-into-pipelines-using-an-in-memory-approach-and-using-a-streaming-approach"></a>読み込みメッセージをメモリ内のアプローチを使用して、ストリーミングのアプローチを使用して、パイプラインの比較  
 次の情報が Nic Barden のブログから引用したもの[ http://blogs.objectsharp.com/cs/blogs/nbarden/archive/2008/04/14/developing-streaming-pipeline-components-part-1.aspx ](http://go.microsoft.com/fwlink/?LinkId=160228) (http://go.microsoft.com/fwlink/?LinkId=160228)します。 このテーブルは、メモリ内のアプローチを使用して、ストリーミングのアプローチを使用してパイプラインに読み込みメッセージの集計の比較を提供します。  
  
|比較しています.|ストリーミング|メモリ内|  
|----------------------|---------------|---------------|  
|メッセージごとのメモリ使用量|メッセージのサイズに関係なく、低|高 (メッセージ サイズによって異なります)|  
|XML データの処理に使用される一般的なクラス|ビルドとカスタムの派生の。<br /><br /> XmlTranslatorStream、XmlReader および XmlWriter|XmlDocument、XPathDocument、MemoryStream および VirtualStream|  
|ドキュメント|役に立たなかった – 多くのサポートされていないと文書化されていない BizTalk クラス|非常に良好な - .NET Framework クラス|  
|「ロジックを処理する」コードの場所|-「結び付ける」リーダーおよび Execute メソッドを使用してストリームします。<br />のデータの読み取りとは、リーダーおよびストリーム内実際の実行に発生します。|パイプライン コンポーネントの Execute メソッドから直接。|  
|data|説明データを読むには、ラッピング各層で再作成されます。|変更し、次のコンポーネントが呼び出される前に各コンポーネントに書き出さの読み取り。|  
  
## <a name="see-also"></a>参照  
 [BizTalk Server アプリケーションの最適化](../technical-guides/optimizing-biztalk-server-applications.md)