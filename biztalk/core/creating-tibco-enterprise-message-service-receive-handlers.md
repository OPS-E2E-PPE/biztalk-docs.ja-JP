---
title: "TIBCO Enterprise Message Service を作成する受信ハンドラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: receive handlers
ms.assetid: e1307e3c-0237-4f19-a642-58e694fe95d0
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83163701f897b782d577351cd08b3f2650ae6fb0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-tibco-enterprise-message-service-receive-handlers"></a><span data-ttu-id="d5528-102">TIBCO Enterprise Message Service 受信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="d5528-102">Creating TIBCO Enterprise Message Service Receive Handlers</span></span>
<span data-ttu-id="d5528-103">TIBCO Enterprise Message Service の受信元は、特定のキューまたはトピックを登録して関連メッセージを受信するリスナー サービスです。</span><span class="sxs-lookup"><span data-stu-id="d5528-103">TIBCO Enterprise Message Service receiver is a listener service that registers a particular Queue or Topic and receives the relative messages.</span></span> <span data-ttu-id="d5528-104">BizTalk Adapter for TIBCO Enterprise Message Service は、新しいセッションを開いて、最初に TIBCO Enterprise Message Service を登録し、その後、メッセージを受信するためにポーリングを継続します。</span><span class="sxs-lookup"><span data-stu-id="d5528-104">BizTalk Adapter for TIBCO Enterprise Message Service first registers with TIBCO Enterprise Message Service by opening a new session, and then it continues polling to receive messages..</span></span> <span data-ttu-id="d5528-105">このセクションでは、TIBCO Enterprise Message Service に接続するために受信ポートを設定する方法と、実行時に TIBCO EMS と対話するためにオーケストレーションに XML を含める方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d5528-105">This section explains how to set the receive port to connect to TIBCO Enterprise Message Service and how to include XML in your orchestration to interact with TIBCO EMS at run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5528-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d5528-106">In This Section</span></span>  
  
-   [<span data-ttu-id="d5528-107">作成する方法には、TIBCO Enterprise Message Service 受信ポート</span><span class="sxs-lookup"><span data-stu-id="d5528-107">How to Create Receive Ports in TIBCO Enterprise Message Service</span></span>](../core/how-to-create-receive-ports-in-tibco-enterprise-message-service.md)  
  
-   [<span data-ttu-id="d5528-108">TIBCO Enterprise Message Service トランスポート プロパティの設定、受信ポート</span><span class="sxs-lookup"><span data-stu-id="d5528-108">Setting TIBCO Enterprise Message Service Transport Properties for the Receive Port</span></span>](../core/set-tibco-enterprise-message-service-transport-properties-for-the-receive-port.md)  
  
-   [<span data-ttu-id="d5528-109">設定する方法 TIBCO Enterprise Message Service 用の受信パイプライン</span><span class="sxs-lookup"><span data-stu-id="d5528-109">How to Set Receive Pipelines for TIBCO Enterprise Message Service</span></span>](../core/how-to-set-receive-pipelines-for-tibco-enterprise-message-service.md)