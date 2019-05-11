---
title: 送信パーティ解決の AS2 コンテキスト プロパティの書き込み |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 808d63d9-076d-4eed-8420-aee12b130fee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 603d4ce029f3518f262274767da2a2da3e819eb7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262055"
---
# <a name="writing-as2-context-properties-for-outbound-party-resolution"></a><span data-ttu-id="44cc5-102">送信パーティ解決の AS2 コンテキスト プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="44cc5-102">Writing AS2 Context Properties for Outbound Party Resolution</span></span>
<span data-ttu-id="44cc5-103">送信 AS2 メッセージのアグリーメントの解決は、AS2To コンテキスト プロパティまたは AS2To プロパティを使用して実行できる、`Http.UserHttpHeaders`コンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="44cc5-103">Agreement resolution of outbound AS2 message can be performed using the AS2To context property or the AS2To property in the `Http.UserHttpHeaders` context property.</span></span> <span data-ttu-id="44cc5-104">ただし、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] AS2 メッセージを受信すると、コンテキストに AS2To プロパティを書き込みません。</span><span class="sxs-lookup"><span data-stu-id="44cc5-104">However, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] does not write the AS2To property to the context upon receiving an AS2 message.</span></span> <span data-ttu-id="44cc5-105">AS2To または UserHttpHeaders コンテキスト プロパティでアグリーメントの解決を実行する場合は、カスタム オーケストレーションまたはカスタム パイプライン コンポーネントを記述があります。</span><span class="sxs-lookup"><span data-stu-id="44cc5-105">If you want to perform agreement resolution on the AS2To or UserHttpHeaders context property, you have to write a custom orchestration or a custom pipeline component to do so.</span></span> <span data-ttu-id="44cc5-106">これは、機能は、送信ポートがアグリーメントにリンクされていない場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="44cc5-106">This is required only if the send port is not linked to the agreement.</span></span>  
  
 <span data-ttu-id="44cc5-107">カスタム オーケストレーションでは、AS2 を追加することができます-を既存の先頭に`Http.UserHttpHeaders`次のコードを使用してコンテキストのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="44cc5-107">In a custom orchestration, you can append AS2-To to the beginning of the existing `Http.UserHttpHeaders` context property using the following code:</span></span>  
  
```  
Message_1(Http.UserHttpHeaders) = “AS2-To: MyPartner\r\n” + Message_1(Http.UserHttpHeaders);  
```  
  
 <span data-ttu-id="44cc5-108">カスタム パイプライン コンポーネントでは、AS2 を追加することができます-を既存の先頭に`Http.UserHttpHeaders`コンテキスト プロパティを次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="44cc5-108">In a custom pipeline component, you can append AS2-To to the beginning of the existing `Http.UserHttpHeaders` context property using the following code.</span></span> <span data-ttu-id="44cc5-109">AS2 を追加する必要があるのに`Http.UserHttpHeaders`コンテキスト プロパティ、メッセージが As2Encoder コンポーネントによって処理される前にします。</span><span class="sxs-lookup"><span data-stu-id="44cc5-109">You need to append AS2-To to `Http.UserHttpHeaders` context property before the message is processed by the As2Encoder component.</span></span>  
  
```  
string strName="UserHttpHeaders";  
string strValue = "AS2-To: MyPartner\r\n" + (string)baseMessage.Context.Read(strName, "http://schemas.microsoft.com/BizTalk/2003/http-properties");  
baseMessage.Context.Write(strName, "http://schemas.microsoft.com/BizTalk/2003/http-properties", strValue);  
```  
  
 <span data-ttu-id="44cc5-110">昇格の詳細については、`EDIIntAS.AS2To`プロパティまたは`BTS.UseHttpHeaders`コンテキストにプロパティの「AS2 ヘッダー コンテキスト プロパティの昇格」を参照してください、 [FILE 送信ポートを経由で AS2 メッセージの送信](../core/sending-an-as2-message-over-a-file-send-port.md)します。</span><span class="sxs-lookup"><span data-stu-id="44cc5-110">For more information on promoting the `EDIIntAS.AS2To` property or the `BTS.UseHttpHeaders` property to the context, see "Promoting AS2 Header Context Properties" in the [Sending an AS2 Message over a FILE Send Port](../core/sending-an-as2-message-over-a-file-send-port.md).</span></span>  
  
 <span data-ttu-id="44cc5-111">コード用 HTTP からヘッダーを書き込むためのカスタム パイプライン コンポーネントに追加することができます。メッセージに UserHttpHeaders コンテキスト プロパティを参照してください[FILE 送信ポートを経由で AS2 メッセージの送信](../core/sending-an-as2-message-over-a-file-send-port.md)します。</span><span class="sxs-lookup"><span data-stu-id="44cc5-111">For code that you can add to a custom pipeline component to write the headers from the HTTP.UserHttpHeaders context property into the message, see [Sending an AS2 Message over a FILE Send Port](../core/sending-an-as2-message-over-a-file-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44cc5-112">参照</span><span class="sxs-lookup"><span data-stu-id="44cc5-112">See Also</span></span>  
 [<span data-ttu-id="44cc5-113">BizTalk Server AS2 ソリューションの開発と構成</span><span class="sxs-lookup"><span data-stu-id="44cc5-113">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)