---
title: 受信場所 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, properties
- receive locations, about receive locations
- receive locations
- receive locations, receive location types
ms.assetid: be5f7e5d-b63f-42f6-985e-895ba3912d34
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15ee246c07fa471cefe8f4dc42f55b0543bb8419
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024264"
---
# <a name="receive-locations"></a><span data-ttu-id="28d14-102">受信場所</span><span class="sxs-lookup"><span data-stu-id="28d14-102">Receive Locations</span></span>
<span data-ttu-id="28d14-103">受信場所の作成時には、着信メッセージを受信するアドレスと、そのアドレスで受信したメッセージを処理するメッセージング パイプラインを指定します。</span><span class="sxs-lookup"><span data-stu-id="28d14-103">Creating a receive location involves specifying an address at which inbound messages arrive and the messaging pipeline that processes the message received at that address.</span></span> <span data-ttu-id="28d14-104">受信場所の作成および有効化は、管理者のみが行えます。</span><span class="sxs-lookup"><span data-stu-id="28d14-104">Only administrators can create and enable receive locations.</span></span>  
  
 <span data-ttu-id="28d14-105">管理者は BizTalk 管理コンソールを使用して、受信場所を作成し、オーケストレーションにバインドし、有効または無効にし、受信場所のグローバル プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="28d14-105">An administrator uses the BizTalk Administration Console to create receive locations, bind receive locations to orchestrations, enable receive locations, disable receive locations, and set global properties for receive locations.</span></span>  
  
 <span data-ttu-id="28d14-106">管理者 (BizTalk 管理コンソールを使用) は、以下の手順に従って受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="28d14-106">An administrator (using the BizTalk Administration Console) follows these steps to create a receive location:</span></span>  
  
1.  <span data-ttu-id="28d14-107">受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="28d14-107">Creates a receive location.</span></span>  
  
2.  <span data-ttu-id="28d14-108">受信場所をホストに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="28d14-108">Associates the receive location with a host.</span></span>  
  
3.  <span data-ttu-id="28d14-109">受信場所をオーケストレーションにバインドします。</span><span class="sxs-lookup"><span data-stu-id="28d14-109">Binds the receive location to an orchestration.</span></span>  
  
4.  <span data-ttu-id="28d14-110">受信場所を有効にします。</span><span class="sxs-lookup"><span data-stu-id="28d14-110">Enables the receive location.</span></span>  
  
5.  <span data-ttu-id="28d14-111">受信場所は、メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="28d14-111">The receive location receives messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28d14-112">Windows Management Instrumentation (WMI) で受信場所に対して行った変更は、BizTalk 管理コンソールの受信場所の表示に影響します。</span><span class="sxs-lookup"><span data-stu-id="28d14-112">Changes to receive locations made by using Windows Management Instrumentation (WMI) affect how receive locations appear in the BizTalk Administration Console.</span></span> <span data-ttu-id="28d14-113">たとえば、管理者が WMI を使用して新しい受信場所を作成した場合、その受信場所は BizTalk 管理コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="28d14-113">For example, if an administrator uses WMI to create a new receive location, that receive location appears in the BizTalk Administration Console.</span></span> <span data-ttu-id="28d14-114">同様に、管理者が受信場所を削除した場合、その受信場所は BizTalk 管理コンソールに表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="28d14-114">Similarly, if an administrator deletes a receive location, the receive location disappears from the BizTalk Administration Console.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="28d14-115">各受信場所には一意の名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="28d14-115">Each receive location must have a unique name.</span></span> <span data-ttu-id="28d14-116">2 つの受信場所と同じで、同じ名前を持つことはできません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開します。</span><span class="sxs-lookup"><span data-stu-id="28d14-116">Two receive locations cannot have the same name in the same [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]deployment.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="28d14-117">受信場所の格納先には強力なアクセス制御リスト (ACL) を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="28d14-117">We recommend that you set strong access control lists (ACL) in the drop location for the receive locations.</span></span> <span data-ttu-id="28d14-118">たとえば、ファイルの受信場所がメッセージを取得するディレクトリに強力な ACL を設定し、認証されたユーザーだけがこの場所にメッセージを格納できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="28d14-118">For example, you must set strong ACLs for the directory where the file receive location picks up messages, so that only authorized users can drop messages in this location.</span></span>  
  
## <a name="receive-location-types"></a><span data-ttu-id="28d14-119">受信場所の種類</span><span class="sxs-lookup"><span data-stu-id="28d14-119">Receive Location Types</span></span>  
 <span data-ttu-id="28d14-120">受信場所には次の 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="28d14-120">There are two types of receive locations</span></span>  
  
-   <span data-ttu-id="28d14-121">一方向。</span><span class="sxs-lookup"><span data-stu-id="28d14-121">One-way.</span></span> <span data-ttu-id="28d14-122">メッセージを格納し、同期応答を待機しないアプリケーションに使用します。</span><span class="sxs-lookup"><span data-stu-id="28d14-122">Used for applications that drop off a message and do not wait for a synchronous reply.</span></span>  
  
-   <span data-ttu-id="28d14-123">要求 - 応答。</span><span class="sxs-lookup"><span data-stu-id="28d14-123">Request-response.</span></span> <span data-ttu-id="28d14-124">メッセージへの応答を求めるアプリケーションに使用します。</span><span class="sxs-lookup"><span data-stu-id="28d14-124">Used with applications that require a response to a message.</span></span>  
  
## <a name="receive-location-properties"></a><span data-ttu-id="28d14-125">受信場所のプロパティ</span><span class="sxs-lookup"><span data-stu-id="28d14-125">Receive Location Properties</span></span>  
 <span data-ttu-id="28d14-126">受信場所にグローバルとアダプター固有のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="28d14-126">Receive locations have global and adapter-specific properties.</span></span> <span data-ttu-id="28d14-127">BizTalk 管理コンソールを使用して、管理者は、特定のアダプターに関連付けられている受信場所のすべてのグローバル プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="28d14-127">Administrators, using the BizTalk Administration Console, set global properties for all of the receive locations associated with a specific adapter.</span></span>  
  
 <span data-ttu-id="28d14-128">受信場所のプロパティへの変更は、順番に行われます。</span><span class="sxs-lookup"><span data-stu-id="28d14-128">Changes to receive location properties happen sequentially.</span></span> <span data-ttu-id="28d14-129">ソリューション開発者がプロパティ値を変更した場合、特定の受信場所、新しいプロパティ値のオーバーライドをグローバル プロパティの値の受信場所、管理者は、BizTalk 管理コンソールで設定します。</span><span class="sxs-lookup"><span data-stu-id="28d14-129">If a solutions developer modifies a property value for a specific receive location, the new property value overrides the global property value for that receive location that the administrator set in the BizTalk Administration Console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28d14-130">参照</span><span class="sxs-lookup"><span data-stu-id="28d14-130">See Also</span></span>  
 <span data-ttu-id="28d14-131">[受信場所の管理](../core/managing-receive-locations.md) </span><span class="sxs-lookup"><span data-stu-id="28d14-131">[Managing Receive Locations](../core/managing-receive-locations.md) </span></span>  
 [<span data-ttu-id="28d14-132">アイテム</span><span class="sxs-lookup"><span data-stu-id="28d14-132">Artifacts</span></span>](../core/artifacts.md)