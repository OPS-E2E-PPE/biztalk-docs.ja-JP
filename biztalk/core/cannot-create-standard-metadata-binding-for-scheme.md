---
title: "スキームの標準メタデータ バインドを作成することはできません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce441c3e-0f6e-46ed-90cf-825dbf89d910
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3228da0dfee18581c5fa8105ce3dd480380cc034
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="cannot-create-standard-metadata-binding-for-scheme"></a><span data-ttu-id="ecf25-102">スキームの標準メタデータ バインドを作成できません</span><span class="sxs-lookup"><span data-stu-id="ecf25-102">Cannot create standard metadata binding for scheme</span></span>
## <a name="details"></a><span data-ttu-id="ecf25-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ecf25-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ecf25-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ecf25-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ecf25-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ecf25-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="ecf25-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ecf25-106">Event ID</span></span>|<span data-ttu-id="ecf25-107">0</span><span class="sxs-lookup"><span data-stu-id="ecf25-107">0</span></span>|  
|<span data-ttu-id="ecf25-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ecf25-108">Event Source</span></span>|<span data-ttu-id="ecf25-109">0</span><span class="sxs-lookup"><span data-stu-id="ecf25-109">0</span></span>|  
|<span data-ttu-id="ecf25-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ecf25-110">Component</span></span>|<span data-ttu-id="ecf25-111">0</span><span class="sxs-lookup"><span data-stu-id="ecf25-111">0</span></span>|  
|<span data-ttu-id="ecf25-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ecf25-112">Symbolic Name</span></span>|<span data-ttu-id="ecf25-113">0</span><span class="sxs-lookup"><span data-stu-id="ecf25-113">0</span></span>|  
|<span data-ttu-id="ecf25-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ecf25-114">Message Text</span></span>|<span data-ttu-id="ecf25-115">スキーム "{0}" の標準メタデータ バインドを作成できません。</span><span class="sxs-lookup"><span data-stu-id="ecf25-115">Cannot create standard metadata binding for scheme "{0}".</span></span> <span data-ttu-id="ecf25-116">サポートされているスキームは、http、https、net.pipe、および net.tcp です。</span><span class="sxs-lookup"><span data-stu-id="ecf25-116">Supported schemes are http, https, net.pipe, and net.tcp</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ecf25-117">説明</span><span class="sxs-lookup"><span data-stu-id="ecf25-117">Explanation</span></span>  
 <span data-ttu-id="ecf25-118">このエラーは、使用するメタデータのサービスは、サポートされたスキームではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="ecf25-118">This error indicates the service from which the metadata is trying to be consumed is not a supported scheme.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ecf25-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ecf25-119">User Action</span></span>  
 <span data-ttu-id="ecf25-120">有効なスキームでメタデータを公開し、新しいメタデータの場所に対して、ウィザードをもう一度実行します。</span><span class="sxs-lookup"><span data-stu-id="ecf25-120">Publish the metadata with a valid scheme and then run the wizard again, against the new metadata location.</span></span>  
  
 <span data-ttu-id="ecf25-121">アダプターおよびバインドの詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプで次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecf25-121">For additional information on adapters and binding, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="ecf25-122">WCF アダプタ</span><span class="sxs-lookup"><span data-stu-id="ecf25-122">WCF Adapters</span></span>](../core/wcf-adapters.md)