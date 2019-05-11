---
title: アダプター ハンドラーとは何ですか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- handlers [adapters]
- adapters, handlers
- handlers [adapters], about handlers
ms.assetid: 4d1afa39-6320-467f-a7e8-f5f18236648e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09ef44c037b175497dfb6c1fb30ea9dd9fb0a43d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379690"
---
# <a name="what-is-an-adapter-handler"></a><span data-ttu-id="d4071-103">アダプター ハンドラーとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="d4071-103">What Is an Adapter Handler?</span></span>
<span data-ttu-id="d4071-104">アダプター ハンドラーは、アダプター コードを実行する BizTalk ホストのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="d4071-104">An adapter handler is an instance of a BizTalk host in which the adapter code runs.</span></span> <span data-ttu-id="d4071-105">指定の送信または受信アダプターのハンドラーをするときに、アダプター コードのコンテキストで実行するホスト インスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4071-105">When you specify a send or receive handler for an adapter you are specifying which host instance the adapter code will run in the context of.</span></span> <span data-ttu-id="d4071-106">アダプター ハンドラーは、アダプタを実行し、アダプターの特定のインスタンスのプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d4071-106">An adapter handler is responsible for executing the adapter and contains properties for a specific instance of an adapter.</span></span> <span data-ttu-id="d4071-107">既定の BizTalk Server の構成がインストールされているアダプターのすべてのアダプター ハンドラーを作成しますが、負荷分散のための追加のアダプタ ハンドラを作成するかを特定のアダプター ハンドラーのプロセスの分離を提供することがあります。</span><span class="sxs-lookup"><span data-stu-id="d4071-107">A default BizTalk Server configuration will create adapter handlers for all of the installed adapters, but you may want to create additional adapter handlers for purposes of load balancing or to provide process isolation for a particular adapter handler.</span></span>  
  
 <span data-ttu-id="d4071-108">アダプター ハンドラーは、BizTalk ホスト インスタンスにバインドされ、BizTalk ホスト インスタンスが BizTalk server にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="d4071-108">Adapter handlers are bound to a BizTalk Host instance, and BizTalk Host instances are bound to a BizTalk server.</span></span> <span data-ttu-id="d4071-109">そのため、負荷分散アダプターが BizTalk サーバー間で処理する場合、BizTalk グループに別の BizTalk server を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4071-109">Therefore, you must add additional BizTalk servers to your BizTalk group if you want to load balance adapter processing across BizTalk servers.</span></span> <span data-ttu-id="d4071-110">プロセスの分離するために、追加のアダプタ ハンドラを作成する場合、BizTalk グループに BizTalk server を追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d4071-110">You do not need to add additional BizTalk servers to your BizTalk group if you are creating additional adapter handlers for the purpose of process isolation.</span></span>  
  
 <span data-ttu-id="d4071-111">アダプター ハンドラーを実行する新しいホスト インスタンスを作成する必要がある場合は、まずホストを作成し、BizTalk server のいずれかで実行するには、そのホストのインスタンスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4071-111">If you need to create a new host instance to run an adapter handler in, you must first create a host and then create an instance of that host to run on one of your BizTalk servers.</span></span> <span data-ttu-id="d4071-112">詳細については、次を参照してください。[新しいホストを作成する方法](../core/how-to-create-a-new-host.md)と[ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md)します。</span><span class="sxs-lookup"><span data-stu-id="d4071-112">For more information, see [How to Create a New Host](../core/how-to-create-a-new-host.md) and [How to Add a Host Instance](../core/how-to-add-a-host-instance.md).</span></span>  
  
 <span data-ttu-id="d4071-113">HTTP および SOAP アダプターの受信ハンドラーを除くすべてのアダプター ハンドラーは、インプロセス ホストで実行するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4071-113">All adapter handlers except for HTTP and SOAP adapter receive handlers must be configured to run in an in-process host.</span></span> <span data-ttu-id="d4071-114">HTTP および SOAP アダプターの受信ハンドラー、分離ホストでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="d4071-114">HTTP and SOAP adapter receive handlers can only be run in an isolated host.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4071-115">参照</span><span class="sxs-lookup"><span data-stu-id="d4071-115">See Also</span></span>  
 [<span data-ttu-id="d4071-116">アダプター ハンドラーの作成と削除</span><span class="sxs-lookup"><span data-stu-id="d4071-116">Creating and Deleting Adapter Handlers</span></span>](../core/creating-and-deleting-adapter-handlers.md)