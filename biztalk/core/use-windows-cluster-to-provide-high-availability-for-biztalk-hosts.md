---
title: "Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現する |Microsoft ドキュメント"
ms.custom: 
ms.date: 2016-01-04
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Passive configuration [Master Secret server]
- Active configuration [Master Secret server]
- clustering, about clustering
- high availability
- Windows Server cluster, warnings
- installation, high availibility planning
- Master Secret server
- installation, configuring
- Master Secret server, configuring
- installation, Windows Server cluster
- clustering
ms.assetid: 4d7f0842-561e-49e0-ab08-504256b9294f
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 338f9fd39208f85ce5748f5ebe5548fa9487c9df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-windows-server-cluster-to-provide-high-availability-for-biztalk-server-hosts2"></a><span data-ttu-id="a2785-102">Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには</span><span class="sxs-lookup"><span data-stu-id="a2785-102">Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a2785-103">BizTalk ホストを Windows Server フェールオーバー クラスター グループ内のクラスター リソースとして構成できるようにする機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="a2785-103"> provides functionality that allows you to configure a BizTalk host as a clustered resource within a  Windows Server failover cluster group.</span></span> <span data-ttu-id="a2785-104">ホストのクラスター化対応により、FTP の受信ハンドラー、(場合によっては) POP3 受信ハンドラーなど、本来であれば複数のホスト インスタンスで同時に実行することのできない、統合された BizTalk アダプターで高い可用性を実現できるようになっています。</span><span class="sxs-lookup"><span data-stu-id="a2785-104">Host cluster support is provided to support high availability for integrated BizTalk adapters that should not be run in multiple host instances simultaneously, such as the FTP receive handler or, under certain circumstances, the POP3 receive handler.</span></span> <span data-ttu-id="a2785-105">MSMQ サービスのクラスター化が必要となるような状況でも、MSMQ アダプターによって送受信されたメッセージについて、トランザクションの一貫性を確実に保つことができます。</span><span class="sxs-lookup"><span data-stu-id="a2785-105">Host cluster support is also provided to ensure transactional consistency for messages sent or received by the MSMQ adapter in scenarios that require that the MSMQ service is clustered.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2785-106">ホスト クラスタリングは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Enterprise Edition のみで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2785-106">Host clustering is only available with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Enterprise Edition.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2785-107">BizTalk ホストをクラスターする前にする必要がありますが構成で少なくとも 2 つ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]内のコンピューター、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Windows Server フェールオーバー クラスターのメンバーとしてグループ化します。</span><span class="sxs-lookup"><span data-stu-id="a2785-107">Before you can cluster a BizTalk host, you must have configured at least two [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group as members of a Windows Server Failover cluster.</span></span> <span data-ttu-id="a2785-108">Windows Server フェールオーバー クラスターを構成する方法の詳細については、Windows Server のオンライン ヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2785-108">For more information about configuring a Windows Server Failover cluster, please see the Windows Server online help.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a2785-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a2785-109">In This Section</span></span>  
  
-   [<span data-ttu-id="a2785-110">Windows Server クラスター上の BizTalk Server のインストールに関する注意点</span><span class="sxs-lookup"><span data-stu-id="a2785-110">Considerations for Installing BizTalk Server on a Windows Server Cluster</span></span>](../core/considerations-for-installing-biztalk-server-on-a-windows-server-cluster2.md)  
  
-   [<span data-ttu-id="a2785-111">BizTalk ホストをクラスター リソースとして構成する方法</span><span class="sxs-lookup"><span data-stu-id="a2785-111">How to Configure a BizTalk Host as a Cluster Resource</span></span>](../core/how-to-configure-a-biztalk-host-as-a-cluster-resource1.md)  
  
-   [<span data-ttu-id="a2785-112">クラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="a2785-112">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)