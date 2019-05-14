---
title: プロセス間のメッセージの認証 |Microsoft Docs
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
ms.openlocfilehash: 0491946d3e8398fa56914b9f9ff4aaa89edb9228
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358764"
---
# <a name="authentication-of-messages-between-processes"></a><span data-ttu-id="3bf74-102">プロセス間のメッセージの認証</span><span class="sxs-lookup"><span data-stu-id="3bf74-102">Authentication of Messages Between Processes</span></span>
<span data-ttu-id="3bf74-103">次の図は、BizTalk server の別の BizTalk ホスト間でメッセージを認証に使用できるセキュリティ機能を示します。</span><span class="sxs-lookup"><span data-stu-id="3bf74-103">The following figure shows the security features in BizTalk Server that enable you to authenticate messages between different BizTalk hosts.</span></span>  
  
 <span data-ttu-id="3bf74-104">![メッセージを認証するセキュリティ機能](../core/media/ebiz-plan-secoverview-auth-process.gif "ebiz_plan_secoverview_auth_process")</span><span class="sxs-lookup"><span data-stu-id="3bf74-104">![Security features authenticating messages](../core/media/ebiz-plan-secoverview-auth-process.gif "ebiz_plan_secoverview_auth_process")</span></span>  
<span data-ttu-id="3bf74-105">BizTalk Server のセキュリティ機能は、プロセス間でメッセージの認証に使用します。</span><span class="sxs-lookup"><span data-stu-id="3bf74-105">Security features BizTalk Server uses to authenticate messages between processes.</span></span>  
  
 <span data-ttu-id="3bf74-106">メッセージ ボックス データベースは、メッセージに一致するサブスクリプションを確認して、これを送信する準備ができて、BizTalk Server でメッセージを受信し、復号化、メッセージの検証し、には、有効なパーティ ID (PID) と、メッセージの送信者を識別する証明書、します。その他のホストをさらに処理するメッセージ。</span><span class="sxs-lookup"><span data-stu-id="3bf74-106">After BizTalk Server receives a message, decrypts and validates the message, and has a valid party ID (PID) and certificate to identity the sender of the message, the MessageBox database is ready to verify the subscriptions that the message matches, and to send this message to other hosts for further processing.</span></span>  
  
 <span data-ttu-id="3bf74-107">メッセージは、別の 1 つのプロセスからフロー、承認、パーティの解決、送信者に関連するビジネス ロジックの下流のプロセスにメッセージの元の送信者の id を渡す必要が多くの場合。</span><span class="sxs-lookup"><span data-stu-id="3bf74-107">As a message flows from one process to another, it is often necessary to pass the identity of the original sender of the message to downstream processes for authorization, party resolution, and business logic relating to the sender.</span></span> <span data-ttu-id="3bf74-108">ただし、すべてのホストのセキュリティまたは信頼メカニズムを使用せずには、この情報のフローを有効にするは大幅に増加するすべてのユーザーがオブジェクトし、コードを検証する必要が (たとえば、オーケストレーション、アダプタ、パイプライン コンポーネント、functoid) が信頼できます.</span><span class="sxs-lookup"><span data-stu-id="3bf74-108">However, enabling all hosts to flow this information without some type of security or trust mechanism would greatly increase the need to verify that all user objects and code (for example, orchestrations, adapters, pipeline components, functoids) are trustworthy.</span></span>  
  
 <span data-ttu-id="3bf74-109">ユーザー オブジェクトとコードの信頼のレベルを区別するための手段を提供するには、BizTalk Server は、ホストのプロパティとして、信頼済み認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="3bf74-109">To provide the means to differentiate the level of trust for user objects and code, BizTalk Server provides Authentication Trust as a property of hosts.</span></span> <span data-ttu-id="3bf74-110">メッセージ ボックス データベースが信頼された認証として設定されていないホストからメッセージを受信したときに、メッセージ ボックス データベースは、PID で guest ID で上書きし、として実行しているホスト インスタンス サービス アカウントを持つ、SSID を上書きします。</span><span class="sxs-lookup"><span data-stu-id="3bf74-110">When the MessageBox database receives a message from a host that has not been set as authentication trusted, the MessageBox database overwrites the PID with the guest ID, and overwrites the SSID with the service account that the host instance is running as.</span></span> <span data-ttu-id="3bf74-111">認証が信頼済みとしてマークされたホストは、BizTalk により、すべての送信者 SID (SSID) を指定するホストとメッセージ ボックス データベースにキューにメッセージに任意のパーティ ID (PID)。</span><span class="sxs-lookup"><span data-stu-id="3bf74-111">When a host is marked as authentication trusted, BizTalk enables the host to specify any sender SID (SSID) and any party ID (PID) on messages that it queues to the MessageBox database.</span></span>  
  
 <span data-ttu-id="3bf74-112">ホストが信頼されているとサポートされないを指定すると、ユーザー オブジェクトとコード信頼したり、信頼されていないセキュリティ境界を定義できます。</span><span class="sxs-lookup"><span data-stu-id="3bf74-112">By specifying which hosts are trusted and which are not, you can define security boundaries in which user objects and code can be trusted or not trusted.</span></span> <span data-ttu-id="3bf74-113">つまり、ユーザー オブジェクトと信頼されている認証に設定されているホストに展開されたコードをユーザー オブジェクトとコードが信頼されている認証に設定されていないホストに展開するよりも信頼性を向上する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bf74-113">That is, user objects and code deployed into hosts that have been set to Authentication Trusted need to be more trustworthy than user objects and code deployed to hosts that have not been set to Authentication Trusted.</span></span> <span data-ttu-id="3bf74-114">信頼済み認証ホストを構成する方法の詳細については、次を参照してください。[ホスト プロパティを変更する方法](../core/how-to-modify-host-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="3bf74-114">For more information about how to configure authentication trusted host, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
 <span data-ttu-id="3bf74-115">メッセージ ボックス データベースでは、メッセージを受信したときに、BizTalk Server はメッセージ ボックス データベースにメッセージを送信したホスト インスタンスの信頼済み認証を強制する、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3bf74-115">When the MessageBox database receives a message, BizTalk Server takes the following steps to enforce the authentication trust of the host instance sending the message to the MessageBox database:</span></span>  
  
1.  <span data-ttu-id="3bf74-116">まず、メッセージ ボックス データベースは、メッセージを送信したホストが SSID が信頼済みホストのホスト インスタンス サービス アカウントのことを確認して信頼された認証として設定されているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="3bf74-116">The MessageBox database first determines whether the host sending the message has been set as authentication trusted by checking that the SSID is that of a host instance service account for a trusted host.</span></span>  
  
2.  <span data-ttu-id="3bf74-117">場合は、ホスト、メッセージ ボックス データベースにメッセージを送信するが、信頼されている認証、メッセージ ボックス データベースは"現状有姿のメッセージ コンテキストに SSID と PID を残します空でない限り、します。</span><span class="sxs-lookup"><span data-stu-id="3bf74-117">If the host that is sending the message to the MessageBox database is authentication trusted, the MessageBox database leaves the SSID and PID in the message context "as is," unless they are empty.</span></span> <span data-ttu-id="3bf74-118">SSID が空の場合、メッセージ ボックス データベースを設定します、SID の呼び出し元のプロセスでは、ホスト SID (HSID)) とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="3bf74-118">If the SSID is empty, the MessageBox database populates it with the SID of the calling process, also known as the host SID (HSID).</span></span> <span data-ttu-id="3bf74-119">ゲスト id PID として設定されます、PID が空の場合</span><span class="sxs-lookup"><span data-stu-id="3bf74-119">If the PID is empty, it sets the PID to the guest ID.</span></span>  
  
3.  <span data-ttu-id="3bf74-120">HSID と PID が送信して、MessageBox データベースにメッセージが認証、SSID が信頼済みとして設定されていないホストが設定されている場合は、これらのフィールドが既に読み込まれているかどうかに関係なく、ゲストに設定されます。</span><span class="sxs-lookup"><span data-stu-id="3bf74-120">If the host that is sending the message to the MessageBox database has not been set as authentication trusted, the SSID is populated with the HSID, and the PID is set to Guest, regardless of whether these fields were already populated.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3bf74-121">SSID と PID は、メッセージの元の送信者の下流のプロセスを実行する場合に、信頼された認証として、メッセージが通過するすべてのホストを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bf74-121">If you want a downstream process to know the SSID and PID of the original sender of the message, you must set all hosts that the message passes through as authentication trusted.</span></span> <span data-ttu-id="3bf74-122">さらに、場合 SSID と PID がで受信したメッセージは受信し、送信メッセージをオーケストレーションの作成に使用するなどの受信メッセージする必要があります明示的にプロパティとして追加されます、これらをフローするためにメッセージを送信するid。</span><span class="sxs-lookup"><span data-stu-id="3bf74-122">In addition, in cases such as when the message is received and subsequently used to construct outbound messages in an orchestration, the SSID and PID received on inbound messages must be explicitly added as a property to outbound messages in order to flow these identities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3bf74-123">認証が信頼済みパイプラインが実行されているホストを構成した場合、BizTalk Server は、パイプライン、信頼された環境を考慮します。</span><span class="sxs-lookup"><span data-stu-id="3bf74-123">If you configured the host where a pipeline is running as authentication trusted, BizTalk Server considers the pipeline to be a trusted environment.</span></span> <span data-ttu-id="3bf74-124">そのため、認証が信頼済みであるホストで実行されている BizTalk パイプラインに含まれているすべてのカスタム コンポーネントが信頼されてもことを確認することが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="3bf74-124">Therefore, it is extremely important that you verify that any custom components that are included in a BizTalk pipeline that is running on a host that is authentication trusted are also trusted.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3bf74-125">認証が信頼済みであるホストと信頼されている認証ではないホストを同じサービス アカウントを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3bf74-125">You cannot use the same service account for hosts that are authentication trusted and for hosts that are not authentication trusted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bf74-126">参照</span><span class="sxs-lookup"><span data-stu-id="3bf74-126">See Also</span></span>  
 <span data-ttu-id="3bf74-127">[受信メッセージの認証](../core/inbound-message-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="3bf74-127">[Inbound Message Authentication](../core/inbound-message-authentication.md) </span></span>  
 <span data-ttu-id="3bf74-128">[送信メッセージの保護](../core/outbound-message-protection.md) </span><span class="sxs-lookup"><span data-stu-id="3bf74-128">[Outbound Message Protection](../core/outbound-message-protection.md) </span></span>  
 <span data-ttu-id="3bf74-129">[メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md) </span><span class="sxs-lookup"><span data-stu-id="3bf74-129">[Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md) </span></span>  
 [<span data-ttu-id="3bf74-130">メッセージの受信者の承認</span><span class="sxs-lookup"><span data-stu-id="3bf74-130">Authorizing the Receiver of a Message</span></span>](../core/authorizing-the-receiver-of-a-message.md)