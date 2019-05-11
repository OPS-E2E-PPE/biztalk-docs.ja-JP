---
title: 送信ポートの送信マップを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, outbound maps
- configuring, send ports
- managing [send ports], configuring
- send ports, outbound maps
- send ports, configuring
- managing [send ports], outbound maps
ms.assetid: 9f5f5504-5a7f-4b21-9a65-91dce9d35890
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7140797eba38ee2eebe22ad01d04fdf4acee83ee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386228"
---
# <a name="how-to-configure-outbound-maps-for-a-send-port"></a><span data-ttu-id="189e6-102">送信ポートの送信マップを構成する方法</span><span class="sxs-lookup"><span data-stu-id="189e6-102">How to Configure Outbound Maps for a Send Port</span></span>
<span data-ttu-id="189e6-103">ここでは、BizTalk Server 管理コンソールを使って、送信ポートの送信マップを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="189e6-103">This topic describes how to configure outbound maps for a send port by using the BizTalk Server Administration console.</span></span> <span data-ttu-id="189e6-104">マップを使用すると、オーケストレーションでメッセージを処理することなく、送信ポートによって送信されたメッセージに XSL 変換を適用できます。</span><span class="sxs-lookup"><span data-stu-id="189e6-104">You use a map to apply an XSL transformation to a message sent by the send port without processing the message through an orchestration.</span></span> <span data-ttu-id="189e6-105">出力マップの追加、マップの削除、既存のマップから別のマップへの変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="189e6-105">You can add an outbound map, remove a map, or change an existing map to a different one.</span></span> <span data-ttu-id="189e6-106">送信ポートには複数のマップを追加できます。ただし、各マップには一意の送信元スキーマが必要となります。</span><span class="sxs-lookup"><span data-stu-id="189e6-106">You can add more than one map to a send port, but each map must have a unique source schema.</span></span> <span data-ttu-id="189e6-107">マップの背景については、次を参照してください。[マップ](../core/maps.md)します。</span><span class="sxs-lookup"><span data-stu-id="189e6-107">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="189e6-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="189e6-108">Prerequisites</span></span>  
 <span data-ttu-id="189e6-109">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="189e6-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="189e6-110">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="189e6-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-outbound-maps-for-a-send-port"></a><span data-ttu-id="189e6-111">送信ポートに対して送信マップを構成するには</span><span class="sxs-lookup"><span data-stu-id="189e6-111">To configure outbound maps for a send port</span></span>  
  
1. <span data-ttu-id="189e6-112">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="189e6-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="189e6-113">コンソール ツリーで、BizTalk グループを展開し、送信ポートの送信マップを構成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="189e6-113">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure the outbound maps for a send port.</span></span>  
  
3. <span data-ttu-id="189e6-114">展開**送信ポート**は、送信ポートを右クリックし、[**プロパティ**、] をクリックし、**送信マップ**します。</span><span class="sxs-lookup"><span data-stu-id="189e6-114">Expand **Send Ports**, right-click the send port, click **Properties**, and then click **Outbound Maps**.</span></span>  
  
4. <span data-ttu-id="189e6-115">次の表に示すように、送信マップを構成し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="189e6-115">Configure outbound maps as described in the following table, and then click **OK**.</span></span> <span data-ttu-id="189e6-116">複数のマップを追加または削除する場合は、この手順を必要に応じて繰り返します。</span><span class="sxs-lookup"><span data-stu-id="189e6-116">Repeat as needed to add or remove multiple maps.</span></span>  
  
   |<span data-ttu-id="189e6-117">プロパティ</span><span class="sxs-lookup"><span data-stu-id="189e6-117">Use this</span></span>|<span data-ttu-id="189e6-118">目的</span><span class="sxs-lookup"><span data-stu-id="189e6-118">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="189e6-119">**[削除]**</span><span class="sxs-lookup"><span data-stu-id="189e6-119">**Remove**</span></span>|<span data-ttu-id="189e6-120">選択したマップを削除する場合にクリックします。</span><span class="sxs-lookup"><span data-stu-id="189e6-120">Click to remove the selected map.</span></span>|  
   |<span data-ttu-id="189e6-121">**送信マップ-ソース ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="189e6-121">**Outbound maps - Source Document**</span></span>|<span data-ttu-id="189e6-122">ドロップダウン リストから、送信マップの送信元ドキュメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="189e6-122">From the drop-down list, select the source document for the outbound map.</span></span>|  
   |<span data-ttu-id="189e6-123">**送信マップ-マップ**</span><span class="sxs-lookup"><span data-stu-id="189e6-123">**Outbound maps - Map**</span></span>|<span data-ttu-id="189e6-124">ドロップダウン リストから、送信元ドキュメントと送信先ドキュメントに関連付けられているマップを選択します。</span><span class="sxs-lookup"><span data-stu-id="189e6-124">From the drop-down list, select the map to associate with the source and target documents.</span></span>|  
   |<span data-ttu-id="189e6-125">**送信マップ]-[送信先ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="189e6-125">**Outbound maps - Target Document**</span></span>|<span data-ttu-id="189e6-126">ドロップダウン リストから、送信マップの送信先ドキュメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="189e6-126">From the drop-down list, select the target document for the outbound map.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="189e6-127">参照</span><span class="sxs-lookup"><span data-stu-id="189e6-127">See Also</span></span>  
 <span data-ttu-id="189e6-128">[作成と送信ポートの構成](../core/creating-and-configuring-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="189e6-128">[Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md) </span></span>  
 [<span data-ttu-id="189e6-129">マップの管理</span><span class="sxs-lookup"><span data-stu-id="189e6-129">Managing Maps</span></span>](../core/managing-maps.md)