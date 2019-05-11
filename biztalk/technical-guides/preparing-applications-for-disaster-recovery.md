---
title: アプリケーションのディザスター リカバリーの準備 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0ef93099-aa6b-424a-a4ce-87d855c6afe3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b9d328d8c1e2f8085c8a1a1709a78824661f62c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379460"
---
# <a name="preparing-applications-for-disaster-recovery"></a><span data-ttu-id="43a32-102">アプリケーションのディザスター リカバリーの準備</span><span class="sxs-lookup"><span data-stu-id="43a32-102">Preparing Applications for Disaster Recovery</span></span>
<span data-ttu-id="43a32-103">BizTalk アプリケーション (バイナリと構成アイテムなどの受信場所と送信ポート) は、ディザスター リカバリー サイトで、グループが復元されるときに、運用環境の BizTalk グループにデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="43a32-103">BizTalk applications (binaries and configuration artifacts such as receive locations and send ports) are deployed to the production BizTalk group when the group is restored at the disaster recovery site.</span></span> <span data-ttu-id="43a32-104">この構成は、かどうかに応じて変更する必要がありますは受信場所と運用環境に固有のポートの送信などの構成の場所があります。</span><span class="sxs-lookup"><span data-stu-id="43a32-104">This configuration may have to be altered depending on whether there are configuration locations such as receive locations and send ports that are production-specific.</span></span>  
  
 <span data-ttu-id="43a32-105">ディザスター リカバリー サイトでアプリケーションの復元を高速化、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でバイナリをインストールする .msi ファイル、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サーバーの実行時間保持する必要が最新の状態のディザスター リカバリー[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行時のサーバー。</span><span class="sxs-lookup"><span data-stu-id="43a32-105">To speed the restoration of applications at the disaster recovery site, a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] .msi file that installs the binaries on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time servers must be kept up-to-date on the disaster recovery [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time servers.</span></span> <span data-ttu-id="43a32-106">ディザスター リカバリーに固有のアプリケーション構成の .msi ファイルをなど、アプリケーションの災害復旧に固有の成果物を構成するためにインストールする必要があります、ディザスター リカバリー サイトで運用環境の BizTalk グループが復元されると、受信場所と、必要に応じて、送信ポート。</span><span class="sxs-lookup"><span data-stu-id="43a32-106">When the production BizTalk group is restored at the disaster recovery site, a disaster recovery-specific application configuration .msi file may need to be installed in order to configure the application for disaster recovery-specific artifacts, such as receive locations and send ports, as necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43a32-107">参照</span><span class="sxs-lookup"><span data-stu-id="43a32-107">See Also</span></span>  
 [<span data-ttu-id="43a32-108">アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="43a32-108">Deploying an Application</span></span>](../technical-guides/deploying-an-application.md)