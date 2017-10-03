---
title: "BAM データを受信する WCF アダプタの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd705c27-5d04-47e5-9bb2-61235f8fe544
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f418512ecd0a3e38f884965d1698579fb300dd74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-the-wcf-adapter-to-intercept-bam-data"></a><span data-ttu-id="508f3-102">BAM データを受信するための WCF アダプタの構成</span><span class="sxs-lookup"><span data-stu-id="508f3-102">Configuring the WCF Adapter to Intercept BAM Data</span></span>
<span data-ttu-id="508f3-103">このセクションでは、BAM WCF インターセプタと連携するように BizTalk WCF アダプタを構成するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="508f3-103">This section contains information about the steps you must take to configure the BizTalk WCF adapter to work with the BAM WCF interceptor.</span></span>  
  
 <span data-ttu-id="508f3-104">基本的な手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="508f3-104">The basic steps are as follows:</span></span>  
  
-   <span data-ttu-id="508f3-105">BAM の動作を machine.config ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="508f3-105">Add the BAM behavior to the machine.config file.</span></span>  
  
-   <span data-ttu-id="508f3-106">BizTalk WCF アダプタを作成します。</span><span class="sxs-lookup"><span data-stu-id="508f3-106">Create a BizTalk WCF adapter.</span></span>  
  
-   <span data-ttu-id="508f3-107">BAM WCF インターセプタを構成します。</span><span class="sxs-lookup"><span data-stu-id="508f3-107">Configure the BAM WCF interception.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="508f3-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="508f3-108">In This Section</span></span>  
  
-   [<span data-ttu-id="508f3-109">BAM インターセプタ動作を Machine.config ファイルに追加する方法</span><span class="sxs-lookup"><span data-stu-id="508f3-109">How to Add the BAM Interceptor Behavior to the Machine.config File</span></span>](../core/how-to-add-the-bam-interceptor-behavior-to-the-machine-config-file.md)  
  
-   [<span data-ttu-id="508f3-110">BizTalk Server の WCF アダプターを作成する方法</span><span class="sxs-lookup"><span data-stu-id="508f3-110">How to Create a WCF Adapter for BizTalk Server</span></span>](../core/how-to-create-a-wcf-adapter-for-biztalk-server.md)  
  
-   [<span data-ttu-id="508f3-111">構成する方法の場所と送受信ポートを BAM WCF インターセプション用</span><span class="sxs-lookup"><span data-stu-id="508f3-111">How to Configure Receive and Send Locations and Ports for BAM WCF Interception</span></span>](../core/how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception.md)  
  
-   [<span data-ttu-id="508f3-112">BAM WCF インターセプションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="508f3-112">How to Configure the BAM WCF Interception</span></span>](../core/how-to-configure-the-bam-wcf-interception.md)  
  
-   [<span data-ttu-id="508f3-113">エラー処理の使用</span><span class="sxs-lookup"><span data-stu-id="508f3-113">Using Fault Handling</span></span>](../core/using-fault-handling.md)