---
title: "管理 WMI (BizTalk Server Samples フォルダ) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- administering, WMI
- examples, Windows Management Instrumentation (WMI)
- Windows Management Instrumentation (WMI), administering
- Windows Management Instrumentation (WMI), examples
- examples, administering
- administering, examples
ms.assetid: 39e2a6fe-2781-4be2-a152-f5e9960a0faa
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19a8698bbe916d86909005ff77c9b1eeea11604f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="admin-wmi-biztalk-server-samples-folder"></a><span data-ttu-id="95537-102">管理 WMI (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="95537-102">Admin-WMI (BizTalk Server Samples Folder)</span></span>
<span data-ttu-id="95537-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のソフトウェア開発キット (SDK) には、Microsoft Windows Management Instrumentation (WMI) 管理のサンプルがいくつか付属しています。</span><span class="sxs-lookup"><span data-stu-id="95537-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes several Microsoft Windows Management Instrumentation (WMI) administration samples in its software development kit (SDK).</span></span> <span data-ttu-id="95537-104">このセクションでは、各 WMI 管理サンプルが示す機能、サンプルをビルドおよび実行する方法、および予測できる実行結果について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="95537-104">This section provides detailed information about the functionality demonstrated by each WMI administration sample, instructions for building and running the sample, and the results you can expect.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="95537-105">展開スクリプトは、展開後に不要になった場合は、削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95537-105">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="95537-106">保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95537-106">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="95537-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="95537-107">In This Section</span></span>  
  
-   <span data-ttu-id="95537-108">[有効にする受信場所 (BizTalk Server サンプル)](../core/enable-receive-location-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="95537-108">[Enable Receive Location (BizTalk Server Sample)](../core/enable-receive-location-biztalk-server-sample.md).</span></span> <span data-ttu-id="95537-109">受信場所を有効にし、その受信場所の受信トランスポート URL を設定する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="95537-109">Demonstrates how to enable a receive location and set the Inbound Transport URL for that receive location.</span></span>  
  
-   <span data-ttu-id="95537-110">[オーケストレーション (BizTalk Server サンプル) を参加させる](../core/enlist-orchestration-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="95537-110">[Enlist Orchestration (BizTalk Server Sample)](../core/enlist-orchestration-biztalk-server-sample.md).</span></span> <span data-ttu-id="95537-111">BizTalk Server オーケストレーションをホストに参加させる方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="95537-111">Demonstrates how to enlist a BizTalk Server orchestration to a host.</span></span>  
  
-   <span data-ttu-id="95537-112">[列挙の受信場所 (BizTalk Server サンプル)](../core/enumerate-receive-locations-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="95537-112">[Enumerate Receive Locations (BizTalk Server Sample)](../core/enumerate-receive-locations-biztalk-server-sample.md).</span></span> <span data-ttu-id="95537-113">1 つ以上の受信場所に関する詳細情報を取得する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="95537-113">Demonstrates how to retrieve details about one or more receive locations.</span></span>  
  
-   <span data-ttu-id="95537-114">[受信ポート (BizTalk Server サンプル) の削除](../core/remove-receive-port-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="95537-114">[Remove Receive Port (BizTalk Server Sample)](../core/remove-receive-port-biztalk-server-sample.md).</span></span> <span data-ttu-id="95537-115">1 つ以上の受信ポートを削除する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="95537-115">Demonstrates how to remove one or more receive ports.</span></span>  
  
-   <span data-ttu-id="95537-116">[送信ポートの削除 (BizTalk Server サンプル)](../core/remove-send-port-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="95537-116">[Remove Send Port (BizTalk Server Sample)](../core/remove-send-port-biztalk-server-sample.md).</span></span> <span data-ttu-id="95537-117">1 つ以上の送信ポートの参加を解除し、削除する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="95537-117">Demonstrates how to unenlist and remove one or more send ports.</span></span>  
  
-   <span data-ttu-id="95537-118">[送信ハンドラー プロパティ (BizTalk Server サンプル) を設定する](../core/set-send-handler-property-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="95537-118">[Set Send Handler Property (BizTalk Server Sample)](../core/set-send-handler-property-biztalk-server-sample.md).</span></span> <span data-ttu-id="95537-119">簡易メール送信プロトコル (SMTP) 送信ハンドラの XML 構成情報を設定する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="95537-119">Demonstrates how to set the XML configuration information for a Simple Mail Transfer Protocol (SMTP) send handler.</span></span>  
  
-   <span data-ttu-id="95537-120">[送信ポートの開始 (BizTalk Server サンプル)](../core/start-send-port-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="95537-120">[Start Send Port (BizTalk Server Sample)](../core/start-send-port-biztalk-server-sample.md).</span></span> <span data-ttu-id="95537-121">ファイル アダプタの使用時に、送信ポートを起動し、プライマリ トランスポートのアドレスを設定する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="95537-121">Demonstrates how to start a send port and set the Primary Transport Address when using the FILE adapter.</span></span>  
  
-   <span data-ttu-id="95537-122">[オーケストレーション (BizTalk Server サンプル) を停止](../core/stop-orchestration-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="95537-122">[Stop Orchestration (BizTalk Server Sample)](../core/stop-orchestration-biztalk-server-sample.md).</span></span> <span data-ttu-id="95537-123">BizTalk Server オーケストレーションを停止する方法、およびオプションとして BizTalk Server オーケストレーションの参加を解除する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="95537-123">Demonstrates how to stop a BizTalk Server orchestration and, optionally, to unenlist it.</span></span>