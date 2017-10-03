---
title: "ストリーミングのメモリ使用率の最適化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8ba8820-65b4-4161-9f7a-3ae3d39e3d11
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e1707007eab19a86e4fabedfe9e16bfa9c8fc59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-memory-usage-with-streaming"></a>ストリーミングのメモリ使用量を最適化します。
このトピックでは、ストリーミングのパターンを使用したオーケストレーションでメッセージを読み込むときに、WCF トランスポートを使用して、またはサイズの大きいメッセージの送受信時のメッセージのメモリ容量を最小限に抑えるための推奨事項を説明します。   
オーケストレーションでコードを使用して、メッセージの内容を読み、ときに、XmlDocument 変数を使用しないでください。 XmlDocument 変数へのメッセージの読み込みと、特にサイズの大きいメッセージ用の大幅なオーバーヘッドが発生します。 このオーバーヘッドは、メモリ使用量とメモリ内構造を構築する処理の観点からです。 XmlDocument インスタンスの使用は、ドキュメント オブジェクト モジュール (DOM) のオブジェクト グラフを構築するためにメモリに読み込まれる全体のメッセージの内容を強制します。 このクラスのインスタンスによって使用されるメモリの総量では、実際のメッセージ サイズの約 10 倍の時間を指定できます。 XmlDocument 変数へのメッセージの読み込み時に必要なメモリ使用量の詳細については、次を参照してください。[章 9 – XML パフォーマンスの向上](http://go.microsoft.com/fwlink/?LinkId=139772)(http://go.microsoft.com/fwlink/?LinkId=139772) MSDN のです。   
このトピックの残りの部分では、XmlDocument 変数へのメッセージの読み込みを必要としないメッセージの内容を読み取るための代替のメソッドを提供します。  
  
## <a name="use-streaming-when-sending-or-receiving-large-messages-with-a-wcf-transport"></a>WCF トランスポートを使用してサイズの大きいメッセージを送受信する際のストリーミングを使用します。  
 WCF トランスポートを使用してサイズの大きいメッセージの送受信時に、Wcf-custom または Wcf-customisolated アダプターを使用しをサポートするバインディングの種類で構成、 **transferMode = Streamed**以下のバインドなどのオプション。  
  
-   **basicHttpBinding + BasicHttpBindingElement、transferMode Streamed を =**  
  
-   **netTcpBinding + NetTcpBindingElement、transferMode Streamed を =**  
  
-   **customBinding + HttpTransportElement、transferMode Streamed を =**  
  
-   **customBinding + ConnectionOrientedTransportElement、transferMode Streamed を =**  
  
 サポートするバインドと共に Wcf-custom または Wcf-customisolated アダプターを選択する、 **transferMode = Streamed**オプションは、必要に応じて、ファイル システムにサイズの大きいメッセージのストリーミングを実装し、可能性の軽減メモリ不足の問題。  
  
## <a name="use-streaming-to-minimize-the-memory-footprint-required-when-loading-messages-in-orchestrations"></a>ストリーミングを使用して、オーケストレーション内のメッセージを読み込むときに必要なメモリ使用量を最小限に抑える  
 次の手法では、オーケストレーションにメッセージを読み込む場合は、メッセージのメモリ使用量を最小限に抑える方法について説明します。  
  
### <a name="use-an-xlangmessage-variable-to-process-the-contents-of-a-message-or-message-part"></a>XLANGMessage 変数を使用してメッセージまたはメッセージ部分のコンテンツを処理  
 .NET クラス ライブラリをオーケストレーションからメッセージを渡す、ときに渡さないでくださいことです。 このトピックの前半に示した理由、XmlDocument 変数として代わりに、XLANGMessage 変数を使用します。 次の手法は、メッセージまたは XLANGMessage 変数を使用してメッセージ部分を読み取るためのメソッドを示しています。  
  
-   **XMLReader でメッセージを処理**XmlReader インスタンスとメッセージの処理、メッセージを XLANGMessage として .NET コードに渡すおよび XmlReader を使用してパーツのコンテンツを取得します。  
  
    ```  
    public void ProcessMessage(XLANGMessage message)  
    {  
        try  
        {  
            using (XmlReader reader = message[0].RetrieveAs(typeof(XmlReader)) as XmlReader)  
            if (reader != null)  
            {  
                ...  
            }  
        }  
        finally  
        {  
            message.Dispose();  
        }  
    }  
    ```  
  
-   **StreamReader を含む文字列に、メッセージの内容を取得**-XmlDocument.OuterXml() を使用する XML 文字列としてメッセージを取得するには XmlDocument のオーケストレーションでの一般的な用途の 1 つです。 次のコード例は、XLANGMessage 変数を使用して文字列としてメッセージを取得する代替方法を示しています。  
  
    ```  
    public static string MessageToString(XLANGMessage message)  
    {  
        string strResults;  
        try  
        {  
            using (Stream stream = message[0].RetrieveAs(typeof(Stream)) as Stream)  
            {  
                using (StreamReader reader = new StreamReader(stream))  
                {  
                    strResults = reader.ReadToEnd();  
                }  
            }  
        }  
        finally  
        {  
            message.Dispose();  
        }  
        return strResults;  
    }  
    ```  
  
-   **文字列に単純な .NET メッセージの内容を取得**-メッセージの種類が単純な .NET 型の場合は、その型としてメッセージを取得できます。 たとえば、文字列としてメッセージを取得するには、XLANGMessage として .NET コードにメッセージを渡すし、パーツのコンテンツを文字列としてを取得します。  
  
    ```  
    public void ProcessMessage(XLANGMessage message)  
    {  
        try  
        {  
            string content = message[0].RetrieveAs(typeof(string)) as string;  
            if (!string.IsNullOrEmpty(content))  
            {  
                ...  
            }  
        }  
        finally  
        {  
            message.Dispose();  
        }  
    }  
    ```  
  
-   **ストリームにメッセージの内容を取得**- をストリームとしてメッセージを取得、XLANGMessage として .NET コードにメッセージを渡すおよび一部のコンテンツをストリームとして取得します。  
  
    ```  
    public Stream ProcessRequestReturnStream(XLANGMessage message, int bufferSize, int thresholdSize)  
    {  
       ...  
       try  
       {  
          using (VirtualStream virtualStream = new VirtualStream(bufferSize, thresholdSize))  
          {  
             using (Stream partStream = (Stream)message[0].RetrieveAs(typeof(Stream)))  
             //Note that when calling this code, if the XmlDocument is quite large, keeping it in a memory with a MemoryStream may have an adverse effect on performance.   
             //In this case, it may be worthwhile to consider an approach that uses a VirtualStream + ReadonlySeekableStream to buffer it to the file system, if its size is bigger than the thresholdSize parameter.  
             //Keep in mind that:  
             // - If the message size is smaller than the threshold size, the VirtualStream class buffers the stream to a MemoryStream.  
             // - If the message size is bigger than the threshold size, the VirtualStream class buffers the stream to a temporary file.  
                using (ReadOnlySeekableStream readOnlySeekableStream = new ReadOnlySeekableStream(partStream, virtualStream, bufferSize))  
                {  
                   using (XmlReader reader = XmlReader.Create(readOnlySeekableStream))  
                   {  
  
                   }  
                }  
             }  
          }  
       }  
       catch (Exception ex)  
       {  
  
       }  
       finally  
       {  
          message.Dispose();  
       }  
       return stream;  
    }  
    ```  
  
-   **.NET オブジェクトに、メッセージの内容を取得**- を .NET オブジェクトとしてメッセージを取得、XLANGMessage として .NET コードに、メッセージを渡すこと、および .NET クラスのインスタンスとしてパーツのコンテンツを取得します。 この後者から作成、Xml メッセージのスキーマ、Visual Studio 2010 で提供される XML スキーマ定義ツール (Xsd.exe) ツールを使用します。  
  
    > [!NOTE]  
    >  この手法は、メッセージが小さい場合にのみ有効です。 それ以外の場合、この方法は、.NET オブジェクトに実際のメッセージを逆シリアル化に大きなオーバーヘッドでれる可能性があります。  
  
    ```  
    public void ProcessMessage(XLANGMessage message)  
    {  
        try  
          {  
          Request request = message[0].RetrieveAs(typeof(Request)) as Request;  
          if (request != null)  
          {  
             ...  
          }  
       }  
       finally  
       {  
          message.Dispose();  
       }  
  
    }  
    ```  
  
> [!NOTE]  
>  使用、 **Dispose()** .NET コードから戻る前に、XLANGMessage パラメーターによって公開されるメソッドが特に重要シナリオとのインスタンスを累積できる時間の長い実行オーケストレーションをループには時間の経過と共に解放せず XLANGMessage オブジェクトです。 呼び出し元のメッセージに関する詳細についてはします。この方法で Dispose() を参照してください[XLANGMessage として表されるメッセージ](http://go.microsoft.com/fwlink/?LinkId=139775)(http://go.microsoft.com/fwlink/?LinkId=139775)、BizTalk Server のドキュメントにします。 このトピックでは、IStreamFactory を使用して、ストリーム ベースのアプローチを使用してユーザー コードで XLANGMessage 変数を作成するためのベスト プラクティスも提供します。  
  
 オーケストレーションによって呼び出されるヘルパー コンポーネント内で、XLANGMessage を処理するさまざまな方法の詳細については、次のトピックを参照してください。  
  
-   [第 1 部、オーケストレーションによって呼び出されるヘルパー コンポーネント内で、XLANGMessage を処理するさまざまな方法は 4](http://go.microsoft.com/fwlink/?LinkID=210420) (http://go.microsoft.com/fwlink/?LinkID=210420)。  
  
-   [第 2 部、オーケストレーションによって呼び出されるヘルパー コンポーネント内で、XLANGMessage を処理するさまざまな方法は 4](http://go.microsoft.com/fwlink/?LinkID=210421) (http://go.microsoft.com/fwlink/?LinkID=210421)。  
  
### <a name="using-xpathreader-and-xpathcollection-to-extract-a-value-from-an-xlangmessage-object-from-a-method-invoked-by-an-orchestration"></a>XPathReader と XPathCollection 使用して、オーケストレーションによって呼び出されるメソッドから XLANGMessage オブジェクトから値を抽出するには  
 XMLDocument クラスをカスタム パイプライン コンポーネントなどのカスタム コードから XML メッセージの内容を読み取るまたはオーケストレーションによって呼び出されるヘルパー クラスを使用しないでください。 XMLDocument インスタンスを使用して、XML メッセージを読み込み、メッセージ全体が効率的ではありませんし、最大で 10 倍の実際のサイズ、メッセージのメモリを必要がありますメモリに読み込まれます。 XML メッセージの内容を読み取る方法がより効率的では、Microsoft.BizTalk.Streaming.dll アセンブリによって提供されるストリーム クラスのいずれかの元のストリームをラップするストリーミングの手法を使用します。 この手法は、サイズの大きいメッセージを読み込むときに特に便利です。  
  
 特定の値は、XmlDocument クラスによって公開される SelectNodes、SelectSingleNode メソッドを使用する代わりに、XML ドキュメントからプルされる必要がある場合は、として Microsoft.BizTalk.XPathReader.dll アセンブリによって提供される XPathReader クラスのインスタンスを使用します。次のコード例に示します。  
  
-   この例では、オーケストレーションによって呼び出されるメソッドの内部 XLANGMessage オブジェクトからの特定の値を抽出する XPathReader と XPathCollection を使用しています。  
  
    ```  
    public static string SelectSingleNode(XLANGMessage message, string xPath)   
    {  
        try  
        {  
            if (message == null || string.IsNullOrEmpty(xPath))  
            {  
                return string.Empty;  
            }  
            using (XmlReader reader = (XmlReader)message[0].RetrieveAs(typeof(XmlReader)))  
            {  
                XPathCollection xPathCollection = new XPathCollection();  
                XPathReader xPathReader = new XPathReader(reader, xPathCollection);  
                xPathCollection.Add(xPath);  
                while (xPathReader.ReadUntilMatch())  
                {  
                    if (xPathReader.Match(0))  
                    {  
                        return xPathReader.ReadString();  
                    }  
                }  
            }  
        }  
        catch (Exception ex)  
        {  
            ...  
        }  
        finally  
        {  
            message.Dispose();  
        }  
        return string.Empty;  
    }  
    ```  
  
## <a name="see-also"></a>参照  
 [BizTalk Server アプリケーションの最適化](../technical-guides/optimizing-biztalk-server-applications.md)