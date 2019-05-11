---
title: 'インターチェンジで構造エラーが。 最後の構造上有効な機能グループ ID が: |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd62855b-ecc6-4cfd-be9c-0025348eb841
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23055c421a847835ceac3ea96286794e73cb5dcc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346220"
---
# <a name="the-interchange-had-structural-error-last-structurally-valid-functional-group-id-was"></a><span data-ttu-id="d8b62-103">インターチェンジで構造エラーが。</span><span class="sxs-lookup"><span data-stu-id="d8b62-103">The interchange had structural error.</span></span> <span data-ttu-id="d8b62-104">最後の機能グループの構造上有効な ID は次のとおりでした。</span><span class="sxs-lookup"><span data-stu-id="d8b62-104">Last structurally valid functional group ID was:</span></span>
## <a name="details"></a><span data-ttu-id="d8b62-105">詳細</span><span class="sxs-lookup"><span data-stu-id="d8b62-105">Details</span></span>  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d8b62-106">製品名</span><span class="sxs-lookup"><span data-stu-id="d8b62-106">Product Name</span></span>   |                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                 |
| <span data-ttu-id="d8b62-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d8b62-107">Product Version</span></span> |                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                             |
|    <span data-ttu-id="d8b62-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d8b62-108">Event ID</span></span>     |                                                                         -                                                                          |
|  <span data-ttu-id="d8b62-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d8b62-109">Event Source</span></span>   |                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="d8b62-110">EDI</span><span class="sxs-lookup"><span data-stu-id="d8b62-110">EDI</span></span>                               |
|    <span data-ttu-id="d8b62-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d8b62-111">Component</span></span>    |                                                                     <span data-ttu-id="d8b62-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="d8b62-112">EDI Engine</span></span>                                                                     |
|  <span data-ttu-id="d8b62-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d8b62-113">Symbolic Name</span></span>  |                                                     <span data-ttu-id="d8b62-114">X12InterchangeStructuralErrorAfter1stGroup</span><span class="sxs-lookup"><span data-stu-id="d8b62-114">X12InterchangeStructuralErrorAfter1stGroup</span></span>                                                     |
|  <span data-ttu-id="d8b62-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d8b62-115">Message Text</span></span>   | <span data-ttu-id="d8b62-116">Id を持つインターチェンジ '{0}'、送信者 id'{1}'、受信者 id '{2}' 構造エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d8b62-116">The interchange with id '{0}', with sender id '{1}', receiver id '{2}' had structural error.</span></span> <span data-ttu-id="d8b62-117">最後の構造上有効な機能グループ ID が '{3}'</span><span class="sxs-lookup"><span data-stu-id="d8b62-117">Last structurally valid functional group ID was '{3}'</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d8b62-118">説明</span><span class="sxs-lookup"><span data-stu-id="d8b62-118">Explanation</span></span>  
 <span data-ttu-id="d8b62-119">このエラー/警告/情報イベントは、受信パイプラインで受信を処理できなかったことを示します X12 インターチェンジで構造エラーが表示された機能グループの後に、インターチェンジで発生したためです。</span><span class="sxs-lookup"><span data-stu-id="d8b62-119">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange, because a structural error occurred in the interchange after the indicated functional group.</span></span> <span data-ttu-id="d8b62-120">これは、エラーで中断されたトランザクション セットを持つ、保持されているインターチェンジで発生した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d8b62-120">This may have occurred with an interchange that was being preserved, with transaction sets suspended on the error.</span></span> <span data-ttu-id="d8b62-121">このエラーをトランザクション セット (またはセット) の結果であり、エラーが含まれているが中断されたが、トランザクションの残りの部分の設定は、保存されたバッチの一部として処理されました。</span><span class="sxs-lookup"><span data-stu-id="d8b62-121">As a result of this error, the transaction set (or sets) that included the error was suspended, but the rest of the transaction sets were processed as part of the preserved batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d8b62-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d8b62-122">User Action</span></span>  
 <span data-ttu-id="d8b62-123">このエラーを解決するには、構造のエラーでは、インターチェンジの送信者し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="d8b62-123">To resolve this error, have the sender of the interchange fix the structural error, and then resend the interchange.</span></span>