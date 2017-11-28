---
title: "バッチが見つかりませんでした |。Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e967e1a-b87f-4c87-a157-a6f63ba96d78
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a73c3e65a806f02faeb81baa6a5263019079b0c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-batch-was-not-found"></a><span data-ttu-id="7d6d4-102">バッチが見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="7d6d4-102">The batch was not found</span></span>
## <a name="details"></a><span data-ttu-id="7d6d4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="7d6d4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7d6d4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="7d6d4-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="7d6d4-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7d6d4-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="7d6d4-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7d6d4-106">Event ID</span></span>|-|  
|<span data-ttu-id="7d6d4-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7d6d4-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7d6d4-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="7d6d4-108"> EDI</span></span>|  
|<span data-ttu-id="7d6d4-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7d6d4-109">Component</span></span>|<span data-ttu-id="7d6d4-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="7d6d4-110">EDI Engine</span></span>|  
|<span data-ttu-id="7d6d4-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7d6d4-111">Symbolic Name</span></span>|<span data-ttu-id="7d6d4-112">Err_BatchNotFound</span><span class="sxs-lookup"><span data-stu-id="7d6d4-112">Err_BatchNotFound</span></span>|  
|<span data-ttu-id="7d6d4-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7d6d4-113">Message Text</span></span>|<span data-ttu-id="7d6d4-114">バッチが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="7d6d4-114">The batch was not found.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7d6d4-115">説明</span><span class="sxs-lookup"><span data-stu-id="7d6d4-115">Explanation</span></span>  
 <span data-ttu-id="7d6d4-116">このエラー/警告/情報イベントは、バッチの開始/停止中、またはバッチ オーケストレーションがメッセージのバッチ処理を試行中に、BizTalk Server がバッチを見つけられなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="7d6d4-116">This Error/Warning/Information event indicates BizTalk Server was unable to find a batch during the start/stop of a batch or while the Batching Orchestration was trying to batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7d6d4-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7d6d4-117">User Action</span></span>  
 <span data-ttu-id="7d6d4-118">このエラーを解決するには、各バッチが親アグリーメントの [アグリーメントのプロパティ] に存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="7d6d4-118">To resolve this error, ensure that the respective batch is present in the Agreement properties of the containing Agreement.</span></span>