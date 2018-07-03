---
title: スキームの標準メタデータ バインドを作成することはできません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce441c3e-0f6e-46ed-90cf-825dbf89d910
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fd4a91535c7872bb5be7328755808eb91758db6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989315"
---
# <a name="cannot-create-standard-metadata-binding-for-scheme"></a><span data-ttu-id="c66e8-102">スキームの標準メタデータ バインドを作成できません</span><span class="sxs-lookup"><span data-stu-id="c66e8-102">Cannot create standard metadata binding for scheme</span></span>
## <a name="details"></a><span data-ttu-id="c66e8-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c66e8-103">Details</span></span>  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c66e8-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c66e8-104">Product Name</span></span>   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| <span data-ttu-id="c66e8-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c66e8-105">Product Version</span></span> |                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                             |
|    <span data-ttu-id="c66e8-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c66e8-106">Event ID</span></span>     |                                                         <span data-ttu-id="c66e8-107">0</span><span class="sxs-lookup"><span data-stu-id="c66e8-107">0</span></span>                                                          |
|  <span data-ttu-id="c66e8-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c66e8-108">Event Source</span></span>   |                                                         <span data-ttu-id="c66e8-109">0</span><span class="sxs-lookup"><span data-stu-id="c66e8-109">0</span></span>                                                          |
|    <span data-ttu-id="c66e8-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c66e8-110">Component</span></span>    |                                                         <span data-ttu-id="c66e8-111">0</span><span class="sxs-lookup"><span data-stu-id="c66e8-111">0</span></span>                                                          |
|  <span data-ttu-id="c66e8-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c66e8-112">Symbolic Name</span></span>  |                                                         <span data-ttu-id="c66e8-113">0</span><span class="sxs-lookup"><span data-stu-id="c66e8-113">0</span></span>                                                          |
|  <span data-ttu-id="c66e8-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c66e8-114">Message Text</span></span>   | <span data-ttu-id="c66e8-115">スキームの標準メタデータ バインドを作成することはできません"{0}"。</span><span class="sxs-lookup"><span data-stu-id="c66e8-115">Cannot create standard metadata binding for scheme "{0}".</span></span> <span data-ttu-id="c66e8-116">サポートされているスキームは、http、https、net.pipe、および net.tcp です。</span><span class="sxs-lookup"><span data-stu-id="c66e8-116">Supported schemes are http, https, net.pipe, and net.tcp</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c66e8-117">説明</span><span class="sxs-lookup"><span data-stu-id="c66e8-117">Explanation</span></span>  
 <span data-ttu-id="c66e8-118">このエラーは、使用するメタデータのサービスは、サポートされたスキームではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="c66e8-118">This error indicates the service from which the metadata is trying to be consumed is not a supported scheme.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c66e8-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c66e8-119">User Action</span></span>  
 <span data-ttu-id="c66e8-120">有効なスキームでメタデータを公開し、新しいメタデータの場所に対して、ウィザードをもう一度実行します。</span><span class="sxs-lookup"><span data-stu-id="c66e8-120">Publish the metadata with a valid scheme and then run the wizard again, against the new metadata location.</span></span>  
  
 <span data-ttu-id="c66e8-121">アダプターおよびバインドの詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプで次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c66e8-121">For additional information on adapters and binding, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="c66e8-122">WCF アダプター</span><span class="sxs-lookup"><span data-stu-id="c66e8-122">WCF Adapters</span></span>](../core/wcf-adapters.md)