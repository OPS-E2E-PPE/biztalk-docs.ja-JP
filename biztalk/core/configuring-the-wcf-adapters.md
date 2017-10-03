---
title: "WCF アダプタの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dde69bb5b2014a20509778e27230840e47c0b36d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-the-wcf-adapters"></a><span data-ttu-id="87b7e-102">WCF アダプタの構成</span><span class="sxs-lookup"><span data-stu-id="87b7e-102">Configuring the WCF Adapters</span></span>
<span data-ttu-id="87b7e-103">Windows Communication Foundation (WCF) 向け BizTalk アダプターを使用すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で WCF ベースのアプリケーションと通信できます。</span><span class="sxs-lookup"><span data-stu-id="87b7e-103">The BizTalk Adapters for Windows Communication Foundation (WCF) allow  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to communicate with WCF-based applications.</span></span> <span data-ttu-id="87b7e-104">BizTalk WCF アダプターは、WCF 定義済みバインドを表す 5 つの物理アダプターを含める-**BasicHttpBinding**、 **WsHttpBinding**、 **NetTcpBinding**、 **NetNamedPipeBinding**、および**NetMsmqBinding**です。</span><span class="sxs-lookup"><span data-stu-id="87b7e-104">The BizTalk WCF adapters include five physical adapters that represent the WCF predefined bindings—**BasicHttpBinding**, **WsHttpBinding**, **NetTcpBinding**, **NetNamedPipeBinding**, and **NetMsmqBinding**.</span></span> <span data-ttu-id="87b7e-105">定義済みバインド用 WCF アダプタの目的は、大半のアプリケーション要件に必要な情報の構成を合理化することです。</span><span class="sxs-lookup"><span data-stu-id="87b7e-105">The WCF adapters for the predefined bindings are provided to enable you to easily configure necessary information for most application requirements.</span></span>  
  
 <span data-ttu-id="87b7e-106">BizTalk WCF アダプタには、受信場所と送信ポートに関する WCF バインドと動作情報を自由に構成するために使用される、2 つのアダプタも含まれています。</span><span class="sxs-lookup"><span data-stu-id="87b7e-106">The BizTalk WCF adapters also include two adapters that enable you to freely configure WCF binding and behavior information for the receive location and send port.</span></span>  
  
 <span data-ttu-id="87b7e-107">どの WCF アダプタの場合も、送信ポートと受信場所に関するトランスポート プロパティ ダイアログ ボックスは類似しています。</span><span class="sxs-lookup"><span data-stu-id="87b7e-107">All the WCF adapters provide similar transport properties dialog boxes for send ports and receive locations.</span></span> <span data-ttu-id="87b7e-108">ただし、WCF アダプタを構成するための詳細なタスクは、物理アダプタごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="87b7e-108">However, the detailed tasks to configure the WCF adapters vary depending on the physical adapter.</span></span> <span data-ttu-id="87b7e-109">アダプタ バインドと直接関連していないタスク (証明書のインストールなど) は、すべての WCF アダプタで同じです。</span><span class="sxs-lookup"><span data-stu-id="87b7e-109">Tasks not directly related to the adapter bindings, such as installing certificates, are the same for all the WCF adapters.</span></span> <span data-ttu-id="87b7e-110">このセクションでは、すべての WCF アダプタに共通のタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="87b7e-110">This section discusses the tasks that are common to all the WCF adapters.</span></span> <span data-ttu-id="87b7e-111">アダプターごとに異なるタスクについては、アダプタの適切なトピックを参照して[WCF アダプタ](../core/wcf-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="87b7e-111">For information about tasks that differ for each adapter, see the appropriate topics for the adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="87b7e-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="87b7e-112">In This Section</span></span>  
  
-   [<span data-ttu-id="87b7e-113">WCF アダプター プロパティ スキーマおよびプロパティ</span><span class="sxs-lookup"><span data-stu-id="87b7e-113">WCF Adapters Property Schema and Properties</span></span>](../core/wcf-adapters-property-schema-and-properties.md)  
  
-   [<span data-ttu-id="87b7e-114">WCF アダプターのセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="87b7e-114">WCF Adapters Security Recommendations</span></span>](../core/wcf-adapters-security-recommendations.md)  
  
-   [<span data-ttu-id="87b7e-115">WCF アダプターの証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="87b7e-115">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="87b7e-116">WCF アダプタのメッセージ本文の指定</span><span class="sxs-lookup"><span data-stu-id="87b7e-116">Specifying the Message Body for the WCF Adapters</span></span>](../core/specifying-the-message-body-for-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="87b7e-117">WCF アダプターで WCF 機能拡張ポイントを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="87b7e-117">How to Enable the WCF Extensibility Points with the WCF Adapters</span></span>](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="87b7e-118">WCF アダプターのパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="87b7e-118">WCF Adapters Performance Counters</span></span>](../core/wcf-adapters-performance-counters.md)  
  
-   [<span data-ttu-id="87b7e-119">WCF アダプタのシングル サインオンのサポート</span><span class="sxs-lookup"><span data-stu-id="87b7e-119">Single Sign-On Support for the WCF Adapters</span></span>](../core/single-sign-on-support-for-the-wcf-adapters.md)  
  
## <a name="see-also"></a><span data-ttu-id="87b7e-120">参照</span><span class="sxs-lookup"><span data-stu-id="87b7e-120">See Also</span></span>  
 [<span data-ttu-id="87b7e-121">WCF アダプタ</span><span class="sxs-lookup"><span data-stu-id="87b7e-121">WCF Adapters</span></span>](../core/wcf-adapters.md)