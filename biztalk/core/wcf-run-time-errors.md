---
title: WCF 実行時エラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5591bd4-aa15-4c7a-903e-fc73b880692f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df75d019b9af36f4ef7fce21ea17dc1e9a8e7aac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999931"
---
# <a name="wcf-run-time-errors"></a><span data-ttu-id="858a5-102">WCF 実行時エラー</span><span class="sxs-lookup"><span data-stu-id="858a5-102">WCF Run-Time Errors</span></span>
<span data-ttu-id="858a5-103">診断および WCF の実行時イベントを解決するための情報です。</span><span class="sxs-lookup"><span data-stu-id="858a5-103">Information for diagnosing and resolving WCF run-time events.</span></span>  
  
## <a name="wcf-service-host-restarted"></a><span data-ttu-id="858a5-104">WCF サービス ホストが再起動されました</span><span class="sxs-lookup"><span data-stu-id="858a5-104">WCF service host restarted</span></span>
  
|                 |                                   <span data-ttu-id="858a5-105">エラーの詳細</span><span class="sxs-lookup"><span data-stu-id="858a5-105">Error details</span></span>                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="858a5-106">製品名</span><span class="sxs-lookup"><span data-stu-id="858a5-106">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="858a5-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="858a5-107">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="858a5-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="858a5-108">Event ID</span></span>     |                                       <span data-ttu-id="858a5-109">0x1FB0</span><span class="sxs-lookup"><span data-stu-id="858a5-109">0x1FB0</span></span>                                       |
|  <span data-ttu-id="858a5-110">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="858a5-110">Event Source</span></span>   |                                         <span data-ttu-id="858a5-111">0</span><span class="sxs-lookup"><span data-stu-id="858a5-111">0</span></span>                                          |
|    <span data-ttu-id="858a5-112">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="858a5-112">Component</span></span>    |                                         <span data-ttu-id="858a5-113">0</span><span class="sxs-lookup"><span data-stu-id="858a5-113">0</span></span>                                          |
|  <span data-ttu-id="858a5-114">シンボル名</span><span class="sxs-lookup"><span data-stu-id="858a5-114">Symbolic Name</span></span>  |                          <span data-ttu-id="858a5-115">BTS_I_WCF_SERVICE_HOST_RESTARTED</span><span class="sxs-lookup"><span data-stu-id="858a5-115">BTS_I_WCF_SERVICE_HOST_RESTARTED</span></span>                          |
|  <span data-ttu-id="858a5-116">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="858a5-116">Message Text</span></span>   |                                         <span data-ttu-id="858a5-117">0</span><span class="sxs-lookup"><span data-stu-id="858a5-117">0</span></span>                                          |
  
## <a name="explanation"></a><span data-ttu-id="858a5-118">説明</span><span class="sxs-lookup"><span data-stu-id="858a5-118">Explanation</span></span>  
 <span data-ttu-id="858a5-119">このメッセージは、WCF アダプターが "参考" イベント ログ エントリを書き込む方法を示します (アダプター向けに用意された API では、情報ではなく警告またはエラーを作成できます)。</span><span class="sxs-lookup"><span data-stu-id="858a5-119">This message provides a way for the WCF adapter to write an “informational” event log entry (the provided APIs for adapters allow the creation of warnings or errors, not information).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="858a5-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="858a5-120">User Action</span></span>  
 <span data-ttu-id="858a5-121">イベント ログにこの情報イベントが含まれている場合は、自動回復が正常に完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="858a5-121">If you see this informational event in the event log, it indicates that the auto-recovery has succeeded.</span></span> <span data-ttu-id="858a5-122">このメッセージについてその他の操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="858a5-122">No further action in regard to this message is necessary.</span></span>