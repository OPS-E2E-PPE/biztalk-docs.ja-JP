---
title: "送信パーティ解決の AS2 コンテキスト プロパティの書き込み |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 808d63d9-076d-4eed-8420-aee12b130fee
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c89804c42554825e387d01ff592e3a628e8225b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="writing-as2-context-properties-for-outbound-party-resolution"></a><span data-ttu-id="32928-102">送信パーティ解決のための AS2 コンテキスト プロパティの記述</span><span class="sxs-lookup"><span data-stu-id="32928-102">Writing AS2 Context Properties for Outbound Party Resolution</span></span>
<span data-ttu-id="32928-103">発信 AS2 メッセージのアグリーメント解決は、AS2To コンテキスト プロパティ、または `Http.UserHttpHeaders` コンテキスト プロパティの AS2To プロパティを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="32928-103">Agreement resolution of outbound AS2 message can be performed using the AS2To context property or the AS2To property in the `Http.UserHttpHeaders` context property.</span></span> <span data-ttu-id="32928-104">しかし、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が AS2 メッセージを受信したとき、AS2To プロパティはコンテキストに書き込まれません。</span><span class="sxs-lookup"><span data-stu-id="32928-104">However, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] does not write the AS2To property to the context upon receiving an AS2 message.</span></span> <span data-ttu-id="32928-105">AS2To コンテキスト プロパティまたは UserHttpHeaders コンテキスト プロパティでアグリーメント解決を実行する場合は、アグリーメント解決を実行するカスタム オーケストレーションまたはカスタム パイプライン コンポーネントを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32928-105">If you want to perform agreement resolution on the AS2To or UserHttpHeaders context property, you have to write a custom orchestration or a custom pipeline component to do so.</span></span> <span data-ttu-id="32928-106">これは、送信ポートがアグリーメントにリンクされていない場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="32928-106">This is required only if the send port is not linked to the agreement.</span></span>  
  
 <span data-ttu-id="32928-107">カスタム オーケストレーションでは、次のコードを使用して、AS2-To を既存の `Http.UserHttpHeaders` コンテキスト プロパティの先頭に追加できます。</span><span class="sxs-lookup"><span data-stu-id="32928-107">In a custom orchestration, you can append AS2-To to the beginning of the existing `Http.UserHttpHeaders` context property using the following code:</span></span>  
  
```  
Message_1(Http.UserHttpHeaders) = “AS2-To: MyPartner\r\n” + Message_1(Http.UserHttpHeaders);  
```  
  
 <span data-ttu-id="32928-108">カスタム パイプライン コンポーネントでは、次のコードを使用して、AS2-To を既存の `Http.UserHttpHeaders` コンテキスト プロパティの先頭に追加できます。</span><span class="sxs-lookup"><span data-stu-id="32928-108">In a custom pipeline component, you can append AS2-To to the beginning of the existing `Http.UserHttpHeaders` context property using the following code.</span></span> <span data-ttu-id="32928-109">AS2-To は、メッセージが As2Encoder コンポーネントによって処理される前に `Http.UserHttpHeaders` コンテキスト プロパティに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32928-109">You need to append AS2-To to `Http.UserHttpHeaders` context property before the message is processed by the As2Encoder component.</span></span>  
  
```  
string strName="UserHttpHeaders";  
string strValue = "AS2-To: MyPartner\r\n" + (string)baseMessage.Context.Read(strName, "http://schemas.microsoft.com/BizTalk/2003/http-properties");  
baseMessage.Context.Write(strName, "http://schemas.microsoft.com/BizTalk/2003/http-properties", strValue);  
```  
  
 <span data-ttu-id="32928-110">昇格の詳細については、`EDIIntAS.AS2To`プロパティまたは`BTS.UseHttpHeaders`、コンテキスト プロパティの AS2 ヘッダー コンテキスト プロパティの昇格」を参照してください、 [FILE 送信ポート経由で AS2 メッセージの送信](../core/sending-an-as2-message-over-a-file-send-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="32928-110">For more information on promoting the `EDIIntAS.AS2To` property or the `BTS.UseHttpHeaders` property to the context, see "Promoting AS2 Header Context Properties" in the [Sending an AS2 Message over a FILE Send Port](../core/sending-an-as2-message-over-a-file-send-port.md).</span></span>  
  
 <span data-ttu-id="32928-111">HTTP ヘッダーを書き込むためのカスタム パイプライン コンポーネントに追加できるコードです。メッセージに UserHttpHeaders コンテキスト プロパティを参照してください[FILE 送信ポート経由で AS2 メッセージの送信](../core/sending-an-as2-message-over-a-file-send-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="32928-111">For code that you can add to a custom pipeline component to write the headers from the HTTP.UserHttpHeaders context property into the message, see [Sending an AS2 Message over a FILE Send Port](../core/sending-an-as2-message-over-a-file-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32928-112">参照</span><span class="sxs-lookup"><span data-stu-id="32928-112">See Also</span></span>  
 [<span data-ttu-id="32928-113">開発と BizTalk Server AS2 ソリューションの構成</span><span class="sxs-lookup"><span data-stu-id="32928-113">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)