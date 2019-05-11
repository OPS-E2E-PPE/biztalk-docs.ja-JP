---
title: Edifact トランザクション セットに含まれるインターチェンジ エラー |Microsoft Docs
description: シリアル化中に発生したエラーです。 Edifact トランザクション セット (グループ) なしのインターチェンジに含まれるは、次のエラーで中断されています
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a0a33ac-d83e-495c-ba75-88c15ad7cfcd
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 368b5ad0f26b642d4d7f3575a8c7a03abac4ca0c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389200"
---
# <a name="edifact-transaction-set-is-suspended-error-and-details"></a><span data-ttu-id="e7fa5-104">Edifact トランザクション セットが中断されたエラーと詳細</span><span class="sxs-lookup"><span data-stu-id="e7fa5-104">Edifact transaction set is suspended error and details</span></span>

`Error encountered during serialization. The Edifact transaction set contained in interchange (without group) is being suspended with following errors`

## <a name="details"></a><span data-ttu-id="e7fa5-105">詳細</span><span class="sxs-lookup"><span data-stu-id="e7fa5-105">Details</span></span>  
  
|                 |                                                                                                                                                                                                                              |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e7fa5-106">製品名</span><span class="sxs-lookup"><span data-stu-id="e7fa5-106">Product Name</span></span>   |                                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                      |
| <span data-ttu-id="e7fa5-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e7fa5-107">Product Version</span></span> |                                                                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                  |
|    <span data-ttu-id="e7fa5-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e7fa5-108">Event ID</span></span>     |                                                                                                              -                                                                                                               |
|  <span data-ttu-id="e7fa5-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e7fa5-109">Event Source</span></span>   |                                                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="e7fa5-110">EDI</span><span class="sxs-lookup"><span data-stu-id="e7fa5-110">EDI</span></span>                                                                    |
|    <span data-ttu-id="e7fa5-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e7fa5-111">Component</span></span>    |                                                                                                          <span data-ttu-id="e7fa5-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="e7fa5-112">EDI Engine</span></span>                                                                                                          |
|  <span data-ttu-id="e7fa5-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e7fa5-113">Symbolic Name</span></span>  |                                                                                           <span data-ttu-id="e7fa5-114">EfactTransactionSetSendErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="e7fa5-114">EfactTransactionSetSendErrorWithoutGroup</span></span>                                                                                           |
|  <span data-ttu-id="e7fa5-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e7fa5-115">Message Text</span></span>   | <span data-ttu-id="e7fa5-116">シリアル化中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="e7fa5-116">Error encountered during serialization.</span></span> <span data-ttu-id="e7fa5-117">Edifact トランザクション セット id を持つ '{0}'id (グループ) なしのインターチェンジに含まれる'{1}'、送信者 id'{2}'、受信者 id '{3}' 次のエラーで中断されています。</span><span class="sxs-lookup"><span data-stu-id="e7fa5-117">The Edifact transaction set with id '{0}' contained in interchange (without group)  with id '{1}', with sender id '{2}', receiver id '{3}' is being suspended with following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e7fa5-118">説明</span><span class="sxs-lookup"><span data-stu-id="e7fa5-118">Explanation</span></span>  
 <span data-ttu-id="e7fa5-119">このエラー/警告/情報イベントは、EDI 送信パイプラインでは、識別されたトランザクション セット、示されたエラーのため送信 EDIFACT インターチェンジをシリアル化するときに、エラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="e7fa5-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified transaction set.</span></span> <span data-ttu-id="e7fa5-120">トランザクション セットがインターチェンジ内のグループでないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e7fa5-120">Note that the transaction set is not in a group in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e7fa5-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e7fa5-121">User Action</span></span>  
 <span data-ttu-id="e7fa5-122">このエラーを解決するには、エラー メッセージの情報を使用してトランザクション セットのエラーを特定し、問題の解決方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="e7fa5-122">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution.</span></span>