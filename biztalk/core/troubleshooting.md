---
title: トラブルシューティングと既知の問題 |Microsoft ドキュメント
description: 既知の問題、ゾンビ状態、パフォーマンスのトラブルシューティング、アダプターのトラブルシューティングを行う、アクセス許可のトラブルシューティング、EDI および AS2、および BizTalk Server で複数のトラブルシューティング
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ecb934c6-3efa-40b6-949b-a04a73e60b07
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df13438e641d55de91096b690a8e5e95e26cbfa4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286690"
---
# <a name="troubleshooting"></a><span data-ttu-id="d634f-103">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d634f-103">Troubleshooting</span></span>

## <a name="overview"></a><span data-ttu-id="d634f-104">概要</span><span class="sxs-lookup"><span data-stu-id="d634f-104">Overview</span></span>
<span data-ttu-id="d634f-105">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]、インターネット インフォメーション サービス (IIS)、Microsoft Windows Server クラスター、エンタープライズ シングル サインオン、Windows [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] など、さまざまな Microsoft テクノロジが利用されています。また、これらのテクノロジに依存する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="d634f-105">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] makes use of or may depend on several different Microsoft technologies including but not limited to Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], the Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)], Internet Information Services (IIS), Microsoft Windows Server Cluster, Enterprise Single Sign-On, and Windows [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span></span> <span data-ttu-id="d634f-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は非常に多くのテクノロジと共に使用されているため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] での問題についてトラブルシューティングを行う場合は、使用されている基本テクノロジや依存関係に関するトラブルシューティングが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="d634f-106">Because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is used with so many other technologies, troubleshooting a problem with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] often involves troubleshooting the underlying technology or dependency that is being used.</span></span> <span data-ttu-id="d634f-107">このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の特定の問題、および[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が依存するソフトウェアで発生する可能性がある問題のトラブルシューティングに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d634f-107">This section provides information about troubleshooting specific [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] problems and information about troubleshooting problems that can occur in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] dependency software.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d634f-108">次の手順</span><span class="sxs-lookup"><span data-stu-id="d634f-108">Next steps</span></span> 
  
-   [<span data-ttu-id="d634f-109">BizTalk Server に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="d634f-109">Known Issues with BizTalk Server</span></span>](../core/known-issues-with-biztalk-server.md)  

-   [<span data-ttu-id="d634f-110">BizTalk Server のゾンビ</span><span class="sxs-lookup"><span data-stu-id="d634f-110">Zombies in BizTalk Server</span></span>](zombies-in-biztalk-server.md)
  
-   [<span data-ttu-id="d634f-111">BizTalk Server 管理をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="d634f-111">Troubleshoot BizTalk Server Administration</span></span>](../core/troubleshooting-biztalk-server-administration.md)  
  
-   [<span data-ttu-id="d634f-112">System.Net のログ記録を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d634f-112">Enabling System.Net Logging</span></span>](../core/enabling-system-net-logging.md)  
  
-   [<span data-ttu-id="d634f-113">BizTalk Server のアクセス許可をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="d634f-113">Troubleshoot BizTalk Server Permissions</span></span>](../core/troubleshooting-biztalk-server-permissions.md)  
  
-   [<span data-ttu-id="d634f-114">BizTalk Server のパフォーマンスをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="d634f-114">Troubleshoot BizTalk Server Performance</span></span>](../core/troubleshooting-biztalk-server-performance.md)  
  
-   [<span data-ttu-id="d634f-115">BizTalk Server アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="d634f-115">Troubleshoot BizTalk Server Adapters</span></span>](../core/troubleshooting-biztalk-server-adapters.md)  
  
-   [<span data-ttu-id="d634f-116">EDI および AS2 ソリューションをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="d634f-116">Troubleshoot EDI and AS2 Solutions</span></span>](../core/troubleshooting-edi-and-as2-solutions.md)  
  
-   [<span data-ttu-id="d634f-117">BizTalk Server の依存関係をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="d634f-117">Troubleshoot BizTalk Server Dependencies</span></span>](../core/troubleshooting-biztalk-server-dependencies.md)  
  
-   [<span data-ttu-id="d634f-118">構成をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="d634f-118">Troubleshoot Configuration</span></span>](../core/troubleshooting-configuration.md)  
  
-   [<span data-ttu-id="d634f-119">BizTalk プロセスのメモリ ダンプを取得します。</span><span class="sxs-lookup"><span data-stu-id="d634f-119">Get a Memory Dump of a BizTalk Process</span></span>](../core/how-to-capture-a-memory-dump-of-a-biztalk-process.md)  
  
-   [<span data-ttu-id="d634f-120">ツールとユーティリティ</span><span class="sxs-lookup"><span data-stu-id="d634f-120">Tools and Utilities</span></span>](../core/tools-and-utilities-to-use-for-troubleshooting.md)  
  
-   [<span data-ttu-id="d634f-121">16 進数の内容の中断メッセージを使用して、メッセージ検証エラーのトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="d634f-121">Troubleshoot Message Validation Failures using the Hexadecimal Contents of Suspended Messages</span></span>](../core/troubleshoot-message-validation-failures-using-the-hexadecimal-contents.md)

- [<span data-ttu-id="d634f-122">イベントとエラー</span><span class="sxs-lookup"><span data-stu-id="d634f-122">Events and Errors</span></span>](events-and-errors2.md)