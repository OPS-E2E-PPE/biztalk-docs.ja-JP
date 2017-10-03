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
ms.openlocfilehash: 1d5a543e2fc5db228d249b2db2c445e254384d03
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-msmq-adapter"></a><span data-ttu-id="e89f2-103">MSMQ アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="e89f2-103">What Is the MSMQ Adapter?</span></span>
<span data-ttu-id="e89f2-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MSMQ アダプター (MSMQ アダプター) を Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と共に使用して、Microsoft メッセージ キュー (MSMQ) にメッセージを送受信できます。</span><span class="sxs-lookup"><span data-stu-id="e89f2-104">With the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Adapter for MSMQ (the MSMQ adapter), you can send and receive messages to Microsoft Message Queuing (also known as MSMQ) queues using Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="e89f2-105">MSMQ アダプターは Message Queuing 4.0 をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e89f2-105">The MSMQ adapter supports Message Queuing 4.0.</span></span> <span data-ttu-id="e89f2-106">このアダプターは、トランザクション キューとトランザクション以外のキュー、パブリック キューと専用キュー、およびローカル キューとリモート キューで動作します。</span><span class="sxs-lookup"><span data-stu-id="e89f2-106">The adapter works with transactional and non-transactional, public and private, and local and remote queues.</span></span> <span data-ttu-id="e89f2-107">また、MSMQ アダプターでは、4 MB を超えるサイズの大きいメッセージがサポートされているので、リモート トランザクションの読み込みやサブキューからの読み込みなどのメッセージ キュー 4.0 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e89f2-107">Additionally, the MSMQ adapter provides large (greater than 4 MB) message support and gives you access to Message Queuing 4.0 features such as remote transactional reads and reading from subqueues.</span></span>  
  
 <span data-ttu-id="e89f2-108">BizTalk Server のインストールを [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] にアップグレードしても、MSMQ 用の BizTalk Server 2009 アダプターは削除されません。</span><span class="sxs-lookup"><span data-stu-id="e89f2-108">If you have upgraded your BizTalk Server installation to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], the BizTalk Server 2009 Adapter for MSMQ is not removed.</span></span> <span data-ttu-id="e89f2-109">ただし、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] で新しいバージョンの MSMQ アダプターがインストールされるので、MSMQ 用の BizTalk Server 2009 アダプターは安全にアンインストールできます。アンインストールしたら、このバージョンのアダプターのディレクトリ構造を手動で削除できます。</span><span class="sxs-lookup"><span data-stu-id="e89f2-109">Because [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] installs a new version of the MSMQ adapter, you can safely uninstall the BizTalk Server 2009 Adapter for MSMQ and then manually remove the directory structure for this version of the adapter.</span></span>