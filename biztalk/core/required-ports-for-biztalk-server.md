---
title: BizTalk Server のポートに必要な |Microsoft ドキュメント
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
ms.openlocfilehash: a3024d0a4b2012318b52b4ad51c328dd55124241
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268354"
---
# <a name="required-ports-for-biztalk-server"></a><span data-ttu-id="a02b7-102">BizTalk Server に必要なポート</span><span class="sxs-lookup"><span data-stu-id="a02b7-102">Required Ports for BizTalk Server</span></span>
<span data-ttu-id="a02b7-103">詳細については、BizTalk Server の展開をセキュリティで保護する、次を参照してください。[サンプル BizTalk Server アーキテクチャ](../core/sample-biztalk-server-architectures.md)です。</span><span class="sxs-lookup"><span data-stu-id="a02b7-103">For complete information about securing your BizTalk Server deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="a02b7-104">このセクションでは、BizTalk Server コンポーネントが相互に通信できるようにファイアウォールで開く必要のあるポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a02b7-104">This section provides information about the ports you need to open on the firewalls so that the BizTalk Server components can communicate with each other.</span></span>  
  
 <span data-ttu-id="a02b7-105">実稼働環境に BizTalk Server で使用するサーバー以外のサーバーがある場合、他のポートを開くことが必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a02b7-105">If you have other servers in your production environment in addition to the ones BizTalk Server uses, you may need to open additional ports.</span></span> <span data-ttu-id="a02b7-106">詳細について、Windows Server System™ のポートの要件は、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=25713](http://go.microsoft.com/fwlink/?LinkId=25713)です。</span><span class="sxs-lookup"><span data-stu-id="a02b7-106">For more information about the port requirements for the Windows Server System™, see [http://go.microsoft.com/fwlink/?LinkId=25713](http://go.microsoft.com/fwlink/?LinkId=25713).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a02b7-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a02b7-107">In This Section</span></span>  
  
-   [<span data-ttu-id="a02b7-108">受信と送信サーバーのポート</span><span class="sxs-lookup"><span data-stu-id="a02b7-108">Ports for the Receive and Send Servers</span></span>](../core/ports-for-the-receive-and-send-servers.md)  
  
-   [<span data-ttu-id="a02b7-109">管理サーバーのポート</span><span class="sxs-lookup"><span data-stu-id="a02b7-109">Ports for the Administration Server</span></span>](../core/ports-for-the-administration-server.md)  
  
-   [<span data-ttu-id="a02b7-110">追跡サーバーのポート</span><span class="sxs-lookup"><span data-stu-id="a02b7-110">Ports for the Tracking Server</span></span>](../core/ports-for-the-tracking-server.md)  
  
-   [<span data-ttu-id="a02b7-111">処理サーバーのポート</span><span class="sxs-lookup"><span data-stu-id="a02b7-111">Ports for the Processing Servers</span></span>](../core/ports-for-the-processing-servers.md)  
  
-   [<span data-ttu-id="a02b7-112">エンタープライズ シングル サインオン サーバーのポート</span><span class="sxs-lookup"><span data-stu-id="a02b7-112">Ports for the Enterprise Single Sign-On Servers</span></span>](../core/ports-for-the-enterprise-single-sign-on-servers.md)  
  
-   [<span data-ttu-id="a02b7-113">BAM ポータル サーバーのポート</span><span class="sxs-lookup"><span data-stu-id="a02b7-113">Ports for the BAM Portal Server</span></span>](../core/ports-for-the-bam-portal-server.md)