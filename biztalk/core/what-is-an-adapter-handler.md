---
title: アダプタ ハンドラについて | Microsoft Docs
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
ms.openlocfilehash: 7c8a1b60661427776dd4e35ffce27bf120bf94a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289306"
---
# <a name="what-is-an-adapter-handler"></a><span data-ttu-id="687a7-103">アダプタ ハンドラについて</span><span class="sxs-lookup"><span data-stu-id="687a7-103">What Is an Adapter Handler?</span></span>
<span data-ttu-id="687a7-104">アダプタ ハンドラとは、アダプタ コードを実行する BizTalk ホストのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="687a7-104">An adapter handler is an instance of a BizTalk host in which the adapter code runs.</span></span> <span data-ttu-id="687a7-105">アダプタの送信ハンドラまたは受信ハンドラを指定するとき、アダプタ コードが実行されるコンテキストとなるホスト インスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="687a7-105">When you specify a send or receive handler for an adapter you are specifying which host instance the adapter code will run in the context of.</span></span> <span data-ttu-id="687a7-106">アダプタ ハンドラには、アダプタを実行する役割があり、アダプタの特定のインスタンスのプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="687a7-106">An adapter handler is responsible for executing the adapter and contains properties for a specific instance of an adapter.</span></span> <span data-ttu-id="687a7-107">既定の BizTalk Server 構成では、インストールされているすべてのアダプタに対してアダプタ ハンドラが作成されますが、特定のアダプタ ハンドラへの負荷分散やプロセス分離のために、追加のアダプタ ハンドラを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="687a7-107">A default BizTalk Server configuration will create adapter handlers for all of the installed adapters, but you may want to create additional adapter handlers for purposes of load balancing or to provide process isolation for a particular adapter handler.</span></span>  
  
 <span data-ttu-id="687a7-108">アダプタ ハンドラは BizTalk ホスト インスタンスにバインドされ、BizTalk ホスト インスタンスは BizTalk Server にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="687a7-108">Adapter handlers are bound to a BizTalk Host instance, and BizTalk Host instances are bound to a BizTalk server.</span></span> <span data-ttu-id="687a7-109">そのため、アダプタの処理の負荷を複数の BizTalk Server 間で分散する場合は、別の BizTalk Server を BizTalk グループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="687a7-109">Therefore, you must add additional BizTalk servers to your BizTalk group if you want to load balance adapter processing across BizTalk servers.</span></span> <span data-ttu-id="687a7-110">プロセス分離のために追加のアダプタ ハンドラを作成する場合は、BizTalk グループに BizTalk Server を追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="687a7-110">You do not need to add additional BizTalk servers to your BizTalk group if you are creating additional adapter handlers for the purpose of process isolation.</span></span>  
  
 <span data-ttu-id="687a7-111">アダプタ ハンドラを実行する新しいホスト インスタンスを作成する場合は、最初にホストを作成してから、BizTalk Server のいずれかで実行する、そのホストのインスタンスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="687a7-111">If you need to create a new host instance to run an adapter handler in, you must first create a host and then create an instance of that host to run on one of your BizTalk servers.</span></span> <span data-ttu-id="687a7-112">詳細については、次を参照してください。[を新しいホストを作成する方法](../core/how-to-create-a-new-host.md)と[ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md)です。</span><span class="sxs-lookup"><span data-stu-id="687a7-112">For more information, see [How to Create a New Host](../core/how-to-create-a-new-host.md) and [How to Add a Host Instance](../core/how-to-add-a-host-instance.md).</span></span>  
  
 <span data-ttu-id="687a7-113">HTTP アダプタおよび SOAP アダプタの受信ハンドラを除くすべてのアダプタ ハンドラは、インプロセス ホストで実行されるように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="687a7-113">All adapter handlers except for HTTP and SOAP adapter receive handlers must be configured to run in an in-process host.</span></span> <span data-ttu-id="687a7-114">HTTP アダプタおよび SOAP アダプタの受信ハンドラは分離ホストでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="687a7-114">HTTP and SOAP adapter receive handlers can only be run in an isolated host.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="687a7-115">参照</span><span class="sxs-lookup"><span data-stu-id="687a7-115">See Also</span></span>  
 [<span data-ttu-id="687a7-116">作成して、アダプター ハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="687a7-116">Creating and Deleting Adapter Handlers</span></span>](../core/creating-and-deleting-adapter-handlers.md)