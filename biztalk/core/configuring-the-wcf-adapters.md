---
title: WCF アダプタの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- NetTcpBinding [WCF adapters]
- configuring [WCF adapters]
- WCF adapters, pre-defined bindings
- configuring [WCF adapters], about configuring WCF adapters
- WsHttpBinding [WCF adapters]
- BasicHttpBinding [WCF adapters]
- NetNamedPipeBinding [WCF adapters]
- NetMsmqBinding [WCF adapters]
- bindings, pre-defined [WCF adapters]
- WCF adapters, configuring
ms.assetid: af01e2d4-303d-407a-b853-dd90b0246a8a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3dbe2541a85879f21d6d2393280933d8335dac0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355129"
---
# <a name="configuring-the-wcf-adapters"></a><span data-ttu-id="0c3dc-102">WCF アダプタの構成</span><span class="sxs-lookup"><span data-stu-id="0c3dc-102">Configuring the WCF Adapters</span></span>
<span data-ttu-id="0c3dc-103">BizTalk アダプターの Windows Communication Foundation (WCF) を許可する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]WCF ベースのアプリケーションと通信します。</span><span class="sxs-lookup"><span data-stu-id="0c3dc-103">The BizTalk Adapters for Windows Communication Foundation (WCF) allow  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to communicate with WCF-based applications.</span></span> <span data-ttu-id="0c3dc-104">BizTalk WCF アダプタには、WCF 定義済みバインドを表す 5 つの物理アダプタが含まれています —**BasicHttpBinding**、 **WsHttpBinding**、 **NetTcpBinding**、 **NetNamedPipeBinding**、および**NetMsmqBinding**します。</span><span class="sxs-lookup"><span data-stu-id="0c3dc-104">The BizTalk WCF adapters include five physical adapters that represent the WCF predefined bindings—**BasicHttpBinding**, **WsHttpBinding**, **NetTcpBinding**, **NetNamedPipeBinding**, and **NetMsmqBinding**.</span></span> <span data-ttu-id="0c3dc-105">定義済みバインド用 WCF アダプタは、ほとんどのアプリケーション要件に必要な情報を簡単に構成するために提供されます。</span><span class="sxs-lookup"><span data-stu-id="0c3dc-105">The WCF adapters for the predefined bindings are provided to enable you to easily configure necessary information for most application requirements.</span></span>  
  
 <span data-ttu-id="0c3dc-106">BizTalk WCF アダプターでは、WCF バインドと動作については、受信場所の構成し、送信ポートを自由にするための 2 つのアダプターも含まれます。</span><span class="sxs-lookup"><span data-stu-id="0c3dc-106">The BizTalk WCF adapters also include two adapters that enable you to freely configure WCF binding and behavior information for the receive location and send port.</span></span>  
  
 <span data-ttu-id="0c3dc-107">すべてのプロパティ ダイアログ ボックスのようなトランスポートを提供する WCF アダプタは送信ポートと受信場所。</span><span class="sxs-lookup"><span data-stu-id="0c3dc-107">All the WCF adapters provide similar transport properties dialog boxes for send ports and receive locations.</span></span> <span data-ttu-id="0c3dc-108">ただし、WCF アダプタを構成する詳細なタスクは、物理アダプターによって異なります。</span><span class="sxs-lookup"><span data-stu-id="0c3dc-108">However, the detailed tasks to configure the WCF adapters vary depending on the physical adapter.</span></span> <span data-ttu-id="0c3dc-109">証明書のインストールなど、アダプターのバインドに直接関連しないタスクは、すべての WCF アダプターは同じです。</span><span class="sxs-lookup"><span data-stu-id="0c3dc-109">Tasks not directly related to the adapter bindings, such as installing certificates, are the same for all the WCF adapters.</span></span> <span data-ttu-id="0c3dc-110">このセクションでは、すべての WCF アダプタに共通するタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0c3dc-110">This section discusses the tasks that are common to all the WCF adapters.</span></span> <span data-ttu-id="0c3dc-111">アダプターごとに異なるタスクについては、アダプターでの該当するトピックを参照してください。 [WCF アダプタ](../core/wcf-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="0c3dc-111">For information about tasks that differ for each adapter, see the appropriate topics for the adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0c3dc-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0c3dc-112">In This Section</span></span>  
  
-   [<span data-ttu-id="0c3dc-113">WCF アダプター プロパティ スキーマおよびプロパティ</span><span class="sxs-lookup"><span data-stu-id="0c3dc-113">WCF Adapters Property Schema and Properties</span></span>](../core/wcf-adapters-property-schema-and-properties.md)  
  
-   [<span data-ttu-id="0c3dc-114">WCF アダプターのセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="0c3dc-114">WCF Adapters Security Recommendations</span></span>](../core/wcf-adapters-security-recommendations.md)  
  
-   [<span data-ttu-id="0c3dc-115">WCF アダプターの証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="0c3dc-115">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="0c3dc-116">WCF アダプターのメッセージ本文の指定</span><span class="sxs-lookup"><span data-stu-id="0c3dc-116">Specifying the Message Body for the WCF Adapters</span></span>](../core/specifying-the-message-body-for-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="0c3dc-117">WCF アダプターで WCF 機能拡張ポイントを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="0c3dc-117">How to Enable the WCF Extensibility Points with the WCF Adapters</span></span>](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="0c3dc-118">WCF アダプターのパフォーマンス カウンタ</span><span class="sxs-lookup"><span data-stu-id="0c3dc-118">WCF Adapters Performance Counters</span></span>](../core/wcf-adapters-performance-counters.md)  
  
-   [<span data-ttu-id="0c3dc-119">WCF アダプターのシングル サインオンのサポート</span><span class="sxs-lookup"><span data-stu-id="0c3dc-119">Single Sign-On Support for the WCF Adapters</span></span>](../core/single-sign-on-support-for-the-wcf-adapters.md)  
  
## <a name="see-also"></a><span data-ttu-id="0c3dc-120">参照</span><span class="sxs-lookup"><span data-stu-id="0c3dc-120">See Also</span></span>  
 [<span data-ttu-id="0c3dc-121">WCF アダプター</span><span class="sxs-lookup"><span data-stu-id="0c3dc-121">WCF Adapters</span></span>](../core/wcf-adapters.md)