---
title: "MSMQ アダプター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: MSMQ adapters
ms.assetid: 2602753b-4eaf-41b3-87bf-c9429cd3cfe1
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 248c9cbbdbf5af2ff1336b3ea4a51894b472e992
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="msmq-adapter"></a><span data-ttu-id="9d33b-102">MSMQ アダプター</span><span class="sxs-lookup"><span data-stu-id="9d33b-102">MSMQ Adapter</span></span>
<span data-ttu-id="9d33b-103">MSMQ アダプターでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] からメッセージキュー 4.0 を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9d33b-103">The MSMQ adapter lets you use Message Queuing 4.0 from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="9d33b-104">メッセージ キュー テクノロジを BizTalk Server と統合すると、一時的にオフラインになる可能性がある異種ネットワークやシステムを経由して、それぞれ別の時間に実行されるアプリケーションどうしがやりとりできるようになります。</span><span class="sxs-lookup"><span data-stu-id="9d33b-104">Integrating Message Queuing technology with BizTalk Server enables applications that are running at different times to communicate across heterogeneous networks and systems that may be temporarily offline.</span></span>  
  
 <span data-ttu-id="9d33b-105">MSMQ アダプター機能には次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="9d33b-105">The MSMQ adapter features include the following:</span></span>  
  
-   <span data-ttu-id="9d33b-106">パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="9d33b-106">Improved performance</span></span>  
  
-   <span data-ttu-id="9d33b-107">マルチスレッド操作のサポート</span><span class="sxs-lookup"><span data-stu-id="9d33b-107">Support for multithreaded operations</span></span>  
  
-   <span data-ttu-id="9d33b-108">メッセージ キュー 4.0 機能のサポート。リモートのトランザクションの読み込み、およびサブキューからの受信を含みます (メッセージ キュー 4.0 で利用可能)。</span><span class="sxs-lookup"><span data-stu-id="9d33b-108">Support for Message Queuing 4.0 features, including support for remote transactional reads and receiving from subqueues (available with Message Queuing 4.0).</span></span>  
  
-   <span data-ttu-id="9d33b-109">4 MB を超えるメッセージ処理のサポート</span><span class="sxs-lookup"><span data-stu-id="9d33b-109">Support for processing messages larger than 4 MB</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9d33b-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9d33b-110">In This Section</span></span>  
  
-   [<span data-ttu-id="9d33b-111">MSMQ アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="9d33b-111">What Is the MSMQ Adapter?</span></span>](../core/what-is-the-msmq-adapter.md)  
  
-   [<span data-ttu-id="9d33b-112">MSMQ アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="9d33b-112">MSMQ Adapter Architecture</span></span>](../core/msmq-adapter-architecture.md)  
  
-   [<span data-ttu-id="9d33b-113">MSMQ アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="9d33b-113">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)  
  
-   [<span data-ttu-id="9d33b-114">MSMQ アダプターで信頼できるメッセージング</span><span class="sxs-lookup"><span data-stu-id="9d33b-114">Reliable Messaging with the MSMQ Adapter</span></span>](../core/reliable-messaging-with-the-msmq-adapter.md)  
  
-   [<span data-ttu-id="9d33b-115">MSMQ アダプター プロパティ スキーマおよびプロパティ</span><span class="sxs-lookup"><span data-stu-id="9d33b-115">MSMQ Adapter Property Schema and Properties</span></span>](../core/msmq-adapter-property-schema-and-properties.md)  
  
-   [<span data-ttu-id="9d33b-116">MSMQ アダプターでメッセージの配信を順序付け</span><span class="sxs-lookup"><span data-stu-id="9d33b-116">Ordered Delivery of Messages with the MSMQ Adapter</span></span>](../core/ordered-delivery-of-messages-with-the-msmq-adapter.md)  
  
-   [<span data-ttu-id="9d33b-117">MSMQ での LoadGen 2007 の使用</span><span class="sxs-lookup"><span data-stu-id="9d33b-117">Using LoadGen 2007 with MSMQ</span></span>](../core/using-loadgen-2007-with-msmq.md)