---
title: 送信 AS2 メッセージのアグリーメントの解決 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 578d7565-534c-4c13-b473-975f347f3a9b
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce8329b2b80ca3b9bfd6b34379d936d6be1df3ef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975859"
---
# <a name="agreement-resolution-for-outgoing-as2-messages"></a><span data-ttu-id="90774-102">送信 AS2 メッセージのアグリーメントの解決</span><span class="sxs-lookup"><span data-stu-id="90774-102">Agreement Resolution for Outgoing AS2 Messages</span></span>
<span data-ttu-id="90774-103">AS2 送信パイプラインは、HTTP/HTTPS トランスポート経由の送信 EDIINT/AS2 エンコード メッセージを処理するときに、メッセージを解決するアグリーメントを決定します。</span><span class="sxs-lookup"><span data-stu-id="90774-103">When an AS2 send pipeline processes an outgoing EDIINT/AS2-encoded message over HTTP/HTTPS transport, it determines the agreement that the message will resolve to.</span></span> <span data-ttu-id="90774-104">その後、それらのアグリーメントのプロパティを使用して送信メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="90774-104">It will then use those agreement properties to process the outgoing message.</span></span> <span data-ttu-id="90774-105">送信パイプラインは、次の条件 (優先度順) を使用してアグリーメントを決定します。</span><span class="sxs-lookup"><span data-stu-id="90774-105">The send pipeline will use the following criteria to determine the agreement (in order of priority):</span></span>  
  
1. <span data-ttu-id="90774-106">送信パイプラインは、AS2From および AS2To コンテキスト プロパティと、アグリーメント プロパティの一部として指定された AS2From および AS2To の値との照合を試みます。</span><span class="sxs-lookup"><span data-stu-id="90774-106">The send pipeline attempts to match the AS2From and AS2To context properties with the values of AS2From and AS2To specified as part of the agreement properties.</span></span>  
  
2. <span data-ttu-id="90774-107">送信パイプラインは、送信メッセージの AS2To コンテキスト プロパティで、その他のアグリーメント リゾルバーとして設定される、AS2To プロパティの値と一致しようとして、前の手順に失敗した場合、**識別子**アグリーメントのタブプロパティ。</span><span class="sxs-lookup"><span data-stu-id="90774-107">If the previous step fails, the send pipeline will attempt to match the AS2To context property of the outbound message with the value of AS2To property, which is set as additional agreement resolver in the **Identifiers** tab of agreement properties.</span></span>  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="90774-108">では、AS2To プロパティをコンテキストに書き込みません。</span><span class="sxs-lookup"><span data-stu-id="90774-108">does not write the AS2To property to the context.</span></span> <span data-ttu-id="90774-109">AS2To コンテキスト プロパティでアグリーメント解決を実行する場合は、アグリーメント解決を実行するカスタム オーケストレーションまたはカスタム パイプライン コンポーネントを組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="90774-109">If you want to perform agreement resolution on the AS2To context property, you will have to incorporate a custom orchestration or a custom pipeline component to do so.</span></span> <span data-ttu-id="90774-110">詳細については、[送信パーティ解決の AS2 コンテキスト プロパティの書き込み](../core/writing-as2-context-properties-for-outbound-party-resolution.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90774-110">For more information, see [Writing AS2 Context Properties for Outbound Party Resolution](../core/writing-as2-context-properties-for-outbound-party-resolution.md).</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="90774-111">動的送信ポートを使用している場合は、アグリーメント解決のためのコンテキストに AS2To プロパティを書き込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="90774-111">When you are using a dynamic send port, the AS2To property must be written to the context for agreement resolution.</span></span>  
  
3. <span data-ttu-id="90774-112">前の手順が失敗した場合、送信パイプラインは、アグリーメントに関連付けられている送信ポートと、メッセージをサブスクライブしている送信ポートとの照合を試みます。</span><span class="sxs-lookup"><span data-stu-id="90774-112">If the previous step fails, the send pipeline will attempt to match the send port that is associated with an agreement with the send port that subscribed to the message.</span></span> <span data-ttu-id="90774-113">送信ポートがアグリーメントに関連付け、**送信ポート**の一方向の AS2 アグリーメントのページ、**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="90774-113">The send port is associated with the agreement in the **Send Ports** page of the one-way AS2 agreement of the **Agreement Properties** dialog box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="90774-114">EDI 処理とは異なり、アグリーメントを特定できない場合に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が使用できるフォールバック AS2 プロパティはありません。</span><span class="sxs-lookup"><span data-stu-id="90774-114">Unlike in EDI processing, there are no fallback AS2 properties that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can use if it cannot determine the agreement.</span></span> <span data-ttu-id="90774-115">ただし、MDN の送信に使用される既定のアグリーメントがあります。</span><span class="sxs-lookup"><span data-stu-id="90774-115">There is, however, a default agreement used to send an MDN.</span></span> <span data-ttu-id="90774-116">また、送信ポートも Http.UserHttpHeaders コンテキスト プロパティも、MDN のアグリーメントの解決には使用されません。</span><span class="sxs-lookup"><span data-stu-id="90774-116">In addition, neither the send port nor the Http.UserHttpHeaders context property is used to resolve the agreement for an MDN.</span></span> <span data-ttu-id="90774-117">詳細については、の「アグリーメント解決の MDN」セクションを参照してください。[送信 MDN の送信](../core/sending-an-outgoing-mdn.md)します。</span><span class="sxs-lookup"><span data-stu-id="90774-117">For more information, see the "Agreement Resolution for an MDN" section of [Sending an Outgoing MDN](../core/sending-an-outgoing-mdn.md).</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="90774-118">場合、AS2 のアグリーメントのプロパティを**識別子**の一方向の AS2 アグリーメントのページ、**アグリーメントのプロパティ** ダイアログ ボックスは既定では英語のパーティ名、および AS2 の値に設定-ヘッダーas2 メッセージは英語以外の名前を設定し、一致が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="90774-118">If the AS2-To agreement property in the **Identifiers** page of the one-way AS2 agreement of the **Agreement Properties** dialog box is set by default to an English party name, and the value in the AS2-To header of the AS2 message is set to a non-English name, then the match will not be found.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="90774-119">AS2 経由で EDI を送信する場合、EDI と AS2 の両方に個別のアグリーメントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90774-119">When sending EDI over AS2, you are required to use separate agreements for both EDI and AS2.</span></span>  
  
 <span data-ttu-id="90774-120">送信プロセスの詳細については、[送信 AS2 メッセージを生成する](../core/generating-an-outgoing-as2-message.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90774-120">For more details on the send process, see [Generating an Outgoing AS2 Message](../core/generating-an-outgoing-as2-message.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90774-121">参照</span><span class="sxs-lookup"><span data-stu-id="90774-121">See Also</span></span>  
 [<span data-ttu-id="90774-122">BizTalk Server が AS2 メッセージを送信する方法</span><span class="sxs-lookup"><span data-stu-id="90774-122">How BizTalk Server Sends AS2 Messages</span></span>](../core/how-biztalk-server-sends-as2-messages.md)