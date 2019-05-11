---
title: BizTalk Server の依存関係のトラブルシューティング |Microsoft Docs
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
ms.openlocfilehash: 4b532fcdd7b323ad537a6cd0534ae690bd0c360c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398686"
---
# <a name="troubleshooting-biztalk-server-dependencies"></a><span data-ttu-id="05835-102">BizTalk Server の依存関係のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="05835-102">Troubleshooting BizTalk Server Dependencies</span></span>
<span data-ttu-id="05835-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]デザイン時および実行時の操作の他のいくつかのマイクロソフト製品の広範に使用します。</span><span class="sxs-lookup"><span data-stu-id="05835-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] makes extensive use of several other Microsoft products for design time and run-time operations.</span></span> <span data-ttu-id="05835-104">このセクションには、これらのテクノロジを基になるで発生する可能性がある問題を解決するためのトラブルシューティングのガイドラインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="05835-104">This section contains troubleshooting guidelines for resolving problems that can occur in these underlying technologies.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="05835-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="05835-105">In This Section</span></span>  
  
-   [<span data-ttu-id="05835-106">MSDTC に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="05835-106">Troubleshooting Problems with MSDTC</span></span>](../core/troubleshooting-problems-with-msdtc.md)  
  
-   [<span data-ttu-id="05835-107">証明書のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="05835-107">Troubleshooting Certificates</span></span>](../core/troubleshooting-certificates.md)  
  
-   [<span data-ttu-id="05835-108">エンタープライズ シングル サインオンのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="05835-108">Troubleshooting Enterprise Single Sign-On</span></span>](../core/troubleshooting-enterprise-single-sign-on.md)  
  
-   [<span data-ttu-id="05835-109">SQL Server のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="05835-109">Troubleshooting SQL Server</span></span>](../core/troubleshooting-sql-server.md)  
  
-   [<span data-ttu-id="05835-110">Web サービスのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="05835-110">Troubleshooting Web Services</span></span>](../core/troubleshooting-web-services.md)  
  
-   [<span data-ttu-id="05835-111">Windows Server クラスターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="05835-111">Troubleshooting a Windows Server Cluster</span></span>](../core/troubleshooting-a-windows-server-cluster.md)  
  
-   [<span data-ttu-id="05835-112">インターネット インフォメーション サービスのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="05835-112">Troubleshooting Internet Information Services</span></span>](../core/troubleshooting-internet-information-services.md)  
  
-   [<span data-ttu-id="05835-113">Windows SharePoint Services のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="05835-113">Troubleshooting Windows SharePoint Services</span></span>](../core/troubleshooting-windows-sharepoint-services.md)