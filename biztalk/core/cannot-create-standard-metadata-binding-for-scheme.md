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
ms.openlocfilehash: d45e8e983e626db3b48c4875573fd7e3a92d50e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357650"
---
# <a name="cannot-create-standard-metadata-binding-for-scheme"></a><span data-ttu-id="798f6-102">スキームの標準メタデータ バインドを作成できません</span><span class="sxs-lookup"><span data-stu-id="798f6-102">Cannot create standard metadata binding for scheme</span></span>
## <a name="details"></a><span data-ttu-id="798f6-103">詳細</span><span class="sxs-lookup"><span data-stu-id="798f6-103">Details</span></span>  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="798f6-104">製品名</span><span class="sxs-lookup"><span data-stu-id="798f6-104">Product Name</span></span>   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| <span data-ttu-id="798f6-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="798f6-105">Product Version</span></span> |                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                             |
|    <span data-ttu-id="798f6-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="798f6-106">Event ID</span></span>     |                                                         <span data-ttu-id="798f6-107">0</span><span class="sxs-lookup"><span data-stu-id="798f6-107">0</span></span>                                                          |
|  <span data-ttu-id="798f6-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="798f6-108">Event Source</span></span>   |                                                         <span data-ttu-id="798f6-109">0</span><span class="sxs-lookup"><span data-stu-id="798f6-109">0</span></span>                                                          |
|    <span data-ttu-id="798f6-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="798f6-110">Component</span></span>    |                                                         <span data-ttu-id="798f6-111">0</span><span class="sxs-lookup"><span data-stu-id="798f6-111">0</span></span>                                                          |
|  <span data-ttu-id="798f6-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="798f6-112">Symbolic Name</span></span>  |                                                         <span data-ttu-id="798f6-113">0</span><span class="sxs-lookup"><span data-stu-id="798f6-113">0</span></span>                                                          |
|  <span data-ttu-id="798f6-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="798f6-114">Message Text</span></span>   | <span data-ttu-id="798f6-115">スキームの標準メタデータ バインドを作成することはできません"{0}"。</span><span class="sxs-lookup"><span data-stu-id="798f6-115">Cannot create standard metadata binding for scheme "{0}".</span></span> <span data-ttu-id="798f6-116">サポートされているスキームは http、https、net.pipe、および net.tcp です。</span><span class="sxs-lookup"><span data-stu-id="798f6-116">Supported schemes are http, https, net.pipe, and net.tcp</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="798f6-117">説明</span><span class="sxs-lookup"><span data-stu-id="798f6-117">Explanation</span></span>  
 <span data-ttu-id="798f6-118">このエラーは、メタデータが使用しようとするサービスがサポートされているスキームを示します。</span><span class="sxs-lookup"><span data-stu-id="798f6-118">This error indicates the service from which the metadata is trying to be consumed is not a supported scheme.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="798f6-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="798f6-119">User Action</span></span>  
 <span data-ttu-id="798f6-120">有効なスキームでメタデータを公開し、新しいメタデータの場所に対して、もう一度ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="798f6-120">Publish the metadata with a valid scheme and then run the wizard again, against the new metadata location.</span></span>  
  
 <span data-ttu-id="798f6-121">アダプターとバインドする方法の詳細についてで次の情報を参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="798f6-121">For additional information on adapters and binding, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="798f6-122">WCF アダプター</span><span class="sxs-lookup"><span data-stu-id="798f6-122">WCF Adapters</span></span>](../core/wcf-adapters.md)