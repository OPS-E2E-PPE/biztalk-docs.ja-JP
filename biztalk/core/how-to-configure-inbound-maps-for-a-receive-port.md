---
title: "受信マップを構成する方法、受信ポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5275b2701d42240df06810ef43563ca4a200151f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-inbound-maps-for-a-receive-port"></a><span data-ttu-id="5ba37-102">受信ポートの受信マップを構成する方法</span><span class="sxs-lookup"><span data-stu-id="5ba37-102">How to Configure Inbound Maps for a Receive Port</span></span>
<span data-ttu-id="5ba37-103">このトピックでは、BizTalk Server 管理コンソールを使用して、受信ポートの受信マップを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5ba37-103">This topic describes how to use the BizTalk Server Administration console to configure inbound maps for a receive port.</span></span> <span data-ttu-id="5ba37-104">受信マップを使用すると、受信メッセージのスキーマを別のスキーマに変換できます。たとえば、パートナーから受信したメッセージを、自社で使用されているスキーマに変換することが可能となります。</span><span class="sxs-lookup"><span data-stu-id="5ba37-104">You use inbound maps to transform inbound messages from one schema to another; for example to transform messages received from a partner into a schema that your company uses.</span></span>  
  
 <span data-ttu-id="5ba37-105">マップを使用すると、オーケストレーションでメッセージを処理することなく、受信ポートによって送信されたメッセージに XSL 変換を適用できます。</span><span class="sxs-lookup"><span data-stu-id="5ba37-105">You use a map to apply an XSL transformation to a message sent by the receive port without processing the message through an orchestration.</span></span> <span data-ttu-id="5ba37-106">受信マップの追加、マップの削除、既存のマップから別のマップへの変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5ba37-106">You can add an inbound map, remove a map, or change an existing map to a different one.</span></span> <span data-ttu-id="5ba37-107">受信ポートに複数のマップを追加することができますが、各マップには、一意の送信元スキーマが必要です。</span><span class="sxs-lookup"><span data-stu-id="5ba37-107">You can add more than one map to a receive port, but each map must have a unique source schema.</span></span> <span data-ttu-id="5ba37-108">マップに関する背景情報については、次を参照してください。[マップ](../core/maps.md)です。</span><span class="sxs-lookup"><span data-stu-id="5ba37-108">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ba37-109">アプリケーション開発者が開発プロセス中に受信ポート用のマップを構成するには、このトピックの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5ba37-109">The application developer can configure maps for a receive port during the development process by using the procedure in this.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5ba37-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="5ba37-110">Prerequisites</span></span>  
 <span data-ttu-id="5ba37-111">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ba37-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="5ba37-112">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="5ba37-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-inbound-maps-for-a-receive-port"></a><span data-ttu-id="5ba37-113">受信ポートの受信マップを構成するには</span><span class="sxs-lookup"><span data-stu-id="5ba37-113">To configure inbound maps for a receive port</span></span>  
  
1.  <span data-ttu-id="5ba37-114">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="5ba37-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="5ba37-115">コンソール ツリーで、BizTalk グループを展開し、受信ポートの受信マップを構成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="5ba37-115">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure an inbound maps for a receive port.</span></span>  
  
3.  <span data-ttu-id="5ba37-116">をクリックして**受信ポート**受信ポートを右クリックしをクリックして**プロパティ**、順にクリック**受信マップ**です。</span><span class="sxs-lookup"><span data-stu-id="5ba37-116">Click **Receive Ports**, right-click the receive port, click **Properties**, and then click **Inbound Maps**.</span></span>  
  
4.  <span data-ttu-id="5ba37-117">次の表に示すように、受信マップを構成し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="5ba37-117">Configure the inbound maps as described in the following table, and then click **OK**.</span></span>  
  
    |<span data-ttu-id="5ba37-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5ba37-118">Use this</span></span>|<span data-ttu-id="5ba37-119">目的</span><span class="sxs-lookup"><span data-stu-id="5ba37-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="5ba37-120">**[削除]**</span><span class="sxs-lookup"><span data-stu-id="5ba37-120">**Remove**</span></span>|<span data-ttu-id="5ba37-121">選択したマップを削除する場合にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba37-121">Click to remove the selected map.</span></span>|  
    |<span data-ttu-id="5ba37-122">**ソース ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="5ba37-122">**Source Document**</span></span>|<span data-ttu-id="5ba37-123">ドロップダウン リストから、このポートで使用する送信元スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="5ba37-123">From the drop-down list, select the source schema to use with this port.</span></span>|  
    |<span data-ttu-id="5ba37-124">**マップ**</span><span class="sxs-lookup"><span data-stu-id="5ba37-124">**Map**</span></span>|<span data-ttu-id="5ba37-125">ドロップダウン リストから、このポートに関連付けるマップを選択します。</span><span class="sxs-lookup"><span data-stu-id="5ba37-125">From the drop-down list, select the map you want to associate with this port.</span></span>|  
    |<span data-ttu-id="5ba37-126">**対象のドキュメント**</span><span class="sxs-lookup"><span data-stu-id="5ba37-126">**Target Document**</span></span>|<span data-ttu-id="5ba37-127">ドロップダウン リストから、このポートで使用する送信先スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="5ba37-127">From the drop-down list, select the destination schema to use with this port.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ba37-128">参照</span><span class="sxs-lookup"><span data-stu-id="5ba37-128">See Also</span></span>  
 <span data-ttu-id="5ba37-129">[受信ポートの管理](../core/managing-receive-ports.md) </span><span class="sxs-lookup"><span data-stu-id="5ba37-129">[Managing Receive Ports](../core/managing-receive-ports.md) </span></span>  
 [<span data-ttu-id="5ba37-130">マップを管理します。</span><span class="sxs-lookup"><span data-stu-id="5ba37-130">Managing Maps</span></span>](../core/managing-maps.md)