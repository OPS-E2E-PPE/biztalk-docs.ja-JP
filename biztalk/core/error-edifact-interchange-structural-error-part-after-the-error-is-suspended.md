---
title: インターチェンジで構造エラーが。 中断されていますが、エラー後の部分 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9071825d-7b90-42bf-bcf9-2a15ae36086d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ebfeec80fb9775fbb99c07fc1c694f38f6b11c7
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530754"
---
# <a name="the-interchange-had-structural-error-the-part-after-the-error-is-being-suspended"></a><span data-ttu-id="4beba-103">インターチェンジで構造エラーが。</span><span class="sxs-lookup"><span data-stu-id="4beba-103">The interchange had structural error.</span></span> <span data-ttu-id="4beba-104">中断されていますが、エラー後の部分</span><span class="sxs-lookup"><span data-stu-id="4beba-104">The part after the error is being suspended</span></span>
## <a name="details"></a><span data-ttu-id="4beba-105">詳細</span><span class="sxs-lookup"><span data-stu-id="4beba-105">Details</span></span>  
  
|                 |                                                                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="4beba-106">製品名</span><span class="sxs-lookup"><span data-stu-id="4beba-106">Product Name</span></span>   |                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| <span data-ttu-id="4beba-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4beba-107">Product Version</span></span> |                                                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                           |
|    <span data-ttu-id="4beba-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4beba-108">Event ID</span></span>     |                                                                                       -                                                                                        |
|  <span data-ttu-id="4beba-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4beba-109">Event Source</span></span>   |                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="4beba-110">EDI</span><span class="sxs-lookup"><span data-stu-id="4beba-110">EDI</span></span>                                             |
|    <span data-ttu-id="4beba-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4beba-111">Component</span></span>    |                                                                                   <span data-ttu-id="4beba-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="4beba-112">EDI Engine</span></span>                                                                                   |
|  <span data-ttu-id="4beba-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4beba-113">Symbolic Name</span></span>  |                                                                        <span data-ttu-id="4beba-114">EfactInterchangeStructuralError</span><span class="sxs-lookup"><span data-stu-id="4beba-114">EfactInterchangeStructuralError</span></span>                                                                         |
|  <span data-ttu-id="4beba-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4beba-115">Message Text</span></span>   | <span data-ttu-id="4beba-116">Id を持つインターチェンジ '{0}'、送信者 id'{1}'、受信者 id '{2}' 構造エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="4beba-116">The interchange with id '{0}', with sender id '{1}', receiver id '{2}' had structural error.</span></span> <span data-ttu-id="4beba-117">詳細については、エラーが中断されていますが後の部分が保留キューを参照します。</span><span class="sxs-lookup"><span data-stu-id="4beba-117">The part after the error is being suspended, refer to Suspended Queue for details</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="4beba-118">説明</span><span class="sxs-lookup"><span data-stu-id="4beba-118">Explanation</span></span>  
 <span data-ttu-id="4beba-119">このエラー/警告/情報イベントは、インターチェンジで構造エラーが発生したために、受信パイプラインが受信 EDIFACT インターチェンジを処理しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="4beba-119">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming EDIFACT interchange, because a structural error occurred in the interchange.</span></span> <span data-ttu-id="4beba-120">エラーで中断されたトランザクション セットを持つ、保持されているインターチェンジでこれが発生しました。</span><span class="sxs-lookup"><span data-stu-id="4beba-120">This occurred with an interchange that was being preserved, with transaction sets suspended on the error.</span></span> <span data-ttu-id="4beba-121">このエラーをトランザクション セット (またはセット) の結果であり、エラーが含まれているが中断されたが、トランザクションの残りの部分の設定は、保存されたバッチの一部として処理されました。</span><span class="sxs-lookup"><span data-stu-id="4beba-121">As a result of this error, the transaction set (or sets) that included the error was suspended, but the rest of the transaction sets were processed as part of the preserved batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4beba-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4beba-122">User Action</span></span>  
 <span data-ttu-id="4beba-123">このエラーを解決するには、構造のエラーでは、インターチェンジの送信者し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="4beba-123">To resolve this error, have the sender of the interchange fix the structural error, and then resend the interchange.</span></span>