---
title: サービス ネットワーク管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 21469dad-6c64-470a-bd58-8309d789ce6c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4280438758e3f2626cf2e0ec68c1e30f51d0bde
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268894"
---
# <a name="service-network-management"></a><span data-ttu-id="3cc59-102">サービス ネットワーク管理</span><span class="sxs-lookup"><span data-stu-id="3cc59-102">Service Network Management</span></span>
<span data-ttu-id="3cc59-103">実行時の効果的な管理には、実行時環境にデプロイされているサービスの知識が必要です。</span><span class="sxs-lookup"><span data-stu-id="3cc59-103">Effective run-time governance requires knowledge of the services deployed into the run-time environment.</span></span> <span data-ttu-id="3cc59-104">AmberPoint SMS には、実際に受信場所と、図 1 に示すように、BizTalk 管理グループ内にデプロイされたポートを送信を検出できます。</span><span class="sxs-lookup"><span data-stu-id="3cc59-104">AmberPoint SMS can discover the actual receive locations and send ports deployed within a BizTalk Management Group, as shown in Figure 1.</span></span>  
  
 <span data-ttu-id="3cc59-105">![AmberPoint コンテナーの検出](../esb-toolkit/media/ch9-amberpointcontainerdiscovery.gif "Ch9 AmberPointContainerDiscovery")</span><span class="sxs-lookup"><span data-stu-id="3cc59-105">![AmberPoint Container Discovery](../esb-toolkit/media/ch9-amberpointcontainerdiscovery.gif "Ch9-AmberPointContainerDiscovery")</span></span>  
  
 <span data-ttu-id="3cc59-106">**図 1**</span><span class="sxs-lookup"><span data-stu-id="3cc59-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="3cc59-107">**AmberPoint コンテナーの検出を SMS 画面**</span><span class="sxs-lookup"><span data-stu-id="3cc59-107">**The AmberPoint SMS Container Discovery screens**</span></span>  
  
 <span data-ttu-id="3cc59-108">AmberPoint SMS 情報を使用して、デプロイされたサービスで、ユーザーが実行時構成を理解し、実行中の他のサービスへの依存関係を理解に役立つサービスのさまざまなパースペクティブが表示サービスのネットワーク。</span><span class="sxs-lookup"><span data-stu-id="3cc59-108">Using information on the deployed services, AmberPoint SMS presents various perspectives of the services that help users to understand the run-time configuration and appreciate their dependencies on other services within the running service network.</span></span> <span data-ttu-id="3cc59-109">図 2 は、サービスのプロファイルとの依存関係の画面を示しています。</span><span class="sxs-lookup"><span data-stu-id="3cc59-109">Figure 2 shows the service profile and dependencies screens.</span></span>  
  
 <span data-ttu-id="3cc59-110">![AmberPoint サービス プロファイル](../esb-toolkit/media/ch9-amberpointserviceprofile.gif "Ch9 AmberPointServiceProfile")</span><span class="sxs-lookup"><span data-stu-id="3cc59-110">![AmberPoint Service Profile](../esb-toolkit/media/ch9-amberpointserviceprofile.gif "Ch9-AmberPointServiceProfile")</span></span>  
  
 <span data-ttu-id="3cc59-111">**図 2**</span><span class="sxs-lookup"><span data-stu-id="3cc59-111">**Figure 2**</span></span>  
  
 <span data-ttu-id="3cc59-112">**SMS の AmberPoint サービス プロファイルとの依存関係画面**</span><span class="sxs-lookup"><span data-stu-id="3cc59-112">**The AmberPoint SMS service profile and dependencies screens**</span></span>  
  
 <span data-ttu-id="3cc59-113">AmberPoint SMS に公開したりなどに、既存の Universal Description, Discovery, と Integration (UDDI) レジストリ、カスタム構成の管理リポジトリ、and マスター システム管理コンソールでは、サービスの検出と実行時のメタデータを転送できます。Microsoft Operations Manager (MOM) 2004 と System Center Operations Manager 2007 (SCOM)。</span><span class="sxs-lookup"><span data-stu-id="3cc59-113">AmberPoint SMS can publish and forward service discoveries and run-time metadata to existing Universal Description, Discovery, and Integration (UDDI) registries, custom configuration management repositories, and master system management consoles, such as Microsoft Operations Manager 2004 (MOM) and System Center Operations Manager 2007 (SCOM).</span></span>