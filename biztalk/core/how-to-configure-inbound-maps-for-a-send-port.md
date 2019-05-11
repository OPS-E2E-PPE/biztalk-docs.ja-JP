---
title: 送信ポートの受信マップを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [send ports], inbound maps
- configuring, send ports
- send ports, inbound maps
- configuring, inbound maps
- managing [send ports], configuring
- send ports, configuring
ms.assetid: 213c66ba-928f-4c00-9a87-f45eaa9f7dca
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65b08e147e95f2fdb899784c373a3dc69013c8b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386237"
---
# <a name="how-to-configure-inbound-maps-for-a-send-port"></a><span data-ttu-id="8e054-102">送信ポートの受信マップを構成する方法</span><span class="sxs-lookup"><span data-stu-id="8e054-102">How to Configure Inbound Maps for a Send Port</span></span>
<span data-ttu-id="8e054-103">このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートの受信マップを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8e054-103">This topic describes how to use the BizTalk Server Administration console to configure inbound maps for a send port.</span></span> <span data-ttu-id="8e054-104">受信マップは、動的または静的な送信請求 - 応答の送信ポートでのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="8e054-104">Inbound maps are used only with dynamic or static solicit-response send ports.</span></span> <span data-ttu-id="8e054-105">マップを使用すると、オーケストレーションでメッセージを処理することなく、ポートが受け取った応答メッセージに XSL 変換を適用できます。</span><span class="sxs-lookup"><span data-stu-id="8e054-105">You use a map to apply an XSL transformation to a response message received by the port without processing the message through an orchestration.</span></span> <span data-ttu-id="8e054-106">受信マップの追加、マップの削除、既存のマップから別のマップへの変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8e054-106">You can add an inbound map, remove a map, or change an existing map to a different one.</span></span> <span data-ttu-id="8e054-107">送信ポートには複数のマップを追加できます。ただし、各マップには一意の送信元スキーマが必要となります。</span><span class="sxs-lookup"><span data-stu-id="8e054-107">You can add more than one map to a send port, but each map must have a unique source schema.</span></span> <span data-ttu-id="8e054-108">マップの背景については、次を参照してください。[マップ](../core/maps.md)します。</span><span class="sxs-lookup"><span data-stu-id="8e054-108">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e054-109">アプリケーション開発者が開発プロセス中にマップを構成するには、このトピックの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8e054-109">The application developer can configure maps during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8e054-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="8e054-110">Prerequisites</span></span>  
 <span data-ttu-id="8e054-111">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e054-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="8e054-112">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="8e054-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-inbound-maps-for-a-send-port"></a><span data-ttu-id="8e054-113">送信ポートの受信マップを構成するには</span><span class="sxs-lookup"><span data-stu-id="8e054-113">To configure inbound maps for a send port</span></span>  
  
1. <span data-ttu-id="8e054-114">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="8e054-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="8e054-115">コンソール ツリーで、BizTalk グループを展開し、送信ポートの受信マップを構成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="8e054-115">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure an inbound map for a send port.</span></span>  
  
3. <span data-ttu-id="8e054-116">展開**送信ポート**は、送信ポートを右クリックし、[**プロパティ**、] をクリックし、**受信マップ**します。</span><span class="sxs-lookup"><span data-stu-id="8e054-116">Expand **Send Ports**, right-click the send port, click **Properties**, and then click **Inbound Maps**.</span></span>  
  
4. <span data-ttu-id="8e054-117">次の表で説明されているように、受信マップを構成し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="8e054-117">Configure the inbound maps as described in the following table, and then click **OK**.</span></span> <span data-ttu-id="8e054-118">複数のマップを追加または削除する場合は、この手順を必要に応じて繰り返します。</span><span class="sxs-lookup"><span data-stu-id="8e054-118">Repeat as needed to add or remove multiple maps.</span></span>  
  
   |<span data-ttu-id="8e054-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8e054-119">Use this</span></span>|<span data-ttu-id="8e054-120">目的</span><span class="sxs-lookup"><span data-stu-id="8e054-120">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="8e054-121">**[削除]**</span><span class="sxs-lookup"><span data-stu-id="8e054-121">**Remove**</span></span>|<span data-ttu-id="8e054-122">選択したマップを削除する場合にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e054-122">Click to remove the selected map.</span></span>|  
   |<span data-ttu-id="8e054-123">**ソース ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="8e054-123">**Source Document**</span></span>|<span data-ttu-id="8e054-124">ドロップダウン リストから、受信マップの送信元ドキュメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="8e054-124">From the drop-down list, select the source document for the inbound map.</span></span>|  
   |<span data-ttu-id="8e054-125">**マップ**</span><span class="sxs-lookup"><span data-stu-id="8e054-125">**Map**</span></span>|<span data-ttu-id="8e054-126">ドロップダウン リストから、送信元ドキュメントと送信先ドキュメントに関連付けられているマップを選択します。</span><span class="sxs-lookup"><span data-stu-id="8e054-126">From the drop-down list, select the map to associate with the source and target documents.</span></span>|  
   |<span data-ttu-id="8e054-127">**送信先ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="8e054-127">**Target Document**</span></span>|<span data-ttu-id="8e054-128">ドロップダウン リストから、受信マップの送信先ドキュメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="8e054-128">From the drop-down list, select the target document for the inbound map.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e054-129">参照</span><span class="sxs-lookup"><span data-stu-id="8e054-129">See Also</span></span>  
 <span data-ttu-id="8e054-130">[作成と送信ポートの構成](../core/creating-and-configuring-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="8e054-130">[Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md) </span></span>  
 [<span data-ttu-id="8e054-131">マップの管理</span><span class="sxs-lookup"><span data-stu-id="8e054-131">Managing Maps</span></span>](../core/managing-maps.md)