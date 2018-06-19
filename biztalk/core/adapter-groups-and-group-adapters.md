---
title: アダプター グループとグループ アダプター |Microsoft ドキュメント
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
ms.openlocfilehash: fcf10f50857026893245cc567783b649f614c4f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225378"
---
# <a name="adapter-groups-and-group-adapters"></a><span data-ttu-id="70837-102">アダプター グループとグループ アダプター</span><span class="sxs-lookup"><span data-stu-id="70837-102">Adapter Groups and Group Adapters</span></span>
<span data-ttu-id="70837-103">*アダプター グループ*収集、整理、一連のアダプターに使用できる管理メカニズムです。</span><span class="sxs-lookup"><span data-stu-id="70837-103">An *adapter group* is an administration mechanism that you can use to collect and organize a set of adapters.</span></span> <span data-ttu-id="70837-104">これに対し、*グループ アダプター*コンポーネント サービスのアダプター グループ内のすべてのアダプターです。</span><span class="sxs-lookup"><span data-stu-id="70837-104">In contrast, a *group adapter* is a component that services all adapters in an adapter group.</span></span> <span data-ttu-id="70837-105">たとえば、同じ COM コンポーネントを使用して、TCP/IP 経由でパスワード同期処理を行う複数のアダプターを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="70837-105">For example, you might write a set of adapters that all use the same COM component to transmit password synchronizations over TCP/IP.</span></span> <span data-ttu-id="70837-106">こうした一連のアダプターをアダプター グループと呼び、また、これらすべてのアダプターにサービスを提供するコンポーネントをグループ アダプターと呼びます。</span><span class="sxs-lookup"><span data-stu-id="70837-106">Your set of adapters is called the adapter group, whereas the component that services them all is called a group adapter.</span></span> <span data-ttu-id="70837-107">アダプター グループは、構成ストアで定義されます。</span><span class="sxs-lookup"><span data-stu-id="70837-107">Adapter groups are described in the configuration store.</span></span> <span data-ttu-id="70837-108">アダプター グループに関する情報 (更新情報を含む) は、`ISSOPSAdapter.ReceiveNotification` を使って取得できます。</span><span class="sxs-lookup"><span data-stu-id="70837-108">You can retrieve information and updates on an adapter group by using `ISSOPSAdapter.ReceiveNotification`.</span></span>  
  
 <span data-ttu-id="70837-109">グループ アダプターには、アダプター グループと同じ名前が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="70837-109">A group adapter has the same name as the adapter group.</span></span> <span data-ttu-id="70837-110">名前付けの制限を除けば、グループ アダプターも通常のアダプターと同じです。</span><span class="sxs-lookup"><span data-stu-id="70837-110">Other than the naming restriction, a group adapter is otherwise identical to a normal adapter.</span></span> <span data-ttu-id="70837-111">たとえば、グループ アダプターには、構成ファイルの定義により、個別のアクセス グループおよび構成プロパティを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="70837-111">For example, a group adapter can have independent access groups and configuration properties, as described by its configuration file.</span></span> <span data-ttu-id="70837-112">通常、グループ アダプターは、アダプター グループに含まれるアダプターと同じコンピューターに配置されます。</span><span class="sxs-lookup"><span data-stu-id="70837-112">A group adapter is most likely on the same computer as any adapters in the adapter group.</span></span> <span data-ttu-id="70837-113">ただし、現時点では、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="70837-113">However, this is not currently enforced.</span></span> <span data-ttu-id="70837-114">同様に、同じアダプター グループ内のすべてのアダプターは、同じコンピューターに配置されるのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="70837-114">Likewise, all adapters in the same adapter group can be expected to be on the same computer.</span></span>  
  
 <span data-ttu-id="70837-115">グループ アダプターは、`ISSOPSAdapter.InitializeAdapter` を使って起動時にアクセスおよび初期化できます。</span><span class="sxs-lookup"><span data-stu-id="70837-115">By using `ISSOPSAdapter.InitializeAdapter`, you can access and initialize a group adapter during startup.</span></span> <span data-ttu-id="70837-116">グループ アダプターを初期化すると、現在のシステム上に配置されている、アダプター グループ内のすべてのアダプターに関する情報が、グループ アダプターに対して通知されます。</span><span class="sxs-lookup"><span data-stu-id="70837-116">When you initialize a group adapter, the system informs the group adapter of all adapters in the adapter group on the current system.</span></span> <span data-ttu-id="70837-117">また、アダプター グループ内のアダプターに変更 (追加、削除、有効化、無効化) が生じると、常にグループ アダプターに対して通知が送られます。</span><span class="sxs-lookup"><span data-stu-id="70837-117">In addition, the system sends notifications to the group adapter any time an adapter is added, deleted, enabled, or disabled in the adapter group.</span></span> <span data-ttu-id="70837-118">ただし、グループ アダプターがパスワード変更通知を受け取ることはありません。</span><span class="sxs-lookup"><span data-stu-id="70837-118">However, the group adapter does not receive any password change notifications.</span></span>  
  
 <span data-ttu-id="70837-119">管理ツールでは、アダプター グループおよびグループ アダプターはオプションとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="70837-119">Adapter groups and group adapters are optional using the Administration tool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70837-120">参照</span><span class="sxs-lookup"><span data-stu-id="70837-120">See Also</span></span>  
 [<span data-ttu-id="70837-121">パスワード同期アダプター</span><span class="sxs-lookup"><span data-stu-id="70837-121">Password Sync Adapters</span></span>](../core/password-sync-adapters.md)