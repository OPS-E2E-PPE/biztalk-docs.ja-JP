---
title: BizTalk Server のポートに必要な |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a11cec7a-de97-47f9-9153-0be82d694fab
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7f30257a85b19bf952672a5a27cc943fc50a68b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267790"
---
# <a name="required-ports-for-biztalk-server"></a><span data-ttu-id="44697-102">BizTalk Server に必要なポート</span><span class="sxs-lookup"><span data-stu-id="44697-102">Required Ports for BizTalk Server</span></span>
<span data-ttu-id="44697-103">BizTalk Server の展開をセキュリティで保護する方法の詳細については、「 [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44697-103">For complete information about securing your BizTalk Server deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="44697-104">このセクションでは、BizTalk Server コンポーネントが互いに通信できるように、ファイアウォールで開く必要があるポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="44697-104">This section provides information about the ports you need to open on the firewalls so that the BizTalk Server components can communicate with each other.</span></span>  
  
 <span data-ttu-id="44697-105">BizTalk Server で使用するだけでなく、運用環境でその他のサーバーがある場合は、追加のポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="44697-105">If you have other servers in your production environment in addition to the ones BizTalk Server uses, you may need to open additional ports.</span></span> <span data-ttu-id="44697-106">Windows Server System™ ポートの要件の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=25713](http://go.microsoft.com/fwlink/?LinkId=25713)します。</span><span class="sxs-lookup"><span data-stu-id="44697-106">For more information about the port requirements for the Windows Server System™, see [http://go.microsoft.com/fwlink/?LinkId=25713](http://go.microsoft.com/fwlink/?LinkId=25713).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="44697-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="44697-107">In This Section</span></span>  
  
-   [<span data-ttu-id="44697-108">受信サーバーと送信サーバーのポート</span><span class="sxs-lookup"><span data-stu-id="44697-108">Ports for the Receive and Send Servers</span></span>](../core/ports-for-the-receive-and-send-servers.md)  
  
-   [<span data-ttu-id="44697-109">管理サーバーのポート</span><span class="sxs-lookup"><span data-stu-id="44697-109">Ports for the Administration Server</span></span>](../core/ports-for-the-administration-server.md)  
  
-   [<span data-ttu-id="44697-110">追跡サーバーのポート</span><span class="sxs-lookup"><span data-stu-id="44697-110">Ports for the Tracking Server</span></span>](../core/ports-for-the-tracking-server.md)  
  
-   [<span data-ttu-id="44697-111">処理サーバーのポート</span><span class="sxs-lookup"><span data-stu-id="44697-111">Ports for the Processing Servers</span></span>](../core/ports-for-the-processing-servers.md)  
  
-   [<span data-ttu-id="44697-112">Enterprise Single Sign-On サーバーのポート</span><span class="sxs-lookup"><span data-stu-id="44697-112">Ports for the Enterprise Single Sign-On Servers</span></span>](../core/ports-for-the-enterprise-single-sign-on-servers.md)  
  
-   [<span data-ttu-id="44697-113">BAM ポータル サーバーのポート</span><span class="sxs-lookup"><span data-stu-id="44697-113">Ports for the BAM Portal Server</span></span>](../core/ports-for-the-bam-portal-server.md)