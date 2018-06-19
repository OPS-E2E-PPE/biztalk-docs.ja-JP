---
title: 'シングル サインオン: イベント 10610 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f6a400eb-7cf2-49df-befb-caf76e845fdf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3e4edc579c18147ad34234fbf268ec8d867c60f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271338"
---
# <a name="single-sign-on-event-10610"></a><span data-ttu-id="0fde9-102">シングル サインオン: イベント 10610</span><span class="sxs-lookup"><span data-stu-id="0fde9-102">Single Sign-On: Event 10610</span></span>
## <a name="details"></a><span data-ttu-id="0fde9-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0fde9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0fde9-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0fde9-104">Product Name</span></span>|<span data-ttu-id="0fde9-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="0fde9-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="0fde9-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0fde9-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="0fde9-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0fde9-107">Event ID</span></span>|<span data-ttu-id="0fde9-108">10610</span><span class="sxs-lookup"><span data-stu-id="0fde9-108">10610</span></span>|  
|<span data-ttu-id="0fde9-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0fde9-109">Event Source</span></span>|<span data-ttu-id="0fde9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0fde9-110">ENTSSO</span></span>|  
|<span data-ttu-id="0fde9-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0fde9-111">Component</span></span>|<span data-ttu-id="0fde9-112">なし</span><span class="sxs-lookup"><span data-stu-id="0fde9-112">N/A</span></span>|  
|<span data-ttu-id="0fde9-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0fde9-113">Symbolic Name</span></span>|<span data-ttu-id="0fde9-114">SSO_WARN_CRED_CACHE_FAILED</span><span class="sxs-lookup"><span data-stu-id="0fde9-114">SSO_WARN_CRED_CACHE_FAILED</span></span>|  
|<span data-ttu-id="0fde9-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0fde9-115">Message Text</span></span>|<span data-ttu-id="0fde9-116">資格情報キャッシュに予期しないエラーが発生し、シャットダウンされました。</span><span class="sxs-lookup"><span data-stu-id="0fde9-116">The credential cache has encountered an unexpected error and has shut down.</span></span> <span data-ttu-id="0fde9-117">パフォーマンスが低下する場合があります。%r</span><span class="sxs-lookup"><span data-stu-id="0fde9-117">This may affect performance.%r</span></span><br /><br /> <span data-ttu-id="0fde9-118">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="0fde9-118">Error Code: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0fde9-119">説明</span><span class="sxs-lookup"><span data-stu-id="0fde9-119">Explanation</span></span>  
 <span data-ttu-id="0fde9-120">資格情報キャッシュに予期しないエラーが発生し、シャットダウンされました。</span><span class="sxs-lookup"><span data-stu-id="0fde9-120">The credential cache has encountered an unexpected error and has shut down.</span></span> <span data-ttu-id="0fde9-121">これによってパフォーマンスは低下する場合がありますが、機能への影響はありません。</span><span class="sxs-lookup"><span data-stu-id="0fde9-121">While this may affect performance, it will not affect functionality.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0fde9-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0fde9-122">User Action</span></span>  
 <span data-ttu-id="0fde9-123">適切なときに SSO サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="0fde9-123">Restart the SSO service when convenient.</span></span>