---
title: 送信ポートの送信マップを構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 51d3feaba929d1a7585a8e7c3b29f6868dcc9dc7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248090"
---
# <a name="how-to-configure-outbound-maps-for-a-send-port"></a><span data-ttu-id="583a8-102">送信ポートの送信マップを構成する方法</span><span class="sxs-lookup"><span data-stu-id="583a8-102">How to Configure Outbound Maps for a Send Port</span></span>
<span data-ttu-id="583a8-103">ここでは、BizTalk Server 管理コンソールを使って、送信ポートの送信マップを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="583a8-103">This topic describes how to configure outbound maps for a send port by using the BizTalk Server Administration console.</span></span> <span data-ttu-id="583a8-104">マップを使用すると、オーケストレーションでメッセージを処理することなく、送信ポートによって送信されたメッセージに XSL 変換を適用できます。</span><span class="sxs-lookup"><span data-stu-id="583a8-104">You use a map to apply an XSL transformation to a message sent by the send port without processing the message through an orchestration.</span></span> <span data-ttu-id="583a8-105">出力マップの追加、マップの削除、既存のマップから別のマップへの変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="583a8-105">You can add an outbound map, remove a map, or change an existing map to a different one.</span></span> <span data-ttu-id="583a8-106">送信ポートには複数のマップを追加できます。ただし、各マップには一意の送信元スキーマが必要となります。</span><span class="sxs-lookup"><span data-stu-id="583a8-106">You can add more than one map to a send port, but each map must have a unique source schema.</span></span> <span data-ttu-id="583a8-107">マップに関する背景情報については、次を参照してください。[マップ](../core/maps.md)です。</span><span class="sxs-lookup"><span data-stu-id="583a8-107">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="583a8-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="583a8-108">Prerequisites</span></span>  
 <span data-ttu-id="583a8-109">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="583a8-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="583a8-110">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="583a8-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-outbound-maps-for-a-send-port"></a><span data-ttu-id="583a8-111">送信ポートに対して送信マップを構成するには</span><span class="sxs-lookup"><span data-stu-id="583a8-111">To configure outbound maps for a send port</span></span>  
  
1.  <span data-ttu-id="583a8-112">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="583a8-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="583a8-113">コンソール ツリーで、BizTalk グループを展開し、送信ポートの送信マップを構成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="583a8-113">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure the outbound maps for a send port.</span></span>  
  
3.  <span data-ttu-id="583a8-114">展開**送信ポート**、送信ポートを右クリックし、をクリックして**プロパティ**、クリックして**送信マップ**です。</span><span class="sxs-lookup"><span data-stu-id="583a8-114">Expand **Send Ports**, right-click the send port, click **Properties**, and then click **Outbound Maps**.</span></span>  
  
4.  <span data-ttu-id="583a8-115">次の表の説明に従って、送信マップを構成し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="583a8-115">Configure outbound maps as described in the following table, and then click **OK**.</span></span> <span data-ttu-id="583a8-116">複数のマップを追加または削除する場合は、この手順を必要に応じて繰り返します。</span><span class="sxs-lookup"><span data-stu-id="583a8-116">Repeat as needed to add or remove multiple maps.</span></span>  
  
    |<span data-ttu-id="583a8-117">プロパティ</span><span class="sxs-lookup"><span data-stu-id="583a8-117">Use this</span></span>|<span data-ttu-id="583a8-118">目的</span><span class="sxs-lookup"><span data-stu-id="583a8-118">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="583a8-119">**[削除]**</span><span class="sxs-lookup"><span data-stu-id="583a8-119">**Remove**</span></span>|<span data-ttu-id="583a8-120">選択したマップを削除する場合にクリックします。</span><span class="sxs-lookup"><span data-stu-id="583a8-120">Click to remove the selected map.</span></span>|  
    |<span data-ttu-id="583a8-121">**送信マップ-ソース ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="583a8-121">**Outbound maps - Source Document**</span></span>|<span data-ttu-id="583a8-122">ドロップダウン リストから、送信マップの送信元ドキュメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="583a8-122">From the drop-down list, select the source document for the outbound map.</span></span>|  
    |<span data-ttu-id="583a8-123">**送信マップ-マップ**</span><span class="sxs-lookup"><span data-stu-id="583a8-123">**Outbound maps - Map**</span></span>|<span data-ttu-id="583a8-124">ドロップダウン リストから、送信元ドキュメントと送信先ドキュメントに関連付けられているマップを選択します。</span><span class="sxs-lookup"><span data-stu-id="583a8-124">From the drop-down list, select the map to associate with the source and target documents.</span></span>|  
    |<span data-ttu-id="583a8-125">**送信マップ-送信先ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="583a8-125">**Outbound maps - Target Document**</span></span>|<span data-ttu-id="583a8-126">ドロップダウン リストから、送信マップの送信先ドキュメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="583a8-126">From the drop-down list, select the target document for the outbound map.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="583a8-127">参照</span><span class="sxs-lookup"><span data-stu-id="583a8-127">See Also</span></span>  
 <span data-ttu-id="583a8-128">[作成して、送信ポートの構成](../core/creating-and-configuring-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="583a8-128">[Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md) </span></span>  
 [<span data-ttu-id="583a8-129">マップを管理します。</span><span class="sxs-lookup"><span data-stu-id="583a8-129">Managing Maps</span></span>](../core/managing-maps.md)