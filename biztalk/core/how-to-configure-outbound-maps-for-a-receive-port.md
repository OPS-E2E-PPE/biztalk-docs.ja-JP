---
title: 送信マップを構成する方法、受信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- maps, outbound
- configuring, maps
- managing [receive ports], outbound maps
- maps, configuring
- receive ports, configuring
- configuring, receive ports
- receive ports, outbound maps
ms.assetid: 01a864a1-9e8c-4b82-9d03-91be09d556da
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c74fcc259b833a64a480bbe88f4cc0273d2a83c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023608"
---
# <a name="how-to-configure-outbound-maps-for-a-receive-port"></a><span data-ttu-id="4479b-102">受信ポートの送信マップを構成する方法</span><span class="sxs-lookup"><span data-stu-id="4479b-102">How to Configure Outbound Maps for a Receive Port</span></span>
<span data-ttu-id="4479b-103">このトピックでは、BizTalk Server 管理コンソールを使用して受信ポートの送信マップを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4479b-103">This topic describes how to use the BizTalk Server Administration console to configure outbound maps for a receive port.</span></span> <span data-ttu-id="4479b-104">要求 - 応答の受信ポートと共に送信マップを使用すると、送信メッセージのスキーマを別のスキーマに変換できます。たとえば、会社が使用するメッセージを取引先が使用するスキーマに変換できます。</span><span class="sxs-lookup"><span data-stu-id="4479b-104">You can use outbound maps with request-response receive ports to transform outbound messages from one schema to another; for example to transform messages that your company uses into a schema that a partner uses.</span></span>  
  
 <span data-ttu-id="4479b-105">マップを使用すると、オーケストレーションでメッセージを処理することなく、受信ポートによって送信された応答メッセージに XSL 変換を適用できます。</span><span class="sxs-lookup"><span data-stu-id="4479b-105">You use a map to apply an XSL transformation to a response message sent by the receive port without processing the message through an orchestration.</span></span> <span data-ttu-id="4479b-106">出力マップの追加、マップの削除、既存のマップから別のマップへの変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4479b-106">You can add an outbound map, remove a map, or change an existing map to a different one.</span></span> <span data-ttu-id="4479b-107">受信ポートに 1 つ以上のマップを追加することができますが、各マップには、一意の送信元スキーマが必要です。 します。</span><span class="sxs-lookup"><span data-stu-id="4479b-107">You can add more than one map to a receive port, but each map must have a unique source schema.</span></span> <span data-ttu-id="4479b-108">マップの背景については、[マップ](../core/maps.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4479b-108">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4479b-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="4479b-109">Prerequisites</span></span>  
 <span data-ttu-id="4479b-110">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4479b-110">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="4479b-111">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="4479b-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-outbound-maps-for-a-receive-port"></a><span data-ttu-id="4479b-112">受信ポートの送信マップを構成するには</span><span class="sxs-lookup"><span data-stu-id="4479b-112">To configure outbound maps for a receive port</span></span>  
  
1. <span data-ttu-id="4479b-113">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="4479b-113">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="4479b-114">コンソール ツリーで、BizTalk グループを展開し、受信ポートの送信マップを構成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="4479b-114">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure outbound maps for a receive port.</span></span>  
  
3. <span data-ttu-id="4479b-115">展開**受信ポート**は、受信ポートを右クリックし、[**プロパティ**、] をクリックし、**送信マップ**します。</span><span class="sxs-lookup"><span data-stu-id="4479b-115">Expand **Receive Ports**, right-click the receive port, click **Properties**, and then click **Outbound Maps**.</span></span>  
  
4. <span data-ttu-id="4479b-116">次の表に示すように、送信マップを構成し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="4479b-116">Configure the outbound maps as described in the following table, and then click **OK**.</span></span>  
  
   |<span data-ttu-id="4479b-117">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4479b-117">Use this</span></span>|<span data-ttu-id="4479b-118">目的</span><span class="sxs-lookup"><span data-stu-id="4479b-118">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="4479b-119">**[削除]**</span><span class="sxs-lookup"><span data-stu-id="4479b-119">**Remove**</span></span>|<span data-ttu-id="4479b-120">選択したマップを削除する場合にクリックします。</span><span class="sxs-lookup"><span data-stu-id="4479b-120">Click to remove the selected map.</span></span>|  
   |<span data-ttu-id="4479b-121">**ソース ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="4479b-121">**Source Document**</span></span>|<span data-ttu-id="4479b-122">ドロップダウン リストから、このポートで使用する送信元スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="4479b-122">From the drop-down list, select the source schema to use with this port.</span></span>|  
   |<span data-ttu-id="4479b-123">**マップ**</span><span class="sxs-lookup"><span data-stu-id="4479b-123">**Map**</span></span>|<span data-ttu-id="4479b-124">ドロップダウン リストから、このポートに関連付けるマップを選択します。</span><span class="sxs-lookup"><span data-stu-id="4479b-124">From the drop-down list, select the map you want to associate with this port.</span></span>|  
   |<span data-ttu-id="4479b-125">**送信先ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="4479b-125">**Target Document**</span></span>|<span data-ttu-id="4479b-126">ドロップダウン リストから、このポートで使用する送信先スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="4479b-126">From the drop-down list, select the destination schema to use with this port.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4479b-127">参照</span><span class="sxs-lookup"><span data-stu-id="4479b-127">See Also</span></span>  
 <span data-ttu-id="4479b-128">[受信ポートの管理](../core/managing-receive-ports.md) </span><span class="sxs-lookup"><span data-stu-id="4479b-128">[Managing Receive Ports](../core/managing-receive-ports.md) </span></span>  
 [<span data-ttu-id="4479b-129">マップの管理</span><span class="sxs-lookup"><span data-stu-id="4479b-129">Managing Maps</span></span>](../core/managing-maps.md)