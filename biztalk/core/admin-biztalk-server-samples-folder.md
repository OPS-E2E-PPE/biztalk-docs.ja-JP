---
title: Admin (BizTalk Server Samples フォルダー) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SDK examples
- examples, administering
- administering, examples
ms.assetid: 178d0ee2-d437-4945-a35d-1a8be524aff1
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b2075ffdf3a9e7750717cef34c222e0f871eb2c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018752"
---
# <a name="admin-biztalk-server-samples-folder"></a><span data-ttu-id="ff68c-102">Admin (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="ff68c-102">Admin (BizTalk Server Samples Folder)</span></span>
<span data-ttu-id="ff68c-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のソフトウェア開発キット (SDK) には、管理のサンプルがいくつか付属しています。</span><span class="sxs-lookup"><span data-stu-id="ff68c-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes several administration samples in its software development kit (SDK).</span></span> <span data-ttu-id="ff68c-104">このセクションでは、各管理サンプルが示す機能、サンプルをビルドおよび実行する方法、および予測できる実行結果について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-104">This section provides detailed information about the functionality demonstrated by each administration sample, instructions for building and running the sample, and the results you can expect.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="ff68c-105">展開スクリプトは、展開後に不要になった場合は、削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff68c-105">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="ff68c-106">保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff68c-106">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ff68c-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ff68c-107">In This Section</span></span>  
  
- <span data-ttu-id="ff68c-108">[Admin-explorerom (BizTalk Server Samples フォルダー)](../core/admin-explorerom-biztalk-server-samples-folder.md)します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-108">[Admin-ExplorerOM (BizTalk Server Samples Folder)](../core/admin-explorerom-biztalk-server-samples-folder.md).</span></span>  
  
  - <span data-ttu-id="ff68c-109">[ApplicationManager (BizTalk Server サンプル)](../core/applicationmanager-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-109">[ApplicationManager (BizTalk Server Sample)](../core/applicationmanager-biztalk-server-sample.md).</span></span> <span data-ttu-id="ff68c-110">開始または BizTalk アプリケーションを停止する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-110">Demonstrates how to start or stop a BizTalk application.</span></span>  
  
  - <span data-ttu-id="ff68c-111">[BrowsingArtifacts (BizTalk Server サンプル)](../core/browsingartifacts-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-111">[BrowsingArtifacts (BizTalk Server Sample)](../core/browsingartifacts-biztalk-server-sample.md).</span></span> <span data-ttu-id="ff68c-112">BizTalk アイテムと属性を列挙する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-112">Demonstrates how to enumerate BizTalk artifacts and attributes.</span></span>  
  
  - <span data-ttu-id="ff68c-113">[CBR (BizTalk Server サンプル)](../core/cbr-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-113">[CBR (BizTalk Server Sample)](../core/cbr-biztalk-server-sample.md).</span></span> <span data-ttu-id="ff68c-114">追加して、BizTalk メッセージのコンテンツ ベース ルーティング用の新しい送信ポートの構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-114">Demonstrates adding and configuring new send ports for content based routing of BizTalk messages.</span></span>  
  
  - <span data-ttu-id="ff68c-115">[DeleteParty (BizTalk Server サンプル)](../core/deleteparty-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-115">[DeleteParty (BizTalk Server Sample)](../core/deleteparty-biztalk-server-sample.md).</span></span> <span data-ttu-id="ff68c-116">指定したパーティを削除する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-116">Demonstrates how to delete a specified party.</span></span>  
  
  - <span data-ttu-id="ff68c-117">[OrchestrationBinding (BizTalk Server サンプル)](../core/orchestrationbinding-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-117">[OrchestrationBinding (BizTalk Server Sample)](../core/orchestrationbinding-biztalk-server-sample.md).</span></span> <span data-ttu-id="ff68c-118">管理およびオーケストレーションを構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-118">Demonstrates how to manage and configure orchestrations.</span></span>  
  
  - <span data-ttu-id="ff68c-119">[PartnerManagement (BizTalk Server サンプル)](../core/partnermanagement-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-119">[PartnerManagement (BizTalk Server Sample)](../core/partnermanagement-biztalk-server-sample.md).</span></span> <span data-ttu-id="ff68c-120">作成とパーティの削除について説明します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-120">Demonstrates creating and deleting parties.</span></span> <span data-ttu-id="ff68c-121">ロールに対するパーティの参加および参加の解除も示します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-121">Also demonstrates enlisting and unenlisting parties with roles.</span></span>  
  
  - <span data-ttu-id="ff68c-122">[ReceiveLocations (BizTalk Server サンプル)](../core/receivelocations-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-122">[ReceiveLocations (BizTalk Server Sample)](../core/receivelocations-biztalk-server-sample.md).</span></span> <span data-ttu-id="ff68c-123">作成および管理する方法を示します 受信ポートの受信場所。</span><span class="sxs-lookup"><span data-stu-id="ff68c-123">Demonstrates how to create and manage receive locations for receive ports.</span></span>  
  
  - <span data-ttu-id="ff68c-124">[ReceivePorts (BizTalk Server サンプル)](../core/receiveports-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-124">[ReceivePorts (BizTalk Server Sample)](../core/receiveports-biztalk-server-sample.md).</span></span> <span data-ttu-id="ff68c-125">受信ポートの作成、列挙、および削除について説明します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-125">Demonstrates creating, enumerating and deleting receive ports.</span></span>  
  
  - <span data-ttu-id="ff68c-126">[SendPortGroups (BizTalk Server サンプル)](../core/sendportgroups-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-126">[SendPortGroups (BizTalk Server Sample)](../core/sendportgroups-biztalk-server-sample.md).</span></span> <span data-ttu-id="ff68c-127">列挙および送信ポート グループを管理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-127">Demonstrates how to enumerate and manage send port groups.</span></span>  
  
  - <span data-ttu-id="ff68c-128">[SendPorts (BizTalk Server サンプル)](../core/sendports-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-128">[SendPorts (BizTalk Server Sample)](../core/sendports-biztalk-server-sample.md).</span></span> <span data-ttu-id="ff68c-129">列挙および送信ポートを管理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-129">Demonstrates how to enumerate and manage send ports.</span></span>  
  
  - <span data-ttu-id="ff68c-130">[UnenlistParties (BizTalk Server サンプル)](../core/unenlistparties-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-130">[UnenlistParties (BizTalk Server Sample)](../core/unenlistparties-biztalk-server-sample.md).</span></span> <span data-ttu-id="ff68c-131">展開された BizTalk アセンブリに関連付けられたすべてのパーティの参加を解除する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-131">Demonstrates how to unenlist all of the parties associated with a deployed BizTalk assembly.</span></span>  
  
  - <span data-ttu-id="ff68c-132">[Sysprep による BizTalk Server VHD (BizTalk Server サンプル)](../core/sysprep-a-biztalk-server-vhd-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-132">[Sysprep a BizTalk Server VHD (BizTalk Server Sample)](../core/sysprep-a-biztalk-server-vhd-biztalk-server-sample.md).</span></span> <span data-ttu-id="ff68c-133">Sysprep が使用して仮想マシンのスナップショットを作成する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]他の仮想マシンに簡単に展開をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ff68c-133">Demonstrates how Sysprep creates a snapshot of a virtual machine with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installed for quick deployment on other virtual machines.</span></span>  
  
- [<span data-ttu-id="ff68c-134">Admin-OperationsOM (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="ff68c-134">Admin-OperationsOM (BizTalk Server Samples Folder)</span></span>](../core/admin-operationsom-biztalk-server-samples-folder.md)  
  
  -   [<span data-ttu-id="ff68c-135">OperationsSamples (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="ff68c-135">OperationsSamples (BizTalk Server Sample)</span></span>](../core/operationssamples-biztalk-server-sample.md)  
  
- [<span data-ttu-id="ff68c-136">Admin-WMI (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="ff68c-136">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)  
  
  -   <span data-ttu-id="ff68c-137">[受信場所 (BizTalk Server サンプル) を有効にする](../core/enable-receive-location-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-137">[Enable Receive Location (BizTalk Server Sample)](../core/enable-receive-location-biztalk-server-sample.md).</span></span> <span data-ttu-id="ff68c-138">受信場所を有効にし、その受信場所の受信トランスポート URL を設定する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-138">Demonstrates how to enable a receive location and set the Inbound Transport URL for that receive location.</span></span>  
  
  -   <span data-ttu-id="ff68c-139">[オーケストレーション (BizTalk Server サンプル) を参加させる](../core/enlist-orchestration-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-139">[Enlist Orchestration (BizTalk Server Sample)](../core/enlist-orchestration-biztalk-server-sample.md).</span></span> <span data-ttu-id="ff68c-140">BizTalk Server オーケストレーションをホストに参加させる方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-140">Demonstrates how to enlist a BizTalk Server orchestration to a host.</span></span>  
  
  -   <span data-ttu-id="ff68c-141">[列挙の受信場所 (BizTalk Server サンプル)](../core/enumerate-receive-locations-biztalk-server-sample.md)サンプル。</span><span class="sxs-lookup"><span data-stu-id="ff68c-141">[Enumerate Receive Locations (BizTalk Server Sample)](../core/enumerate-receive-locations-biztalk-server-sample.md) Sample.</span></span> <span data-ttu-id="ff68c-142">1 つ以上の受信場所に関する詳細情報を取得する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-142">Demonstrates how to retrieve details about one or more receive locations.</span></span>  
  
  -   <span data-ttu-id="ff68c-143">[受信ポート (BizTalk Server サンプル) の削除](../core/remove-receive-port-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-143">[Remove Receive Port (BizTalk Server Sample)](../core/remove-receive-port-biztalk-server-sample.md).</span></span> <span data-ttu-id="ff68c-144">1 つ以上の受信ポートを削除する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-144">Demonstrates how to remove one or more receive ports.</span></span>  
  
  -   <span data-ttu-id="ff68c-145">[送信ポートの削除 (BizTalk Server サンプル)](../core/remove-send-port-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-145">[Remove Send Port (BizTalk Server Sample)](../core/remove-send-port-biztalk-server-sample.md).</span></span> <span data-ttu-id="ff68c-146">1 つ以上の送信ポートの参加を解除し、削除する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-146">Demonstrates how to unenlist and remove one or more send ports.</span></span>  
  
  -   <span data-ttu-id="ff68c-147">[送信ハンドラー プロパティ (BizTalk Server サンプル) の設定](../core/set-send-handler-property-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-147">[Set Send Handler Property (BizTalk Server Sample)](../core/set-send-handler-property-biztalk-server-sample.md).</span></span> <span data-ttu-id="ff68c-148">簡易メール送信プロトコル (SMTP) 送信ハンドラの XML 構成情報を設定する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-148">Demonstrates how to set the XML configuration information for a Simple Mail Transfer Protocol (SMTP) send handler.</span></span>  
  
  -   <span data-ttu-id="ff68c-149">[送信ポートの開始 (BizTalk Server サンプル)](../core/start-send-port-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-149">[Start Send Port (BizTalk Server Sample)](../core/start-send-port-biztalk-server-sample.md).</span></span> <span data-ttu-id="ff68c-150">ファイル アダプタの使用時に、送信ポートを起動し、プライマリ トランスポートのアドレスを設定する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-150">Demonstrates how to start a send port and set the Primary Transport Address when using the FILE adapter.</span></span>  
  
  -   <span data-ttu-id="ff68c-151">[オーケストレーションの停止 (BizTalk Server サンプル)](../core/stop-orchestration-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-151">[Stop Orchestration (BizTalk Server Sample)](../core/stop-orchestration-biztalk-server-sample.md).</span></span> <span data-ttu-id="ff68c-152">BizTalk Server オーケストレーションを停止する方法、およびオプションとして BizTalk Server オーケストレーションの参加を解除する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="ff68c-152">Demonstrates how to stop a BizTalk Server orchestration and, optionally, to unenlist it.</span></span>