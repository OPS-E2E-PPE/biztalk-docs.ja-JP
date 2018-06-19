---
title: BizTalk Server の依存関係のトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 677b7ef3-9a91-4f1e-bfc5-926bfab23a0f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a75cf1986c9c7bf66aa48370704ca3569d0db87
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279250"
---
# <a name="troubleshooting-biztalk-server-dependencies"></a><span data-ttu-id="d10c2-102">BizTalk Server の依存関係に関するトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d10c2-102">Troubleshooting BizTalk Server Dependencies</span></span>
<span data-ttu-id="d10c2-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、デザイン時および実行時の操作において他の Microsoft 製品を頻繁に使用します。</span><span class="sxs-lookup"><span data-stu-id="d10c2-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] makes extensive use of several other Microsoft products for design time and run-time operations.</span></span> <span data-ttu-id="d10c2-104">ここでは、これらの基本テクノロジで発生する可能性がある問題を解決するために、トラブルシューティングのガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="d10c2-104">This section contains troubleshooting guidelines for resolving problems that can occur in these underlying technologies.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d10c2-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d10c2-105">In This Section</span></span>  
  
-   [<span data-ttu-id="d10c2-106">MSDTC の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d10c2-106">Troubleshooting Problems with MSDTC</span></span>](../core/troubleshooting-problems-with-msdtc.md)  
  
-   [<span data-ttu-id="d10c2-107">証明書のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d10c2-107">Troubleshooting Certificates</span></span>](../core/troubleshooting-certificates.md)  
  
-   [<span data-ttu-id="d10c2-108">エンタープライズ シングル サインオンのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d10c2-108">Troubleshooting Enterprise Single Sign-On</span></span>](../core/troubleshooting-enterprise-single-sign-on.md)  
  
-   [<span data-ttu-id="d10c2-109">SQL Server のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d10c2-109">Troubleshooting SQL Server</span></span>](../core/troubleshooting-sql-server.md)  
  
-   [<span data-ttu-id="d10c2-110">Web サービスのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d10c2-110">Troubleshooting Web Services</span></span>](../core/troubleshooting-web-services.md)  
  
-   [<span data-ttu-id="d10c2-111">Windows Server クラスターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d10c2-111">Troubleshooting a Windows Server Cluster</span></span>](../core/troubleshooting-a-windows-server-cluster.md)  
  
-   [<span data-ttu-id="d10c2-112">インターネット インフォメーション サービスのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d10c2-112">Troubleshooting Internet Information Services</span></span>](../core/troubleshooting-internet-information-services.md)  
  
-   [<span data-ttu-id="d10c2-113">Windows SharePoint Services のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d10c2-113">Troubleshooting Windows SharePoint Services</span></span>](../core/troubleshooting-windows-sharepoint-services.md)