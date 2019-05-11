---
title: アダプター グループとグループ アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e0a9423-99dd-4474-afa1-fd8e1d074cd1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33cba4d210f79072f5f36a0a47e8546b2d2db265
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361450"
---
# <a name="adapter-groups-and-group-adapters"></a><span data-ttu-id="4bddd-102">アダプター グループとグループ アダプター</span><span class="sxs-lookup"><span data-stu-id="4bddd-102">Adapter Groups and Group Adapters</span></span>
<span data-ttu-id="4bddd-103">*アダプター グループ*を収集して、一連のアダプターの整理に使用できる管理メカニズムです。</span><span class="sxs-lookup"><span data-stu-id="4bddd-103">An *adapter group* is an administration mechanism that you can use to collect and organize a set of adapters.</span></span> <span data-ttu-id="4bddd-104">これに対し、*グループ アダプター*はアダプター グループ内のすべてのアダプター サービスを提供するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="4bddd-104">In contrast, a *group adapter* is a component that services all adapters in an adapter group.</span></span> <span data-ttu-id="4bddd-105">たとえば、アダプターのセットを記述する場合があります TCP/IP 経由でパスワード同期を送信する同じ COM コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="4bddd-105">For example, you might write a set of adapters that all use the same COM component to transmit password synchronizations over TCP/IP.</span></span> <span data-ttu-id="4bddd-106">サービスのすべてのコンポーネントは、グループ アダプターと呼ばれますが、一連のアダプターは、アダプター グループと呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4bddd-106">Your set of adapters is called the adapter group, whereas the component that services them all is called a group adapter.</span></span> <span data-ttu-id="4bddd-107">構成ストアでは、アダプター グループがについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4bddd-107">Adapter groups are described in the configuration store.</span></span> <span data-ttu-id="4bddd-108">使用して、情報と、アダプター グループの更新プログラムを取得することができます`ISSOPSAdapter.ReceiveNotification`します。</span><span class="sxs-lookup"><span data-stu-id="4bddd-108">You can retrieve information and updates on an adapter group by using `ISSOPSAdapter.ReceiveNotification`.</span></span>  
  
 <span data-ttu-id="4bddd-109">グループ アダプターには、アダプター グループと同じ名前があります。</span><span class="sxs-lookup"><span data-stu-id="4bddd-109">A group adapter has the same name as the adapter group.</span></span> <span data-ttu-id="4bddd-110">名前付けの制限、以外は、グループ アダプターは通常のアダプターと同じでもそれ以外の場合。</span><span class="sxs-lookup"><span data-stu-id="4bddd-110">Other than the naming restriction, a group adapter is otherwise identical to a normal adapter.</span></span> <span data-ttu-id="4bddd-111">たとえば、グループ アダプターが、構成ファイルの説明に従って、個別のアクセス グループおよび構成のプロパティを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="4bddd-111">For example, a group adapter can have independent access groups and configuration properties, as described by its configuration file.</span></span> <span data-ttu-id="4bddd-112">グループ アダプターは、アダプター グループに含まれるアダプターと同じコンピューターに最も可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4bddd-112">A group adapter is most likely on the same computer as any adapters in the adapter group.</span></span> <span data-ttu-id="4bddd-113">ただし、これは現在適用されません。</span><span class="sxs-lookup"><span data-stu-id="4bddd-113">However, this is not currently enforced.</span></span> <span data-ttu-id="4bddd-114">同様に、同じコンピューター上に存在する同じアダプター グループ内のすべてのアダプターが期待できます。</span><span class="sxs-lookup"><span data-stu-id="4bddd-114">Likewise, all adapters in the same adapter group can be expected to be on the same computer.</span></span>  
  
 <span data-ttu-id="4bddd-115">使用して`ISSOPSAdapter.InitializeAdapter`、アクセスして、スタートアップ時に、グループ アダプターを初期化します。</span><span class="sxs-lookup"><span data-stu-id="4bddd-115">By using `ISSOPSAdapter.InitializeAdapter`, you can access and initialize a group adapter during startup.</span></span> <span data-ttu-id="4bddd-116">グループ アダプターを初期化するときに、システムは現在のシステムでアダプター グループ内のすべてのアダプターのグループ アダプターに通知します。</span><span class="sxs-lookup"><span data-stu-id="4bddd-116">When you initialize a group adapter, the system informs the group adapter of all adapters in the adapter group on the current system.</span></span> <span data-ttu-id="4bddd-117">さらに、システム通知を送信、グループ アダプターにいつでも、アダプターは追加、削除、有効な場合、または、アダプター グループに無効になっています。</span><span class="sxs-lookup"><span data-stu-id="4bddd-117">In addition, the system sends notifications to the group adapter any time an adapter is added, deleted, enabled, or disabled in the adapter group.</span></span> <span data-ttu-id="4bddd-118">ただし、グループ アダプターはパスワード変更通知を受信しません。</span><span class="sxs-lookup"><span data-stu-id="4bddd-118">However, the group adapter does not receive any password change notifications.</span></span>  
  
 <span data-ttu-id="4bddd-119">アダプター グループとグループ アダプターは、管理ツールを使用して省略可能です。</span><span class="sxs-lookup"><span data-stu-id="4bddd-119">Adapter groups and group adapters are optional using the Administration tool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bddd-120">参照</span><span class="sxs-lookup"><span data-stu-id="4bddd-120">See Also</span></span>  
 [<span data-ttu-id="4bddd-121">パスワード同期アダプター</span><span class="sxs-lookup"><span data-stu-id="4bddd-121">Password Sync Adapters</span></span>](../core/password-sync-adapters.md)