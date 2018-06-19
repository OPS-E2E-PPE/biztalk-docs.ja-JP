---
title: FILE 送信ポート経由で AS2 メッセージの送信 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c5ce9ff-fd73-4d5f-9b16-387c1e520c3a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 555066cb81eabe7328734e73fd9598fbd2cd418a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270730"
---
# <a name="sending-an-as2-message-over-a-file-send-port"></a>FILE 送信ポートを使用した AS2 メッセージの送信
通常、AS2 メッセージは HTTP アダプターを介して送信されます。 ただし、カスタム コンポーネントを作成する場合は、AS2 メッセージを FILE アダプター経由で送信できます。 このトピックでは、このようなソリューションのしくみについて説明し、ソリューションのサンプル コードを示します。  
  
 AS2 メッセージが HTTP 経由で送信されると、送信パイプラインの AS2 エンコーダーは、メッセージの送信に必要な HTTP (および AS2) ヘッダーを `HTTP.UserHttpHeaders` コンテキスト プロパティに挿入します。 これらのヘッダーは、既存の `HTTP.UserHttpHeaders` コンテキスト プロパティ、別のコンテキスト プロパティ、またはアグリーメント プロパティから (この優先順位で) 取得されます。 送信ポートの HTTP アダプターは、これらのヘッダーをメッセージに書き込み、HTTP 経由でメッセージを送信します。  
  
 送信ポートの HTTP アダプターの代わりに FILE アダプターを使用する場合、`HTTP.UserHttpHeaders` コンテキスト プロパティのヘッダー値は、メッセージに書き込まれません。 `HTTP.UserHttpHeaders` のヘッダーをメッセージの前に付けるためのカスタム パイプライン コンポーネントを作成する必要があります。 こうすることにより、メッセージは FILE アダプターによってフォルダーに追加でき、必要な HTTP ヘッダーが含まれた AS2 メッセージになります。  
  
 すべての AS2 ヘッダーが `HTTP.UserHttpHeaders` コンテキスト プロパティに含まれるようにするためにも、カスタム コンポーネントの作成が必要になる場合があります。 カスタム オーケストレーションまたはカスタム パイプライン コンポーネントを AS2Encoder の前に作成すると、AS2 エンコーダーによって `HTTP.UserHttpHeaders` を構築するために使用されるコンテキスト プロパティを設定できます。  
  
## <a name="writing-headers-to-an-as2-message"></a>AS2 メッセージへのヘッダーの書き込み  
 HTTP アダプターではなく FILE アダプターを使用して AS2 メッセージを生成するには、カスタムの AS2 送信パイプラインで AS2 エンコーダーの後にカスタム パイプライン コンポーネントを追加します。 `HTTP.UserHttpHeaders` コンテキスト プロパティのヘッダーをメッセージに書き込むコードを、このカスタム パイプライン コンポーネントに追加します。 サンプル コードは次のとおりです。  
  
```  
public IBaseMessage Execute(IPipelineContext pContext, IBaseMessage pInMsg)  
        {  
            IPipelineContext pipelineContext = pContext;  
            IBaseMessage baseMessage = pInMsg;  
  
            //Prepend Headers  
            MemoryStream ms = new MemoryStream();  
            string strName = "UserHttpHeaders";  
            string strValue = (string)baseMessage.Context.Read(strName,  
              "http://schemas.microsoft.com/BizTalk/2003/  
              http-properties");  
  
            //Leave an empty line between the headers and the body  
            strValue += "\r\n";  
            ms.Write(Encoding.ASCII.GetBytes(strValue), 0,   
               Encoding.ASCII.GetByteCount(strValue));  
  
            //Append Body  
            Stream sr = baseMessage.BodyPart.Data;  
  
            //Read the body of the message and append it to the memory   
              stream containing the headers  
            int size = 1024;  
            byte[] buffer = new byte[size];  
            while (0 != (size = sr.Read(buffer, 0, buffer.Length)))  
            {  
                ms.Write(buffer, 0, size);  
            }  
  
            //Set the body of the message to the new memory stream  
            baseMessage.BodyPart.Data = ms;  
  
            //Rewind the stream  
            ms.Seek(0, SeekOrigin.Begin);  
  
            return baseMessage;  
        }  
```  
  
## <a name="promoting-as2-header-context-properties"></a>AS2 ヘッダー コンテキスト プロパティの昇格  
 カスタム オーケストレーションまたはカスタム パイプライン コンポーネントを使用すると、AS2 ヘッダーのプロパティをメッセージのコンテキストに昇格できます。  
  
 カスタム パイプライン コンポーネントを使用して AS2 ヘッダー プロパティを昇格するには、カスタムの AS2 送信パイプラインで AS2 エンコーダーの前にカスタム パイプライン コンポーネントを追加します。 `HTTP.UserHttpHeaders` からメッセージにヘッダーを書き込むには、上記のサンプル コードを使用できます。ただし、Read メソッドを Promote メソッドで置き換えて、昇格するコンテキスト プロパティの名前、値、および名前空間を指定する必要があります。  
  
 カスタム オーケストレーションを使用して AS2 ヘッダー プロパティを昇格するには、FILE 受信ポート、メッセージの構築図形、および FILE 送信ポートを使用してオーケストレーションを作成します。 メッセージの構築図形には、AS2 ヘッダーが含まれた昇格対象プロパティを設定するコードを追加します。 カスタム オーケストレーションに `Microsoft.BizTalk.HttpTransport.dll` への参照を追加する必要があります。  
  
 HTTP ヘッダーの名前空間は非 AS2 HTTP ヘッダーの場合は `http://schemas.microsoft.com/BizTalk/2003/http-properties` であり、AS2 ヘッダーの場合は `http://schemas.microsoft.com/BizTalk/2003/as2-properties` です。  
  
 次のサンプル コードに、オーケストレーションのメッセージの構築図形で AS2 ヘッダー プロパティを昇格する方法を示します。 このコードでは、MDN の AS2 ヘッダーが昇格されます。  
  
```  
Message_2=new System.Xml.XmlDocument();  
Message_2=Message_1;  
Message_2(EdiIntAS.IsAS2PayloadMessage)=false;  
Message_2(EdiIntAS.IsAS2AsynchronousMdn)=true;  
Message_2(EdiIntAS.IsAS2MdnResponseMessage)=true;  
Message_2(EdiIntAS.SendMDN)=true;  
Message_2(EdiIntAS.IsAS2MessageSigned)=false;  
Message_2(EdiIntAS.AS2To)="Party1";  
Message_2(EdiIntAS.AS2From)="Home";  
Message_2(EdiIntAS.MessageId)="123456";  
Message_2(EdiIntAS.OriginalMessageId)="2123456";  
Message_2(HTTP.UserHttpHeaders)="Message1-Id: xyz\r\nMyHeader: MyValue";  
```  
  
## <a name="see-also"></a>参照  
 [開発と BizTalk Server AS2 ソリューションの構成](../core/developing-and-configuring-biztalk-server-as2-solutions.md)