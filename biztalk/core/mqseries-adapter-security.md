---
title: "MQSeries アダプタのセキュリティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, MQSeries adapters
- MQSeries adapters, security
ms.assetid: 0bd82c21-6b77-4a66-a4e9-4a91ba4a56c4
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08d5228dab8463c2ad5dc7f9d9347899d4c41a67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="security-with-the-mqseries-adapter"></a><span data-ttu-id="5f816-102">MQSeries アダプタでのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="5f816-102">Security with the MQSeries adapter</span></span>

<span data-ttu-id="5f816-103">MQSeries アダプタをセキュリティで保護するには、BizTalk Server と MQSeries Server をセキュリティで保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f816-103">MQSeries adapter security begins with securing your BizTalk and MQSeries servers.</span></span> <span data-ttu-id="5f816-104">BizTalk Server の保護方法の詳細については、次を参照してください。[セキュリティで保護されたデータの保護と](secure-and-protect-your-biztalk-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="5f816-104">For information about securing BizTalk Server, see [Secure and protect your data](secure-and-protect-your-biztalk-messages.md).</span></span> <span data-ttu-id="5f816-105">MQSeries Server をセキュリティで保護する方法の詳細については、IBM MQSeries Server のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f816-105">For information about MQSeries Server security, see the IBM MQSeries Server documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f816-106">MQSeries アダプタでは、BizTalk Server と MQSeries Server 間のメッセージの送受信にパケット プライバシーが自動的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5f816-106">The adapter automatically uses packet privacy for sending and receiving messages between BizTalk Server and MQSeries Server.</span></span>  

## <a name="adapter-security"></a><span data-ttu-id="5f816-107">アダプタのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="5f816-107">Adapter security</span></span>  
 <span data-ttu-id="5f816-108">アダプタ自体をセキュリティで保護した状態で使用するには、次の 4 つの事項に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f816-108">Using the adapter itself securely requires attention to four areas:</span></span>  
  
-   <span data-ttu-id="5f816-109">MQSAgent 用のアプリケーション ID とメンバの選択</span><span class="sxs-lookup"><span data-stu-id="5f816-109">Choosing the application identity and members for MQSAgent</span></span>  
  
-   <span data-ttu-id="5f816-110">アダプタを使用した、BizTalk Server アカウントの管理</span><span class="sxs-lookup"><span data-stu-id="5f816-110">Controlling the BizTalk Server accounts using the adapter</span></span>  
  
-   <span data-ttu-id="5f816-111">キュー作成スクリプトのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="5f816-111">Securing the queue creation scripts</span></span>  
  
-   <span data-ttu-id="5f816-112">適切な使用、 **SSO 関連アプリケーション**プロパティ</span><span class="sxs-lookup"><span data-stu-id="5f816-112">Making appropriate use of the **SSO Affiliate Application** property</span></span>  
  
 <span data-ttu-id="5f816-113">構成時にアプリケーション ID に割り当てられるアカウントは、管理者アカウント以外のアカウントにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f816-113">The account assigned to the application identity during configuration should not be an administrator account.</span></span> <span data-ttu-id="5f816-114">アカウントに最低限の権限が必要ではなく、— 読み取りおよび書き込みアクセス、MQSeries キューをします。</span><span class="sxs-lookup"><span data-stu-id="5f816-114">Rather, the account should have the minimum required privileges—read and write access to the MQSeries queues.</span></span>  
  
 <span data-ttu-id="5f816-115">MQSAgent のロールには、アダプタを使用して BizTalk Server アカウントのみを割り当てるようにします。</span><span class="sxs-lookup"><span data-stu-id="5f816-115">Make sure that you assign only BizTalk Server accounts using the adapter to the MQSAgent role.</span></span>  
  
 <span data-ttu-id="5f816-116">キュー定義の処理中に作成されたスクリプトをエクスポートして使用する場合、スクリプトはセキュリティで保護された場所に格納するようにします。</span><span class="sxs-lookup"><span data-stu-id="5f816-116">When using exported scripts created during the queue definition process, keep the scripts in a secure area.</span></span> <span data-ttu-id="5f816-117">また、管理者がスクリプトを使用した場合にのみアクセスできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f816-117">Only administrators using the scripts should have access.</span></span>  
  
 <span data-ttu-id="5f816-118">アプリケーションでは、送信メッセージにユーザーの資格情報を格納する MQCIH および MQIIH ヘッダー プロパティを使用する場合を使用して、 **SSO 関連アプリケーション**プロパティを**トランスポートのプロパティ**ページ。</span><span class="sxs-lookup"><span data-stu-id="5f816-118">If your application uses MQCIH and MQIIH header properties to put user credentials in outbound messages, use the **SSO Affiliate Application** property on the **Transport Properties** page.</span></span> <span data-ttu-id="5f816-119">このプロパティの詳細については、次を参照してください。[方法を構成する MQSeries アダプターの受信場所と送信ポートに](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)です。</span><span class="sxs-lookup"><span data-stu-id="5f816-119">For more information about this property, see [How to Configure MQSeries Adapter Receive Locations and Send Ports](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f816-120">参照</span><span class="sxs-lookup"><span data-stu-id="5f816-120">See Also</span></span>  
 <span data-ttu-id="5f816-121">[MQSeries アダプターの構造](../core/structure-of-the-mqseries-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5f816-121">[Structure of the MQSeries Adapter](../core/structure-of-the-mqseries-adapter.md) </span></span>  
 [<span data-ttu-id="5f816-122">MQSeries アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="5f816-122">What Is the MQSeries Adapter?</span></span>](../core/what-is-the-mqseries-adapter.md)