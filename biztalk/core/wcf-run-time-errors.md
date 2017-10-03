---
title: "WCF の実行時エラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5591bd4-aa15-4c7a-903e-fc73b880692f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97f4107ddf791b8d9fd152f2258cd3185f23498f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="wcf-run-time-errors"></a><span data-ttu-id="cecd7-102">WCF 実行時エラー</span><span class="sxs-lookup"><span data-stu-id="cecd7-102">WCF Run-Time Errors</span></span>
<span data-ttu-id="cecd7-103">診断および解決する WCF の実行時イベントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cecd7-103">Information for diagnosing and resolving WCF run-time events.</span></span>  
  
## <a name="wcf-service-host-restarted"></a><span data-ttu-id="cecd7-104">WCF サービス ホストが再起動されました</span><span class="sxs-lookup"><span data-stu-id="cecd7-104">WCF service host restarted</span></span>
  
||<span data-ttu-id="cecd7-105">エラーの詳細</span><span class="sxs-lookup"><span data-stu-id="cecd7-105">Error details</span></span>|  
|-|-|  
|<span data-ttu-id="cecd7-106">製品名</span><span class="sxs-lookup"><span data-stu-id="cecd7-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="cecd7-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="cecd7-107">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="cecd7-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cecd7-108">Event ID</span></span>|<span data-ttu-id="cecd7-109">0x1FB0</span><span class="sxs-lookup"><span data-stu-id="cecd7-109">0x1FB0</span></span>|  
|<span data-ttu-id="cecd7-110">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="cecd7-110">Event Source</span></span>|<span data-ttu-id="cecd7-111">0</span><span class="sxs-lookup"><span data-stu-id="cecd7-111">0</span></span>|  
|<span data-ttu-id="cecd7-112">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cecd7-112">Component</span></span>|<span data-ttu-id="cecd7-113">0</span><span class="sxs-lookup"><span data-stu-id="cecd7-113">0</span></span>|  
|<span data-ttu-id="cecd7-114">シンボル名</span><span class="sxs-lookup"><span data-stu-id="cecd7-114">Symbolic Name</span></span>|<span data-ttu-id="cecd7-115">BTS_I_WCF_SERVICE_HOST_RESTARTED</span><span class="sxs-lookup"><span data-stu-id="cecd7-115">BTS_I_WCF_SERVICE_HOST_RESTARTED</span></span>|  
|<span data-ttu-id="cecd7-116">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="cecd7-116">Message Text</span></span>|<span data-ttu-id="cecd7-117">0</span><span class="sxs-lookup"><span data-stu-id="cecd7-117">0</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cecd7-118">説明</span><span class="sxs-lookup"><span data-stu-id="cecd7-118">Explanation</span></span>  
 <span data-ttu-id="cecd7-119">このメッセージは、WCF アダプターが "参考" イベント ログ エントリを書き込む方法を示します (アダプター向けに用意された API では、情報ではなく警告またはエラーを作成できます)。</span><span class="sxs-lookup"><span data-stu-id="cecd7-119">This message provides a way for the WCF adapter to write an “informational” event log entry (the provided APIs for adapters allow the creation of warnings or errors, not information).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cecd7-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="cecd7-120">User Action</span></span>  
 <span data-ttu-id="cecd7-121">イベント ログにこの情報イベントが含まれている場合は、自動回復が正常に完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="cecd7-121">If you see this informational event in the event log, it indicates that the auto-recovery has succeeded.</span></span> <span data-ttu-id="cecd7-122">このメッセージについてその他の操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="cecd7-122">No further action in regard to this message is necessary.</span></span>