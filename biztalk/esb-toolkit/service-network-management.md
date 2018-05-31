---
title: サービスのネットワークの管理 |Microsoft ドキュメント
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
ms.openlocfilehash: 741abaaa3042cb40f7043b25ce041bb84740f26a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294770"
---
# <a name="service-network-management"></a><span data-ttu-id="efd04-102">サービスのネットワーク管理</span><span class="sxs-lookup"><span data-stu-id="efd04-102">Service Network Management</span></span>
<span data-ttu-id="efd04-103">効果的な実行時の管理には、実行時環境にデプロイされているサービスの知識が必要です。</span><span class="sxs-lookup"><span data-stu-id="efd04-103">Effective run-time governance requires knowledge of the services deployed into the run-time environment.</span></span> <span data-ttu-id="efd04-104">AmberPoint SMS には、実際の受信場所と送信では、図 1 に示すようを BizTalk 管理グループ内に配置されたポートを検出できます。</span><span class="sxs-lookup"><span data-stu-id="efd04-104">AmberPoint SMS can discover the actual receive locations and send ports deployed within a BizTalk Management Group, as shown in Figure 1.</span></span>  
  
 <span data-ttu-id="efd04-105">![AmberPoint コンテナーの検出](../esb-toolkit/media/ch9-amberpointcontainerdiscovery.gif "Ch9 AmberPointContainerDiscovery")</span><span class="sxs-lookup"><span data-stu-id="efd04-105">![AmberPoint Container Discovery](../esb-toolkit/media/ch9-amberpointcontainerdiscovery.gif "Ch9-AmberPointContainerDiscovery")</span></span>  
  
 <span data-ttu-id="efd04-106">**図 1**</span><span class="sxs-lookup"><span data-stu-id="efd04-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="efd04-107">**AmberPoint コンテナーの検出を SMS 画面**</span><span class="sxs-lookup"><span data-stu-id="efd04-107">**The AmberPoint SMS Container Discovery screens**</span></span>  
  
 <span data-ttu-id="efd04-108">AmberPoint SMS は実行時構成を把握し、実行されている、内の他のサービスへの依存関係を認めるようにユーザーを支援するサービスのさまざまなパースペクティブをデプロイ済みサービスの情報を使用して、サービスのネットワーク。</span><span class="sxs-lookup"><span data-stu-id="efd04-108">Using information on the deployed services, AmberPoint SMS presents various perspectives of the services that help users to understand the run-time configuration and appreciate their dependencies on other services within the running service network.</span></span> <span data-ttu-id="efd04-109">図 2 は、サービスのプロファイルとの依存関係の画面を示しています。</span><span class="sxs-lookup"><span data-stu-id="efd04-109">Figure 2 shows the service profile and dependencies screens.</span></span>  
  
 <span data-ttu-id="efd04-110">![AmberPoint サービス プロファイル](../esb-toolkit/media/ch9-amberpointserviceprofile.gif "Ch9 AmberPointServiceProfile")</span><span class="sxs-lookup"><span data-stu-id="efd04-110">![AmberPoint Service Profile](../esb-toolkit/media/ch9-amberpointserviceprofile.gif "Ch9-AmberPointServiceProfile")</span></span>  
  
 <span data-ttu-id="efd04-111">**図 2**</span><span class="sxs-lookup"><span data-stu-id="efd04-111">**Figure 2**</span></span>  
  
 <span data-ttu-id="efd04-112">**AmberPoint SMS サービスのプロファイルとの依存関係の画面**</span><span class="sxs-lookup"><span data-stu-id="efd04-112">**The AmberPoint SMS service profile and dependencies screens**</span></span>  
  
 <span data-ttu-id="efd04-113">AmberPoint SMS の発行およびなどを既存の Universal Description, Discovery, と Integration (UDDI) レジストリ、カスタム構成管理リポジトリでは、and マスター システム管理コンソールでは、サービスの検出と実行時のメタデータを転送できます。Microsoft Operations Manager (MOM) 2004 と System Center Operations Manager 2007 (SCOM)。</span><span class="sxs-lookup"><span data-stu-id="efd04-113">AmberPoint SMS can publish and forward service discoveries and run-time metadata to existing Universal Description, Discovery, and Integration (UDDI) registries, custom configuration management repositories, and master system management consoles, such as Microsoft Operations Manager 2004 (MOM) and System Center Operations Manager 2007 (SCOM).</span></span>