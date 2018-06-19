---
title: 通信方式エラー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06656073-9bae-4d6f-98ae-2714a72ee79c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36677694b8f2d0973c04d942a196d055b696bd5c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232210"
---
# <a name="communication-pattern-errors"></a><span data-ttu-id="3206d-102">通信方式エラー</span><span class="sxs-lookup"><span data-stu-id="3206d-102">Communication Pattern Errors</span></span>
<span data-ttu-id="3206d-103">診断および WCF の通信方式エラーを解決するための情報です。</span><span class="sxs-lookup"><span data-stu-id="3206d-103">Information for diagnosing and resolving WCF Communication Pattern errors.</span></span>  

## <a name="fault-messages-are-not-supported-on-one-way-ports"></a><span data-ttu-id="3206d-104">エラー メッセージは一方向のポートではサポートされていません</span><span class="sxs-lookup"><span data-stu-id="3206d-104">Fault messages are not supported on one-way ports</span></span>
  
||<span data-ttu-id="3206d-105">エラーの詳細</span><span class="sxs-lookup"><span data-stu-id="3206d-105">Error details</span></span>|  
|-|-|  
|<span data-ttu-id="3206d-106">製品名</span><span class="sxs-lookup"><span data-stu-id="3206d-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="3206d-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3206d-107">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="3206d-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3206d-108">Event ID</span></span>|<span data-ttu-id="3206d-109">0</span><span class="sxs-lookup"><span data-stu-id="3206d-109">0</span></span>|  
|<span data-ttu-id="3206d-110">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3206d-110">Event Source</span></span>|<span data-ttu-id="3206d-111">0</span><span class="sxs-lookup"><span data-stu-id="3206d-111">0</span></span>|  
|<span data-ttu-id="3206d-112">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3206d-112">Component</span></span>|<span data-ttu-id="3206d-113">0</span><span class="sxs-lookup"><span data-stu-id="3206d-113">0</span></span>|  
|<span data-ttu-id="3206d-114">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3206d-114">Symbolic Name</span></span>|<span data-ttu-id="3206d-115">0</span><span class="sxs-lookup"><span data-stu-id="3206d-115">0</span></span>|  
|<span data-ttu-id="3206d-116">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3206d-116">Message Text</span></span>|<span data-ttu-id="3206d-117">エラー メッセージは一方向のポートではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3206d-117">Fault messages are not supported on one-way ports.</span></span> <span data-ttu-id="3206d-118">サービス「{1}」説明"{0}"ポートの種類を修正し、ウィザードを再実行</span><span class="sxs-lookup"><span data-stu-id="3206d-118">Correct service description "{0}" port type "{1}" and rerun the wizard</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3206d-119">説明</span><span class="sxs-lookup"><span data-stu-id="3206d-119">Explanation</span></span>  
 <span data-ttu-id="3206d-120">このエラーは、使用するサービスが一方向のサービスであり、誤って指定されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="3206d-120">This error indicates the service trying to be consumed is a one-way service and has the fault specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3206d-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3206d-121">User Action</span></span>  
 <span data-ttu-id="3206d-122">通信パターンを一方向から要求 - 応答に切り替える方法でサービスを修正します。</span><span class="sxs-lookup"><span data-stu-id="3206d-122">Correct the service by switching the communication pattern from one-way to request-response.</span></span> <span data-ttu-id="3206d-123">または、コードの誤りを削除します。</span><span class="sxs-lookup"><span data-stu-id="3206d-123">Or remove the fault in the code.</span></span>
 
 