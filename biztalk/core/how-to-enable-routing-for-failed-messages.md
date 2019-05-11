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
ms.openlocfilehash: 1e524f96114e887569c10294be0e665f1aa711a6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337940"
---
# <a name="how-to-enable-routing-for-failed-messages"></a><span data-ttu-id="36b97-102">失敗したメッセージのルーティングを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="36b97-102">How to Enable Routing for Failed Messages</span></span>
<span data-ttu-id="36b97-103">失敗したメッセージのルーティング送信のプロパティであると受信ポート、および「有効化が失敗したメッセージをルーティングする」を示すポートのプロパティ ページで有効です。</span><span class="sxs-lookup"><span data-stu-id="36b97-103">Failed message routing is a property of send and receive ports, and is enabled by indicating "Enable routing for failed messages" on the port's property page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36b97-104">受信ポートの構成は、その受信ポートに関連付けられているすべての受信場所に適用されます。</span><span class="sxs-lookup"><span data-stu-id="36b97-104">The configuration on a receive port applies to all receive locations associated with that receive port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36b97-105">送信ポートの構成は、プライマリおよびバックアップ トランスポートの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="36b97-105">The configuration on a send port applies to both the primary and backup transports.</span></span>  
  
### <a name="to-configure-failed-message-routing-for-a-receive-port-this-applies-to-both-one-way-and-request-response-receive-ports"></a><span data-ttu-id="36b97-106">失敗したメッセージのルーティングを受信ポートを構成する (一方向の両方に適用し、要求-応答受信ポート)</span><span class="sxs-lookup"><span data-stu-id="36b97-106">To configure failed message routing for a receive port (this applies to both one-way and request-response receive ports)</span></span>  
  
1. <span data-ttu-id="36b97-107">BizTalk Server 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="36b97-107">Open the BizTalk Server Administration console.</span></span>  
  
2. <span data-ttu-id="36b97-108">展開[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**アプリケーション**、し、送信ポートが所属するアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="36b97-108">Expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the application to which the send port belongs.</span></span>  
  
3. <span data-ttu-id="36b97-109">をクリックして、**受信ポート**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="36b97-109">Click the **Receive Ports** folder.</span></span>  
  
4. <span data-ttu-id="36b97-110">右側のウィンドウで、構成する受信ポートの名前をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="36b97-110">In the right pane, double-click the name of the receive port you want to configure.</span></span>  
  
5. <span data-ttu-id="36b97-111">左側のウィンドウで、受信ポートのプロパティ ページで選択、**全般**カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="36b97-111">On the receive port's property page, in the left pane, select the **General** category.</span></span>  
  
6. <span data-ttu-id="36b97-112">右側のウィンドウで、選択、**失敗したメッセージのルーティングを有効にする**チェック ボックスをオンにして**適用**します。</span><span class="sxs-lookup"><span data-stu-id="36b97-112">In the right pane, select the **Enable routing for failed messages** check box, and then click **Apply**.</span></span>  
  
### <a name="to-configure-failed-message-routing-for-a-send-port-this-applies-only-to-static-one-way-and-static-solicit-response-send-ports"></a><span data-ttu-id="36b97-113">失敗した (これは静的な一方向と静的な送信請求-応答送信ポートにのみ適用されます)、送信ポートのメッセージのルーティングを構成するには</span><span class="sxs-lookup"><span data-stu-id="36b97-113">To configure failed message routing for a send port (this applies only to static one-way and static solicit-response send ports)</span></span>  
  
1. <span data-ttu-id="36b97-114">BizTalk Server 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="36b97-114">Open the BizTalk Server Administration console.</span></span>  
  
2. <span data-ttu-id="36b97-115">展開[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**アプリケーション**、し、送信ポートが所属するアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="36b97-115">Expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the application to which the send port belongs.</span></span>  
  
3. <span data-ttu-id="36b97-116">をクリックして、**送信ポート**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="36b97-116">Click the **Send Ports** folder.</span></span>  
  
4. <span data-ttu-id="36b97-117">右側のウィンドウで、構成する送信ポートの名前をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="36b97-117">In the right pane, double-click the name of the send port you want to configure.</span></span>  
  
5. <span data-ttu-id="36b97-118">送信ポートのプロパティ ページで、左側のウィンドウで選択、**トランスポートの詳細オプション**カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="36b97-118">On the send port's property page, in the left pane, select the **Transport Advanced Options** category.</span></span>  
  
6. <span data-ttu-id="36b97-119">右側のウィンドウでの**トランスポート オプション**グループ ボックスで、**失敗したメッセージのルーティングを有効にする**チェック ボックスをオンにして**適用**。</span><span class="sxs-lookup"><span data-stu-id="36b97-119">In the right pane, in the **Transport Options** group box, select the **Enable routing for failed messages** check box, and then click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36b97-120">参照</span><span class="sxs-lookup"><span data-stu-id="36b97-120">See Also</span></span>  
 [<span data-ttu-id="36b97-121">エラー処理</span><span class="sxs-lookup"><span data-stu-id="36b97-121">Error Handling</span></span>](../core/error-handling.md)