---
title: "MSMQ アダプターとは何ですか。 | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, about MSMQ adapters
- MSMQ adapters
ms.assetid: 4f4bfe49-19fc-4195-8826-0329f17cbe94
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: caeac28ce33e2f5eeacbb73b03d9873ec1e74c92
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="what-is-the-msmq-adapter"></a><span data-ttu-id="1d4b4-103">MSMQ アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="1d4b4-103">What Is the MSMQ Adapter?</span></span>
<span data-ttu-id="1d4b4-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MSMQ アダプター (MSMQ アダプター) を Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と共に使用して、Microsoft メッセージ キュー (MSMQ) にメッセージを送受信できます。</span><span class="sxs-lookup"><span data-stu-id="1d4b4-104">With the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Adapter for MSMQ (the MSMQ adapter), you can send and receive messages to Microsoft Message Queuing (also known as MSMQ) queues using Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="1d4b4-105">MSMQ アダプターは Message Queuing 4.0 をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1d4b4-105">The MSMQ adapter supports Message Queuing 4.0.</span></span> <span data-ttu-id="1d4b4-106">このアダプターは、トランザクション キューとトランザクション以外のキュー、パブリック キューと専用キュー、およびローカル キューとリモート キューで動作します。</span><span class="sxs-lookup"><span data-stu-id="1d4b4-106">The adapter works with transactional and non-transactional, public and private, and local and remote queues.</span></span> <span data-ttu-id="1d4b4-107">また、MSMQ アダプターでは、4 MB を超えるサイズの大きいメッセージがサポートされているので、リモート トランザクションの読み込みやサブキューからの読み込みなどのメッセージ キュー 4.0 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1d4b4-107">Additionally, the MSMQ adapter provides large (greater than 4 MB) message support and gives you access to Message Queuing 4.0 features such as remote transactional reads and reading from subqueues.</span></span>  
  
 <span data-ttu-id="1d4b4-108">BizTalk Server 環境を BizTalk Server をアップグレードした場合、MSMQ の BizTalk Server 2009 アダプターは削除されません。</span><span class="sxs-lookup"><span data-stu-id="1d4b4-108">If you have upgraded your BizTalk Server installation to BizTalk Server, the BizTalk Server 2009 Adapter for MSMQ is not removed.</span></span> <span data-ttu-id="1d4b4-109">BizTalk Server では、MSMQ アダプターの新しいバージョンがインストールされる、ため、msmq、BizTalk Server 2009 アダプターを安全にアンインストールし、アダプターのこのバージョンのディレクトリ構造を手動で削除できます。</span><span class="sxs-lookup"><span data-stu-id="1d4b4-109">Because BizTalk Server installs a new version of the MSMQ adapter, you can safely uninstall the BizTalk Server 2009 Adapter for MSMQ and then manually remove the directory structure for this version of the adapter.</span></span>