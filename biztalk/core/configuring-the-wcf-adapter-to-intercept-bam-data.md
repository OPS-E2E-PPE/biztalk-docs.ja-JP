---
title: BAM データを受信する WCF アダプタの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd705c27-5d04-47e5-9bb2-61235f8fe544
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15faf342e5fc947fea236d179f66bd7622e21ebb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390735"
---
# <a name="configuring-the-wcf-adapter-to-intercept-bam-data"></a><span data-ttu-id="f413f-102">BAM データを受信するための WCF アダプタの構成</span><span class="sxs-lookup"><span data-stu-id="f413f-102">Configuring the WCF Adapter to Intercept BAM Data</span></span>
<span data-ttu-id="f413f-103">このセクションでは、BAM WCF インターセプタと連携するように BizTalk WCF アダプタを構成するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="f413f-103">This section contains information about the steps you must take to configure the BizTalk WCF adapter to work with the BAM WCF interceptor.</span></span>  
  
 <span data-ttu-id="f413f-104">基本的な手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f413f-104">The basic steps are as follows:</span></span>  
  
-   <span data-ttu-id="f413f-105">BAM の動作を machine.config ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="f413f-105">Add the BAM behavior to the machine.config file.</span></span>  
  
-   <span data-ttu-id="f413f-106">BizTalk WCF アダプタを作成します。</span><span class="sxs-lookup"><span data-stu-id="f413f-106">Create a BizTalk WCF adapter.</span></span>  
  
-   <span data-ttu-id="f413f-107">BAM WCF インターセプタを構成します。</span><span class="sxs-lookup"><span data-stu-id="f413f-107">Configure the BAM WCF interception.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f413f-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f413f-108">In This Section</span></span>  
  
-   [<span data-ttu-id="f413f-109">BAM インターセプタ動作を Machine.config ファイルに追加する方法</span><span class="sxs-lookup"><span data-stu-id="f413f-109">How to Add the BAM Interceptor Behavior to the Machine.config File</span></span>](../core/how-to-add-the-bam-interceptor-behavior-to-the-machine-config-file.md)  
  
-   [<span data-ttu-id="f413f-110">BizTalk Server の WCF アダプターを作成する方法</span><span class="sxs-lookup"><span data-stu-id="f413f-110">How to Create a WCF Adapter for BizTalk Server</span></span>](../core/how-to-create-a-wcf-adapter-for-biztalk-server.md)  
  
-   [<span data-ttu-id="f413f-111">受信し、BAM WCF 傍受のための送信場所とポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="f413f-111">How to Configure Receive and Send Locations and Ports for BAM WCF Interception</span></span>](../core/how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception.md)  
  
-   [<span data-ttu-id="f413f-112">BAM WCF インターセプションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="f413f-112">How to Configure the BAM WCF Interception</span></span>](../core/how-to-configure-the-bam-wcf-interception.md)  
  
-   [<span data-ttu-id="f413f-113">エラー処理の使用</span><span class="sxs-lookup"><span data-stu-id="f413f-113">Using Fault Handling</span></span>](../core/using-fault-handling.md)