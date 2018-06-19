---
title: バッチ ID と関連付けられているアグリーメントが有効ではないか、または期限切れです。 バッチ処理を続行できません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d92cb07-7646-42b3-90a8-18acbcd145cd
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e68e91fe1cd2d91c20c84a32afd37212769a4736
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241490"
---
# <a name="the-agreement-associated-with-batchid-is-not-enabled-or-has-expired-batching-cannot-continue"></a><span data-ttu-id="492b5-103">バッチ ID と関連付けられているアグリーメントが有効ではないか、または期限切れです。</span><span class="sxs-lookup"><span data-stu-id="492b5-103">The agreement associated with BatchId is not enabled or has expired.</span></span> <span data-ttu-id="492b5-104">バッチ処理を続行できません</span><span class="sxs-lookup"><span data-stu-id="492b5-104">Batching cannot continue</span></span>
## <a name="details"></a><span data-ttu-id="492b5-105">詳細</span><span class="sxs-lookup"><span data-stu-id="492b5-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="492b5-106">製品名</span><span class="sxs-lookup"><span data-stu-id="492b5-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="492b5-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="492b5-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="492b5-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="492b5-108">Event ID</span></span>|-|  
|<span data-ttu-id="492b5-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="492b5-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="492b5-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="492b5-110"> EDI</span></span>|  
|<span data-ttu-id="492b5-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="492b5-111">Component</span></span>|<span data-ttu-id="492b5-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="492b5-112">EDI Engine</span></span>|  
|<span data-ttu-id="492b5-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="492b5-113">Symbolic Name</span></span>|<span data-ttu-id="492b5-114">ErrorBatchAgreementDisabled</span><span class="sxs-lookup"><span data-stu-id="492b5-114">ErrorBatchAgreementDisabled</span></span>|  
|<span data-ttu-id="492b5-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="492b5-115">Message Text</span></span>|<span data-ttu-id="492b5-116">バッチ ID {0} と関連付けられているアグリーメントが有効ではないか、または期限切れです。</span><span class="sxs-lookup"><span data-stu-id="492b5-116">The agreement associated with BatchId {0} is not enabled or has expired.</span></span> <span data-ttu-id="492b5-117">バッチ処理を続行できません。</span><span class="sxs-lookup"><span data-stu-id="492b5-117">Batching cannot continue.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="492b5-118">説明</span><span class="sxs-lookup"><span data-stu-id="492b5-118">Explanation</span></span>  
 <span data-ttu-id="492b5-119">このエラー/警告/情報イベントは、アグリーメントが期限切れのために、BizTalk Server がバッチを開始できなかったか、またはバッチ メッセージを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="492b5-119">This Error/Warning/Information event indicates BizTalk Server was not able to start a batch or process a batch message because of Agreement getting expired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="492b5-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="492b5-120">User Action</span></span>  
 <span data-ttu-id="492b5-121">このエラーを解決するには、指定された ID のバッチが、親アグリーメントの [アグリーメント] プロパティに存在し、その開始日と終了日がアグリーメントの開始日と終了日の範囲内であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="492b5-121">To resolve this error, ensure that a batch with the given Id is present in the Agreement properties of the containing Agreement and its start and end date fall within the start and end dates of the Agreement.</span></span> <span data-ttu-id="492b5-122">また、アグリーメントが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="492b5-122">Also make sure that the agreement is enabled.</span></span>