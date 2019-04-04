---
title: 受信マップを構成する方法、受信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- configuring, maps
- configuring, inbound maps
- maps, configuring
- receive ports, configuring
- receive ports, inbound maps
- configuring, receive ports
- maps, inbound
- managing [receive ports], inbound maps
ms.assetid: b7448b39-f024-4353-818b-f753c2d60751
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b840f4c418c835765345adc01da5c9c18812d3ce
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985603"
---
# <a name="how-to-configure-inbound-maps-for-a-receive-port"></a><span data-ttu-id="bfb98-102">受信ポートの受信マップを構成する方法</span><span class="sxs-lookup"><span data-stu-id="bfb98-102">How to Configure Inbound Maps for a Receive Port</span></span>
<span data-ttu-id="bfb98-103">このトピックでは、BizTalk Server 管理コンソールを使用して、受信ポートの受信マップを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bfb98-103">This topic describes how to use the BizTalk Server Administration console to configure inbound maps for a receive port.</span></span> <span data-ttu-id="bfb98-104">受信マップを使用すると、受信メッセージのスキーマを別のスキーマに変換できます。たとえば、パートナーから受信したメッセージを、自社で使用されているスキーマに変換することが可能となります。</span><span class="sxs-lookup"><span data-stu-id="bfb98-104">You use inbound maps to transform inbound messages from one schema to another; for example to transform messages received from a partner into a schema that your company uses.</span></span>  
  
 <span data-ttu-id="bfb98-105">マップを使用すると、オーケストレーションでメッセージを処理することなく、受信ポートによって送信されたメッセージに XSL 変換を適用できます。</span><span class="sxs-lookup"><span data-stu-id="bfb98-105">You use a map to apply an XSL transformation to a message sent by the receive port without processing the message through an orchestration.</span></span> <span data-ttu-id="bfb98-106">受信マップの追加、マップの削除、既存のマップから別のマップへの変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bfb98-106">You can add an inbound map, remove a map, or change an existing map to a different one.</span></span> <span data-ttu-id="bfb98-107">受信ポートに 1 つ以上のマップを追加することができますが、各マップには、一意の送信元スキーマが必要です。 します。</span><span class="sxs-lookup"><span data-stu-id="bfb98-107">You can add more than one map to a receive port, but each map must have a unique source schema.</span></span> <span data-ttu-id="bfb98-108">マップの背景については、[マップ](../core/maps.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfb98-108">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bfb98-109">アプリケーション開発者が開発プロセス中に受信ポート用のマップを構成するには、このトピックの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bfb98-109">The application developer can configure maps for a receive port during the development process by using the procedure in this.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bfb98-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="bfb98-110">Prerequisites</span></span>  
 <span data-ttu-id="bfb98-111">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfb98-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="bfb98-112">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="bfb98-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-inbound-maps-for-a-receive-port"></a><span data-ttu-id="bfb98-113">受信ポートの受信マップを構成するには</span><span class="sxs-lookup"><span data-stu-id="bfb98-113">To configure inbound maps for a receive port</span></span>  
  
1. <span data-ttu-id="bfb98-114">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="bfb98-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="bfb98-115">コンソール ツリーで、BizTalk グループを展開し、受信ポートの受信マップを構成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="bfb98-115">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure an inbound maps for a receive port.</span></span>  
  
3. <span data-ttu-id="bfb98-116">クリックして**受信ポート**は、受信ポートを右クリックし、**プロパティ**、順にクリックします**受信マップ**します。</span><span class="sxs-lookup"><span data-stu-id="bfb98-116">Click **Receive Ports**, right-click the receive port, click **Properties**, and then click **Inbound Maps**.</span></span>  
  
4. <span data-ttu-id="bfb98-117">次の表で説明されているように、受信マップを構成し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="bfb98-117">Configure the inbound maps as described in the following table, and then click **OK**.</span></span>  
  
   |<span data-ttu-id="bfb98-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="bfb98-118">Use this</span></span>|<span data-ttu-id="bfb98-119">目的</span><span class="sxs-lookup"><span data-stu-id="bfb98-119">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="bfb98-120">**[削除]**</span><span class="sxs-lookup"><span data-stu-id="bfb98-120">**Remove**</span></span>|<span data-ttu-id="bfb98-121">選択したマップを削除する場合にクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfb98-121">Click to remove the selected map.</span></span>|  
   |<span data-ttu-id="bfb98-122">**ソース ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="bfb98-122">**Source Document**</span></span>|<span data-ttu-id="bfb98-123">ドロップダウン リストから、このポートで使用する送信元スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="bfb98-123">From the drop-down list, select the source schema to use with this port.</span></span>|  
   |<span data-ttu-id="bfb98-124">**マップ**</span><span class="sxs-lookup"><span data-stu-id="bfb98-124">**Map**</span></span>|<span data-ttu-id="bfb98-125">ドロップダウン リストから、このポートに関連付けるマップを選択します。</span><span class="sxs-lookup"><span data-stu-id="bfb98-125">From the drop-down list, select the map you want to associate with this port.</span></span>|  
   |<span data-ttu-id="bfb98-126">**送信先ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="bfb98-126">**Target Document**</span></span>|<span data-ttu-id="bfb98-127">ドロップダウン リストから、このポートで使用する送信先スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="bfb98-127">From the drop-down list, select the destination schema to use with this port.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bfb98-128">参照</span><span class="sxs-lookup"><span data-stu-id="bfb98-128">See Also</span></span>  
 <span data-ttu-id="bfb98-129">[受信ポートの管理](../core/managing-receive-ports.md) </span><span class="sxs-lookup"><span data-stu-id="bfb98-129">[Managing Receive Ports](../core/managing-receive-ports.md) </span></span>  
 [<span data-ttu-id="bfb98-130">マップの管理</span><span class="sxs-lookup"><span data-stu-id="bfb98-130">Managing Maps</span></span>](../core/managing-maps.md)