---
title: 失敗したメッセージのルーティングを有効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d33beed4-1ae2-4282-95ac-5d68aab7fb5d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c00e49afa528bc0008d73272dca561d461660367
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008491"
---
# <a name="how-to-enable-routing-for-failed-messages"></a><span data-ttu-id="0c5e7-102">失敗したメッセージのルーティングを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="0c5e7-102">How to Enable Routing for Failed Messages</span></span>
<span data-ttu-id="0c5e7-103">失敗したメッセージのルーティングは送受信ポートのプロパティの一種であり、ポートのプロパティ ページで [失敗したメッセージをルーティングする] を指定すると有効になります。</span><span class="sxs-lookup"><span data-stu-id="0c5e7-103">Failed message routing is a property of send and receive ports, and is enabled by indicating "Enable routing for failed messages" on the port's property page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c5e7-104">受信ポートの構成は、その受信ポートに関連付けられているすべての受信場所に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0c5e7-104">The configuration on a receive port applies to all receive locations associated with that receive port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c5e7-105">送信ポートの構成は、プライマリ トランスポートとバックアップ トランスポートの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0c5e7-105">The configuration on a send port applies to both the primary and backup transports.</span></span>  
  
### <a name="to-configure-failed-message-routing-for-a-receive-port-this-applies-to-both-one-way-and-request-response-receive-ports"></a><span data-ttu-id="0c5e7-106">失敗したメッセージのルーティングを受信ポートに対して構成するには (一方向の受信ポートと要求 - 応答の受信ポートの両方に適用)</span><span class="sxs-lookup"><span data-stu-id="0c5e7-106">To configure failed message routing for a receive port (this applies to both one-way and request-response receive ports)</span></span>  
  
1. <span data-ttu-id="0c5e7-107">BizTalk Server 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="0c5e7-107">Open the BizTalk Server Administration console.</span></span>  
  
2. <span data-ttu-id="0c5e7-108">展開[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**アプリケーション**、し、送信ポートが所属するアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="0c5e7-108">Expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the application to which the send port belongs.</span></span>  
  
3. <span data-ttu-id="0c5e7-109">をクリックして、**受信ポート**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="0c5e7-109">Click the **Receive Ports** folder.</span></span>  
  
4. <span data-ttu-id="0c5e7-110">右ペインで、構成する受信ポートの名前をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c5e7-110">In the right pane, double-click the name of the receive port you want to configure.</span></span>  
  
5. <span data-ttu-id="0c5e7-111">左側のウィンドウで、受信ポートのプロパティ ページで選択、**全般**カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="0c5e7-111">On the receive port's property page, in the left pane, select the **General** category.</span></span>  
  
6. <span data-ttu-id="0c5e7-112">右側のウィンドウで、選択、**失敗したメッセージのルーティングを有効にする**チェック ボックスをオンにして**適用**します。</span><span class="sxs-lookup"><span data-stu-id="0c5e7-112">In the right pane, select the **Enable routing for failed messages** check box, and then click **Apply**.</span></span>  
  
### <a name="to-configure-failed-message-routing-for-a-send-port-this-applies-only-to-static-one-way-and-static-solicit-response-send-ports"></a><span data-ttu-id="0c5e7-113">失敗したメッセージのルーティングを送信ポートに対して構成するには (静的な一方向の送信ポートと静的な送信請求 - 応答の送信ポートにのみ適用)</span><span class="sxs-lookup"><span data-stu-id="0c5e7-113">To configure failed message routing for a send port (this applies only to static one-way and static solicit-response send ports)</span></span>  
  
1. <span data-ttu-id="0c5e7-114">BizTalk Server 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="0c5e7-114">Open the BizTalk Server Administration console.</span></span>  
  
2. <span data-ttu-id="0c5e7-115">展開[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**アプリケーション**、し、送信ポートが所属するアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="0c5e7-115">Expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the application to which the send port belongs.</span></span>  
  
3. <span data-ttu-id="0c5e7-116">をクリックして、**送信ポート**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="0c5e7-116">Click the **Send Ports** folder.</span></span>  
  
4. <span data-ttu-id="0c5e7-117">右ペインで、構成する送信ポートの名前をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c5e7-117">In the right pane, double-click the name of the send port you want to configure.</span></span>  
  
5. <span data-ttu-id="0c5e7-118">送信ポートのプロパティ ページで、左側のウィンドウで選択、**トランスポートの詳細オプション**カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="0c5e7-118">On the send port's property page, in the left pane, select the **Transport Advanced Options** category.</span></span>  
  
6. <span data-ttu-id="0c5e7-119">右側のウィンドウでの**トランスポート オプション**グループ ボックスで、**失敗したメッセージのルーティングを有効にする**チェック ボックスをオンにして**適用**。</span><span class="sxs-lookup"><span data-stu-id="0c5e7-119">In the right pane, in the **Transport Options** group box, select the **Enable routing for failed messages** check box, and then click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c5e7-120">参照</span><span class="sxs-lookup"><span data-stu-id="0c5e7-120">See Also</span></span>  
 [<span data-ttu-id="0c5e7-121">エラー処理</span><span class="sxs-lookup"><span data-stu-id="0c5e7-121">Error Handling</span></span>](../core/error-handling.md)