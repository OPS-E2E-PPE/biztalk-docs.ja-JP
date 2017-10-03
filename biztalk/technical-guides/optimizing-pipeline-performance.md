---
title: "パイプラインのパフォーマンスの最適化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5137747-0dcf-4c96-90a7-01afb92f56a6
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4311efd0d23e29b63f02fc34b1650a894d29d335
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-pipeline-performance"></a>パイプラインのパフォーマンスを最適化します。
このトピックでのパイプラインのパフォーマンスを最適化するためのガイドラインを説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューションです。  
  
## <a name="best-practices-for-optimizing-performance-of-biztalk-server-pipelines"></a>BizTalk Server パイプラインのパフォーマンスを最適化するためのベスト プラクティス  
  
1.  パイプライン コンポーネントは、パフォーマンスに大きな影響を与えるため (たとえば、パススルー パイプライン コンポーネントを実行する、XML アセンブラー/逆アセンブラー パイプライン コンポーネントをより最大 30%)、そのカスタム パイプライン コンポーネントが実行することを確認してください最適な状態での展開では、それらを実装前にします。 BizTalk アプリケーションの全体的なパフォーマンスを最大化したい場合は、パイプライン コンポーネントで、カスタム パイプラインの数を最小限に抑えます。  
  
2.  パフォーマンスを向上できます全体と、パイプライン コンポーネントでメッセージの永続化の頻度を減らすことによって冗長性を最小化するようにコンポーネントをコーディングします。 すべてのカスタム アセンブリは具体的には、カスタムの追跡コンポーネントと同様に、パフォーマンスに悪影響を及ぼす可能性のあるアイテム テストするくださいとは別に負荷が高い状況を検索して、システムが最大能力で操作するときに、その動作を確認するにはボトルネックです。  
  
3.  パイプライン コンポーネント内の受信メッセージを読み取る必要がある場合は、メモリを使用してにドキュメント全体が読み込まれないように、 **XmlDocument**オブジェクト。 インスタンスで必要な領域の量、 **XmlDocument**を読み込んで、XML ドキュメントのメモリ内表現を作成するクラスは、実際のメッセージ サイズの 10 倍までです。 メッセージを読み取るために使用する必要があります、 **XmlTextReader**と共に、次のクラスのインスタンスのオブジェクト。  
  
    -   **VirtualStream (Microsoft.BizTalk.Streaming.dll)** -このクラスのソース コードにある 2 つの場所、パイプラインの SDK の下にある次のように: \samples\pipelines\arbitraryxpathpropertyhandler および SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm です。  
  
    -   **ReadOnlySeekableStream (Microsoft.BizTalk.Streaming.dll)**です。  
  
    -   **SeekAbleReadOnlyStream** -このクラスのソース コードにある 2 つの場所、パイプラインの SDK の下にある次のように: \samples\pipelines\arbitraryxpathpropertyhandler および SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm です。  
  
4.  PassThruReceive パイプラインと可能な限り PassThruTransmit の標準パイプラインを使用します。 任意のパイプライン コンポーネントが含まれていないし、メッセージの処理を実行しません。 このため、それらには受信または送信メッセージの最大のパフォーマンスを確認してください。 バイナリ メッセージを送信する必要がある場合は、BizTalk メッセージ ボックスと送信ポートで PassThruTransmit パイプラインにバイナリ ドキュメントを公開する必要がある場合は、受信場所で PassThruReceive パイプラインを使用できます。 メッセージがフォーマットされているし、転送する準備ができて場合オーケストレーションにバインドされる物理送信ポートで PassThruTransmit パイプラインを使用することもできます。 次の操作のいずれかを実行する必要がある場合、別のアプローチを使用する必要があります。  
  
    -   受信 XML またはフラット ファイル メッセージのコンテキストにプロパティを昇格します。  
  
    -   受信場所内のマップを適用します。  
  
    -   メッセージをサブスクライブするオーケストレーションでマップを適用します。  
  
    -   メッセージをサブスクライブする送信ポートでマップを適用します。  
  
     これらの操作を行うためには、プローブし、受信パイプライン内のドキュメントの種類を検出して MessageType コンテキスト プロパティに、(名前空間 #root 名) の値を割り当てます。 この操作は、通常、Xml 逆アセンブラー コンポーネント (XmlDasmComp) などの逆アセンブラー コンポーネントまたはフラット ファイル逆アセンブラー コンポーネント (FFDasmComp) して行います。 この例では、standard (たとえば、XmlReceive パイプライン) または標準またはカスタム逆アセンブラー コンポーネントを含むカスタム パイプラインを使用する必要があります。  
  
5.  できる限り遅くリソースを取得し、できるだけ早くリリースできるだけします。 たとえば、データベース上のデータにアクセスする必要がある場合は、できるだけ遅く接続を開くしてできるだけ早く閉じます。 C# を使用して、暗黙的に破棄可能なオブジェクトを解放するステートメントを使用して、または、オブジェクトを明示的に破棄するには、try – catch – finally ステートメントの finally ブロックします。 すると、コンポーネントをデバッグする単純なソース コードをインストルメント化します。  
  
6.  厳密にメッセージの処理を高速化する必要はありません、パイプラインからコンポーネントを削除します。  
  
7.  受信パイプライン内のメッセージのルーティング (オーケストレーション、送信ポート) またはメッセージ コンテキスト プロパティ (送信ポート) の降格する必要がある場合にのみ、メッセージ コンテキストに項目を昇格する必要があります。  
  
8.  メッセージを表示してメタデータを含める必要があるあり、ルーティングまたは降格目的で、使用するメタデータを使用しない場合、 **IBaseMessageContext.Write**メソッドの代わりに、 **IBaseMessageContext.Promote**メソッド。  
  
9. XPath 式を使用してメッセージから情報を抽出する必要がある場合は、メモリを使用してにドキュメント全体が読み込まれないように、 **XmlDocument**だけ使用するオブジェクトを**SelectNodes**または**SelectSingleNode**メソッドです。 またはで説明する手法を使用して[ストリーミングでのメモリ使用量の最適化](../technical-guides/optimizing-memory-usage-with-streaming.md)です。  
  
## <a name="use-streaming-to-minimize-the-memory-footprint-required-when-loading-messages-in-pipelines"></a>ストリーミングを使用して、パイプラインでメッセージを読み込むときに必要なメモリ使用量を最小限に抑える  
 次の手法では、パイプラインにメッセージを読み込む場合は、メッセージのメモリ使用量を最小限に抑える方法について説明します。  
  
### <a name="use-readonlyseekablestream-and-virtualstream-to-process-a-message-from-a-pipeline-component"></a>ReadOnlySeekableStream と VirtualStream パイプライン コンポーネントからのメッセージの処理を使用してください。  
 メッセージ全体をパイプライン コンポーネントの内部でメモリに読み込まれないようにするベスト プラクティスと見なされます。 優先のアプローチは、カスタム ストリームの実装とし、要求が行われる読み取りとして、受信ストリームをラップする、カスタム ストリームの実装が、基になる、ラップされたストリームを読み取り、(純粋なストリーミング的に) 読み取られると、データを処理します。 これを実装するのには非常に難しくなり、ストリームで実行する必要がある新機能によって、可能なことができない可能性があります。 このケースでは、使用して、 **ReadOnlySeekableStream**と**VirtualStream** Microsoft.BizTalk.Streaming.dll によって公開されるクラスです。 これらの実装を提供しても[任意の XPath プロパティ ハンドラ (BizTalk Server サンプル)](http://go.microsoft.com/fwlink/?LinkId=160069) (http://go.microsoft.com/fwlink/?LinkId=160069) BizTalk SDK に含まれています。**ReadOnlySeekableStream**カーソルは、ストリームの先頭に移動できることを確認します。 **VirtualStream**サイズが、指定されたしきい値を超えていない限り、MemoryStream を内部で、使用する場合、ファイル システムにストリームが書き込まれます。 これら 2 つのストリームの組み合わせで使用する (を使用して**VirtualStream**の永続的な記憶域として、 **ReadOnlySeekableStream**)"seekability"と「オーバーフロー ファイル システムに」機能の両方を提供します。 これには、メッセージ全体をメモリに読み込むことがなくサイズの大きいメッセージの処理が対応しています。 次のコードは、この機能を実装するパイプライン コンポーネントで使用可能性があります。  
  
```  
int bufferSize = 0x280;  
int thresholdSize = 0x100000;  
Stream vStream = new VirtualStream(bufferSize, thresholdSize);  
Stream seekStream = new ReadOnlySeekableStream(inboundStream, vStream, bufferSize);  
```  
  
 このコードは、bufferSize を公開することで「オーバーフローしきい値」を提供し、各 thresholdSize 変数は、受信場所または送信ポート構成します。 開発者や管理者がさまざまなメッセージ型と (32 ビット エディションとなどのさまざまな構成が、このオーバーフローしきい値を調整し、ことができます。64 ビット)。  
  
### <a name="using-xpathreader-and-xpathcollection-to-extract-a-given-ibasemessage-object-from-within-a-custom-pipeline-component"></a>XPathReader と XPathCollection を使用して、カスタム パイプライン コンポーネントの中から指定された IBaseMessage オブジェクトを抽出します。  
 特定の値を使用する代わりに、XML ドキュメントからプルされる必要がある場合、 **SelectNodes**と**SelectSingleNode** XmlDocument クラスによって公開されたメソッドが XPathReader クラスのインスタンスを使用します。次のコード例に示すように、Microsoft.BizTalk.XPathReader.dll アセンブリによって提供されます。  
  
> [!NOTE]  
>  小さいメッセージを特に、SelectNodes または SelectSingleNode と共に、XmlDocument を使用することがあります XPathReader を使用するよりも優れたパフォーマンスが、XPathReader では、アプリケーションのフラットなメモリ プロファイルを維持することができます。  
  
 XPathReader と XPathCollection を使用して抽出する方法を示します、指定された**IBaseMessage**カスタム パイプライン コンポーネント内のオブジェクトにします。  
  
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
  
## <a name="use-xmlreader-and-xmlwriter-with-xmltranslatorstream-to-process-a-message-from-a-pipeline-component"></a>パイプライン コンポーネントからのメッセージを処理するのに XMLTranslatorStream で XMLReader および XMLWriter を使用します。  
 ストリーミングの手法を使用してカスタム パイプライン コンポーネントを実装するための別の方法は、.NET を使用する**XmlReader**と**XmlWriter**クラスと組み合わせて、 **XmlTranslatorStream** BizTalk Server によって提供されるクラスです。 たとえば、 **NamespaceTranslatorStream** Microsoft.BizTalk.Pipeline.Components アセンブリに含まれているクラスから継承**XmlTranslatorStream**し、古い名前空間の代わりに使用することができますストリームに含まれる XML ドキュメントに新しいものです。 新しいインスタンスをメッセージのボディ部の元のデータ ストリームをラップするカスタム パイプライン コンポーネントの内部には、この機能を使用するために、 **NamespaceTranslatorStream**クラスおよび後者を返します。 この方法で、受信メッセージがない読み取り、処理内では、パイプライン コンポーネントが、ストリームは、同一のパイプラインの後続のコンポーネントによって読み取られるか、最後に、ドキュメントを BizTalk Server に発行する前に、メッセージ エージェントによって使用される場合にのみメッセージ ボックスです。  
  
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
 パイプライン コンポーネントを作成オブジェクトの有効期間を管理し、これらのオブジェクトが不要にするとすぐに、ガベージ コレクションを実行します。  場合は、パイプライン コンポーネントには、このようなオブジェクトをパイプラインがパイプラインのコンテキストからフェッチするリソースの追跡ツールに追加する必要がありますし、最後のパイプラインの実行が終了するまでにオブジェクトの有効期間が希望しています。  
  
 リソースの追跡ツールは、次の種類のオブジェクトに使用します。  
  
-   ストリーム オブジェクト  
  
-   COM オブジェクト  
  
-   IDisposable オブジェクト  
  
 メッセージ エンジンはそれが成功したか失敗したかどうかに関係なく、パイプラインは完全に実行した後、適切なタイミングでリソースの追跡ツールに追加されるすべてのネイティブ リソースが解放されることを確認します。 リソース トラッカー インスタンスとそれを追跡しているオブジェクトの有効期間は、パイプラインのコンテキスト オブジェクトによって管理されます。 パイプラインのコンテキストは IPipelineContext インターフェイスを実装するオブジェクトをパイプライン コンポーネントのすべての種類に提供されます。  
  
 たとえば、次のコード スニペットは、カスタム パイプライン コンポーネントで ResourceTracker プロパティを使用する方法について説明するサンプルです。 コード スニペットを ResourceTracker プロパティを使用するには、次のパラメーターを使用して`IPipelineContext.ResourceTracker.AddResource`です。 このパラメーターには。  
  
-   IPipelineContext インターフェイスは、ドキュメント処理に固有のすべてのインターフェイスへのアクセスに使用するメソッドを定義します。  
  
-   ResourceTracker プロパティは、IPipelineContext を参照し、パイプライン処理の最後に明示的に破棄されるオブジェクトを追跡するために使用します。  
  
-   ResourceTracker.AddResource メソッド COM オブジェクト、破棄可能なオブジェクトおよびストリームを追跡するために使用およびは常に内で使用、カスタム パイプライン コンポーネントを明示的に閉じる (ストリーム)、(IDisposable オブジェクト) を破棄またはこれら (COM オブジェクト) のリリースBizTalk メッセージ ボックスに、メッセージが公開される場合、リソースの種類。  
  
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
  
## <a name="comparison-of-loading-messages-into-pipelines-using-an-in-memory-approach-and-using-a-streaming-approach"></a>読み込みメッセージをインメモリ アプローチを使用して、ストリーミングの手法を使用するパイプラインの比較  
 次の情報は、Nic Barden ブログから取得されました[http://blogs.objectsharp.com/cs/blogs/nbarden/archive/2008/04/14/developing-streaming-pipeline-components-part-1.aspx](http://go.microsoft.com/fwlink/?LinkId=160228) (http://go.microsoft.com/fwlink/?LinkId=160228)。 次の表は、パイプライン インメモリ アプローチを使用して、ストリーミングの手法の利用に読み込みメッセージの集計の比較を提供します。  
  
|比較しています.|ストリーミング|メモリ内|  
|----------------------|---------------|---------------|  
|1 つのメッセージのメモリ使用量|メッセージのサイズに関係なく、低|高 (メッセージのサイズによって異なります)|  
|XML データの処理に使用する一般的なクラス|構築されたのとではカスタム派生します。<br /><br /> XmlTranslatorStream、XmlReader、および XmlWriter|XmlDocument、XPathDocument、MemoryStream および VirtualStream|  
|ドキュメント|Poor – 多くのサポートされないと文書化されていない BizTalk クラス|非常に良好 - .NET Framework クラス|  
|「処理ロジック」のコードの場所|-「をネットワーク上で」リーダーおよび Execute メソッドを使用してストリーム。<br />実際の実行は、データの読み取りと、リーダーおよびストリーム内に発生します。|パイプライン コンポーネントの実行メソッドから直接。|  
|data|それを介するデータが読み込まれるとは、ラッピング各層で再作成されます。|読み、変更して、次のコンポーネントが呼び出される前に各コンポーネントに書き込まれます。|  
  
## <a name="see-also"></a>参照  
 [BizTalk Server アプリケーションの最適化](../technical-guides/optimizing-biztalk-server-applications.md)