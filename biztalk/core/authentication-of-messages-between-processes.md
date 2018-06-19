---
title: プロセス間でメッセージの認証 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PID
- security, warnings
- processing, messages
- processing, security
- messages, processing
- security, messages
- MessageBox database, authenticating
- SSID
- authenticating, warnings
ms.assetid: fa746ee3-fc22-4e63-a5cc-8bc0cbeb536b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c54fb463353ed6551dcbf5764fae05e63fdb778
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231306"
---
# <a name="authentication-of-messages-between-processes"></a><span data-ttu-id="efa66-102">プロセス間でメッセージの認証</span><span class="sxs-lookup"><span data-stu-id="efa66-102">Authentication of Messages Between Processes</span></span>
<span data-ttu-id="efa66-103">次の図に、BizTalk ホスト間でメッセージの認証に使用できる BizTalk Server のセキュリティ機能を示します。</span><span class="sxs-lookup"><span data-stu-id="efa66-103">The following figure shows the security features in BizTalk Server that enable you to authenticate messages between different BizTalk hosts.</span></span>  
  
 <span data-ttu-id="efa66-104">![メッセージを認証するセキュリティ機能](../core/media/ebiz-plan-secoverview-auth-process.gif "ebiz_plan_secoverview_auth_process")</span><span class="sxs-lookup"><span data-stu-id="efa66-104">![Security features authenticating messages](../core/media/ebiz-plan-secoverview-auth-process.gif "ebiz_plan_secoverview_auth_process")</span></span>  
<span data-ttu-id="efa66-105">BizTalk Server でプロセス間のメッセージ認証に使用されるセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="efa66-105">Security features BizTalk Server uses to authenticate messages between processes.</span></span>  
  
 <span data-ttu-id="efa66-106">BizTalk Server で、メッセージが受信、解読、検証され、メッセージの送信者を識別する有効なパーティ ID (PID) と証明書が取得されると、メッセージ ボックス データベースでは、メッセージに一致するサブスクリプションを確認して後続の処理用にメッセージを他のホストに送信する準備ができたことになります。</span><span class="sxs-lookup"><span data-stu-id="efa66-106">After BizTalk Server receives a message, decrypts and validates the message, and has a valid party ID (PID) and certificate to identity the sender of the message, the MessageBox database is ready to verify the subscriptions that the message matches, and to send this message to other hosts for further processing.</span></span>  
  
 <span data-ttu-id="efa66-107">メッセージがプロセス間で受け渡される際には、承認、パーティの解決、送信者に関連するビジネス ロジックでの使用などの目的で、下流のプロセスにメッセージの元の送信者 ID を渡す必要が生じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="efa66-107">As a message flows from one process to another, it is often necessary to pass the identity of the original sender of the message to downstream processes for authorization, party resolution, and business logic relating to the sender.</span></span> <span data-ttu-id="efa66-108">しかし、すべてのホストに対し、セキュリティまたは信頼メカニズムを使用せずにこの情報を送信することを許可すると、すべてのユーザー オブジェクトとコード (オーケストレーション、アダプタ、パイプライン コンポーネント、Functoid など) について信頼性を検証する必要があり、負荷が非常に大きくなります。</span><span class="sxs-lookup"><span data-stu-id="efa66-108">However, enabling all hosts to flow this information without some type of security or trust mechanism would greatly increase the need to verify that all user objects and code (for example, orchestrations, adapters, pipeline components, functoids) are trustworthy.</span></span>  
  
 <span data-ttu-id="efa66-109">BizTalk Server では、ユーザー オブジェクトやコードの信頼性レベルを区別する方法として、ホストのプロパティとして提供されている "信頼されている認証" を使用できます。</span><span class="sxs-lookup"><span data-stu-id="efa66-109">To provide the means to differentiate the level of trust for user objects and code, BizTalk Server provides Authentication Trust as a property of hosts.</span></span> <span data-ttu-id="efa66-110">認証が信頼済みに設定されていないホストからメッセージを受信した場合、メッセージ ボックス データベースではメッセージの PID が Guest ID で上書きされ、SSID がホスト インスタンスを実行しているサービス アカウントで上書きされます。</span><span class="sxs-lookup"><span data-stu-id="efa66-110">When the MessageBox database receives a message from a host that has not been set as authentication trusted, the MessageBox database overwrites the PID with the guest ID, and overwrites the SSID with the service account that the host instance is running as.</span></span> <span data-ttu-id="efa66-111">認証が信頼済みに設定されているホストでは、メッセージ ボックス データベースにキュー送信するメッセージに任意の送信者 SID (SSID) および任意のパーティ ID (PID) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="efa66-111">When a host is marked as authentication trusted, BizTalk enables the host to specify any sender SID (SSID) and any party ID (PID) on messages that it queues to the MessageBox database.</span></span>  
  
 <span data-ttu-id="efa66-112">信頼済みのホストとそうでないホストを区別することで、ユーザー オブジェクトとコードを信頼できるかどうかのセキュリティ処理境界を定義できます。</span><span class="sxs-lookup"><span data-stu-id="efa66-112">By specifying which hosts are trusted and which are not, you can define security boundaries in which user objects and code can be trusted or not trusted.</span></span> <span data-ttu-id="efa66-113">つまり、認証が信頼済みに設定されているホストに展開されるユーザー オブジェクトとコードは、認証が信頼済みに設定されていないホストに展開されるユーザー オブジェクトとコードより信頼できます。</span><span class="sxs-lookup"><span data-stu-id="efa66-113">That is, user objects and code deployed into hosts that have been set to Authentication Trusted need to be more trustworthy than user objects and code deployed to hosts that have not been set to Authentication Trusted.</span></span> <span data-ttu-id="efa66-114">信頼済み認証ホストを構成する方法の詳細については、次を参照してください。[ホストのプロパティを変更する方法](../core/how-to-modify-host-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="efa66-114">For more information about how to configure authentication trusted host, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
 <span data-ttu-id="efa66-115">メッセージ ボックス データベースがメッセージを受信すると、BizTalk Server では以下の手順が実行され、メッセージ ボックス データベースにメッセージを送信したホスト インスタンスの認証が信頼済みであることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="efa66-115">When the MessageBox database receives a message, BizTalk Server takes the following steps to enforce the authentication trust of the host instance sending the message to the MessageBox database:</span></span>  
  
1.  <span data-ttu-id="efa66-116">最初に、メッセージ ボックス データベースで、メッセージを送信したホストの認証が信頼済みに設定されているかどうかが判定されます。これは、そのホストの SSID が信頼済みホストのホスト インスタンス サービス アカウントの SSID であるかどうかを確認することで行われます。</span><span class="sxs-lookup"><span data-stu-id="efa66-116">The MessageBox database first determines whether the host sending the message has been set as authentication trusted by checking that the SSID is that of a host instance service account for a trusted host.</span></span>  
  
2.  <span data-ttu-id="efa66-117">メッセージ ボックス データベースにメッセージを送信したホストの認証が信頼済みに設定されている場合、メッセージ コンテキストの SSID と PID は、空でない限りそのまま残されます。</span><span class="sxs-lookup"><span data-stu-id="efa66-117">If the host that is sending the message to the MessageBox database is authentication trusted, the MessageBox database leaves the SSID and PID in the message context "as is," unless they are empty.</span></span> <span data-ttu-id="efa66-118">SSID が空の場合、メッセージ ボックス データベースでは、呼び出したプロセスの SID (ホスト SID (HSID)) が SSID として使用されます。</span><span class="sxs-lookup"><span data-stu-id="efa66-118">If the SSID is empty, the MessageBox database populates it with the SID of the calling process, also known as the host SID (HSID).</span></span> <span data-ttu-id="efa66-119">PID が空の場合は、Guest ID が PID として設定されます。</span><span class="sxs-lookup"><span data-stu-id="efa66-119">If the PID is empty, it sets the PID to the guest ID.</span></span>  
  
3.  <span data-ttu-id="efa66-120">メッセージ ボックス データベースにメッセージを送信したホストの認証が信頼済みに設定されていない場合は、SSID と PID が既に設定されているかどうかに関係なく、SSID には HSID が設定され、PID には Guest ID が設定されます。</span><span class="sxs-lookup"><span data-stu-id="efa66-120">If the host that is sending the message to the MessageBox database has not been set as authentication trusted, the SSID is populated with the HSID, and the PID is set to Guest, regardless of whether these fields were already populated.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="efa66-121">下流のプロセスでメッセージの元の送信者の SSID と PID が必要な場合は、メッセージが通過するすべてのホストの認証を信頼済みに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efa66-121">If you want a downstream process to know the SSID and PID of the original sender of the message, you must set all hosts that the message passes through as authentication trusted.</span></span> <span data-ttu-id="efa66-122">また、オーケストレーションで受信したメッセージを送信メッセージの作成に使用する場合などは、受信メッセージの SSID と PID を送信メッセージのプロパティとして明示的に追加し、下流のプロセスに渡されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="efa66-122">In addition, in cases such as when the message is received and subsequently used to construct outbound messages in an orchestration, the SSID and PID received on inbound messages must be explicitly added as a property to outbound messages in order to flow these identities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="efa66-123">パイプラインが実行されているホストに対し認証を信頼済みとして構成した場合、BizTalk Server でそのパイプラインは信頼済みの環境と見なされます。</span><span class="sxs-lookup"><span data-stu-id="efa66-123">If you configured the host where a pipeline is running as authentication trusted, BizTalk Server considers the pipeline to be a trusted environment.</span></span> <span data-ttu-id="efa66-124">そのため、認証が信頼済みとなっているホストで実行されている BizTalk パイプラインについては、含まれるすべてのカスタム コンポーネントが信頼済みかどうかを確認することが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="efa66-124">Therefore, it is extremely important that you verify that any custom components that are included in a BizTalk pipeline that is running on a host that is authentication trusted are also trusted.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="efa66-125">認証が信頼済みであるホストと信頼されている認証されていないホストで同じサービス アカウントを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="efa66-125">You cannot use the same service account for hosts that are authentication trusted and for hosts that are not authentication trusted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efa66-126">参照</span><span class="sxs-lookup"><span data-stu-id="efa66-126">See Also</span></span>  
 <span data-ttu-id="efa66-127">[受信メッセージの認証](../core/inbound-message-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="efa66-127">[Inbound Message Authentication](../core/inbound-message-authentication.md) </span></span>  
 <span data-ttu-id="efa66-128">[送信メッセージの保護](../core/outbound-message-protection.md) </span><span class="sxs-lookup"><span data-stu-id="efa66-128">[Outbound Message Protection](../core/outbound-message-protection.md) </span></span>  
 <span data-ttu-id="efa66-129">[メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md) </span><span class="sxs-lookup"><span data-stu-id="efa66-129">[Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md) </span></span>  
 [<span data-ttu-id="efa66-130">メッセージの受信者の承認</span><span class="sxs-lookup"><span data-stu-id="efa66-130">Authorizing the Receiver of a Message</span></span>](../core/authorizing-the-receiver-of-a-message.md)