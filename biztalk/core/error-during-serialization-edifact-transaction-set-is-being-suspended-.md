---
title: "Edifact トランザクション セットがインターチェンジのエラーに含まれている |Microsoft ドキュメント"
description: "シリアル化中にエラーが発生しました。 インターチェンジに含まれる EDIFACT トランザクション セット (グループ以外) が、次のエラーで中断されています"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a0a33ac-d83e-495c-ba75-88c15ad7cfcd
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67f089e49941ffec7d3392b3bc35edcbc4eefec5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="edifact-transaction-set-is-suspended-error-and-details"></a><span data-ttu-id="c198a-104">Edifact トランザクション セットは、中断されたエラーの詳細</span><span class="sxs-lookup"><span data-stu-id="c198a-104">Edifact transaction set is suspended error and details</span></span>

`Error encountered during serialization. The Edifact transaction set contained in interchange (without group) is being suspended with following errors`

## <a name="details"></a><span data-ttu-id="c198a-105">詳細</span><span class="sxs-lookup"><span data-stu-id="c198a-105">Details</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="c198a-106">製品名</span><span class="sxs-lookup"><span data-stu-id="c198a-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="c198a-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c198a-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="c198a-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c198a-108">Event ID</span></span>|-|  
|<span data-ttu-id="c198a-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c198a-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c198a-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="c198a-110"> EDI</span></span>|  
|<span data-ttu-id="c198a-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c198a-111">Component</span></span>|<span data-ttu-id="c198a-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="c198a-112">EDI Engine</span></span>|  
|<span data-ttu-id="c198a-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c198a-113">Symbolic Name</span></span>|<span data-ttu-id="c198a-114">EfactTransactionSetSendErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="c198a-114">EfactTransactionSetSendErrorWithoutGroup</span></span>|  
|<span data-ttu-id="c198a-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c198a-115">Message Text</span></span>|<span data-ttu-id="c198a-116">シリアル化中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c198a-116">Error encountered during serialization.</span></span> <span data-ttu-id="c198a-117">Edifact トランザクション セット id '{0}' id '{1}'、送信者 id '{2}' を持つ (グループなしの) インターチェンジに含まれている受信者 id '{3}' で中断されていますが次のエラー。</span><span class="sxs-lookup"><span data-stu-id="c198a-117">The Edifact transaction set with id '{0}' contained in interchange (without group)  with id '{1}', with sender id '{2}', receiver id '{3}' is being suspended with following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c198a-118">説明</span><span class="sxs-lookup"><span data-stu-id="c198a-118">Explanation</span></span>  
 <span data-ttu-id="c198a-119">このエラー/警告/情報イベントは、識別されたトランザクション セットに、示されたエラーがあったため、EDIFACT の送信インターチェンジのシリアル化中に EDI 送信パイプラインでエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="c198a-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified transaction set.</span></span> <span data-ttu-id="c198a-120">このトランザクション セットは、インターチェンジ内のグループには含まれないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c198a-120">Note that the transaction set is not in a group in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c198a-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c198a-121">User Action</span></span>  
 <span data-ttu-id="c198a-122">このエラーを解決するには、情報を使用して、エラー メッセージに、トランザクション セットでエラーを特定し、問題の解決方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="c198a-122">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution.</span></span>