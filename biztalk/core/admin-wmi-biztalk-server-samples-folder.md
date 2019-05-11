---
title: ADMIN-WMI (BizTalk Server Samples フォルダー) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- administering, WMI
- examples, Windows Management Instrumentation (WMI)
- Windows Management Instrumentation (WMI), administering
- Windows Management Instrumentation (WMI), examples
- examples, administering
- administering, examples
ms.assetid: 39e2a6fe-2781-4be2-a152-f5e9960a0faa
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19d27b2f987ef9ecbd9e7c00e9d149ae26bf7a5a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360034"
---
# <a name="admin-wmi-biztalk-server-samples-folder"></a><span data-ttu-id="f07bc-102">ADMIN-WMI (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="f07bc-102">Admin-WMI (BizTalk Server Samples Folder)</span></span>
<span data-ttu-id="f07bc-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソフトウェア開発キット (SDK) のいくつかの Microsoft Windows Management Instrumentation (WMI) 管理サンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f07bc-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes several Microsoft Windows Management Instrumentation (WMI) administration samples in its software development kit (SDK).</span></span> <span data-ttu-id="f07bc-104">ここでは、各 WMI 管理サンプルを構築して、サンプルと予想される結果を実行する手順で示されている機能の詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="f07bc-104">This section provides detailed information about the functionality demonstrated by each WMI administration sample, instructions for building and running the sample, and the results you can expect.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="f07bc-105">展開スクリプトは、展開後に不要になった場合は、削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f07bc-105">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="f07bc-106">保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f07bc-106">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f07bc-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f07bc-107">In This Section</span></span>  
  
-   <span data-ttu-id="f07bc-108">[受信場所 (BizTalk Server サンプル) を有効にする](../core/enable-receive-location-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="f07bc-108">[Enable Receive Location (BizTalk Server Sample)](../core/enable-receive-location-biztalk-server-sample.md).</span></span> <span data-ttu-id="f07bc-109">受信場所を有効にし、その受信場所の受信トランスポート URL を設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f07bc-109">Demonstrates how to enable a receive location and set the Inbound Transport URL for that receive location.</span></span>  
  
-   <span data-ttu-id="f07bc-110">[オーケストレーション (BizTalk Server サンプル) を参加させる](../core/enlist-orchestration-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="f07bc-110">[Enlist Orchestration (BizTalk Server Sample)](../core/enlist-orchestration-biztalk-server-sample.md).</span></span> <span data-ttu-id="f07bc-111">ホストする BizTalk Server オーケストレーションを参加させる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f07bc-111">Demonstrates how to enlist a BizTalk Server orchestration to a host.</span></span>  
  
-   <span data-ttu-id="f07bc-112">[列挙の受信場所 (BizTalk Server サンプル)](../core/enumerate-receive-locations-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="f07bc-112">[Enumerate Receive Locations (BizTalk Server Sample)](../core/enumerate-receive-locations-biztalk-server-sample.md).</span></span> <span data-ttu-id="f07bc-113">詳細を取得する方法の 1 つまたは複数の受信場所。</span><span class="sxs-lookup"><span data-stu-id="f07bc-113">Demonstrates how to retrieve details about one or more receive locations.</span></span>  
  
-   <span data-ttu-id="f07bc-114">[受信ポート (BizTalk Server サンプル) の削除](../core/remove-receive-port-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="f07bc-114">[Remove Receive Port (BizTalk Server Sample)](../core/remove-receive-port-biztalk-server-sample.md).</span></span> <span data-ttu-id="f07bc-115">1 つを削除する方法を示します以上の受信ポート。</span><span class="sxs-lookup"><span data-stu-id="f07bc-115">Demonstrates how to remove one or more receive ports.</span></span>  
  
-   <span data-ttu-id="f07bc-116">[送信ポートの削除 (BizTalk Server サンプル)](../core/remove-send-port-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="f07bc-116">[Remove Send Port (BizTalk Server Sample)](../core/remove-send-port-biztalk-server-sample.md).</span></span> <span data-ttu-id="f07bc-117">参加を解除し、1 つまたは複数の送信ポートを削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f07bc-117">Demonstrates how to unenlist and remove one or more send ports.</span></span>  
  
-   <span data-ttu-id="f07bc-118">[送信ハンドラー プロパティ (BizTalk Server サンプル) の設定](../core/set-send-handler-property-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="f07bc-118">[Set Send Handler Property (BizTalk Server Sample)](../core/set-send-handler-property-biztalk-server-sample.md).</span></span> <span data-ttu-id="f07bc-119">簡易メール転送プロトコル (SMTP) の送信ハンドラの XML 構成情報を設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f07bc-119">Demonstrates how to set the XML configuration information for a Simple Mail Transfer Protocol (SMTP) send handler.</span></span>  
  
-   <span data-ttu-id="f07bc-120">[送信ポートの開始 (BizTalk Server サンプル)](../core/start-send-port-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="f07bc-120">[Start Send Port (BizTalk Server Sample)](../core/start-send-port-biztalk-server-sample.md).</span></span> <span data-ttu-id="f07bc-121">送信ポートを起動し、ファイル アダプターを使用する場合は、プライマリ トランスポート アドレスを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f07bc-121">Demonstrates how to start a send port and set the Primary Transport Address when using the FILE adapter.</span></span>  
  
-   <span data-ttu-id="f07bc-122">[オーケストレーションの停止 (BizTalk Server サンプル)](../core/stop-orchestration-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="f07bc-122">[Stop Orchestration (BizTalk Server Sample)](../core/stop-orchestration-biztalk-server-sample.md).</span></span> <span data-ttu-id="f07bc-123">BizTalk Server オーケストレーションを停止する方法について説明し、必要に応じて参加を解除します。</span><span class="sxs-lookup"><span data-stu-id="f07bc-123">Demonstrates how to stop a BizTalk Server orchestration and, optionally, to unenlist it.</span></span>