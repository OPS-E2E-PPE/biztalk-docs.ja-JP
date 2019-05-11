---
title: 障害からの回復 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eefb036b-7254-407d-a203-66708c07f67d
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e3b7ec97b4a6bda1a3adf267717c7f6cac61851
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395095"
---
# <a name="recovering-from-a-disaster"></a><span data-ttu-id="deb01-102">障害からの回復</span><span class="sxs-lookup"><span data-stu-id="deb01-102">Recovering from a Disaster</span></span>
<span data-ttu-id="deb01-103">このセクションを運用環境の操作をディザスター リカバリー サイトに転送する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="deb01-103">This section details the steps to transfer production operations to the disaster recovery site.</span></span> <span data-ttu-id="deb01-104">このセクションの目的は、オンラインの実稼働システムを"source"システムと呼びます。</span><span class="sxs-lookup"><span data-stu-id="deb01-104">For the purposes of this section, the online production system is referred to as the “source” system.</span></span> <span data-ttu-id="deb01-105">ディザスター リカバリー サイトは、"、"destination"システム"と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="deb01-105">The disaster recovery site is referred to as the “destination” system.</span></span> <span data-ttu-id="deb01-106">このセクションでは、ディザスター リカバリーのプロセスの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="deb01-106">This section provides an overview of the disaster recovery process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="deb01-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="deb01-107">In This Section</span></span>  
  
-   [<span data-ttu-id="deb01-108">BizTalk グループの復元</span><span class="sxs-lookup"><span data-stu-id="deb01-108">Restoring the BizTalk Group</span></span>](../technical-guides/restoring-the-biztalk-group.md)  
  
-   [<span data-ttu-id="deb01-109">ランタイム コンピューターの回復</span><span class="sxs-lookup"><span data-stu-id="deb01-109">Recovering the Runtime Computers</span></span>](../technical-guides/recovering-the-runtime-computers.md)  
  
-   [<span data-ttu-id="deb01-110">その他のアプリケーションの回復</span><span class="sxs-lookup"><span data-stu-id="deb01-110">Recovering Additional Applications</span></span>](../technical-guides/recovering-additional-applications.md)  
  
-   [<span data-ttu-id="deb01-111">ログ配布のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="deb01-111">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)