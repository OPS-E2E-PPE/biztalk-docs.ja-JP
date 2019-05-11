---
title: シングル サインオン:イベント 10610 |Microsoft Docs
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
ms.openlocfilehash: 451468316420c0653b967a25f233564303a6e1a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397724"
---
# <a name="single-sign-on-event-10610"></a><span data-ttu-id="959e3-102">シングル サインオン:イベント 10610</span><span class="sxs-lookup"><span data-stu-id="959e3-102">Single Sign-On: Event 10610</span></span>
## <a name="details"></a><span data-ttu-id="959e3-103">詳細</span><span class="sxs-lookup"><span data-stu-id="959e3-103">Details</span></span>  
  
|                 |                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="959e3-104">製品名</span><span class="sxs-lookup"><span data-stu-id="959e3-104">Product Name</span></span>   |                                                       <span data-ttu-id="959e3-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="959e3-105">Enterprise Single Sign-On</span></span>                                                       |
| <span data-ttu-id="959e3-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="959e3-106">Product Version</span></span> |                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                       |
|    <span data-ttu-id="959e3-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="959e3-107">Event ID</span></span>     |                                                                 <span data-ttu-id="959e3-108">10610</span><span class="sxs-lookup"><span data-stu-id="959e3-108">10610</span></span>                                                                 |
|  <span data-ttu-id="959e3-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="959e3-109">Event Source</span></span>   |                                                                <span data-ttu-id="959e3-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="959e3-110">ENTSSO</span></span>                                                                 |
|    <span data-ttu-id="959e3-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="959e3-111">Component</span></span>    |                                                                  <span data-ttu-id="959e3-112">なし</span><span class="sxs-lookup"><span data-stu-id="959e3-112">N/A</span></span>                                                                  |
|  <span data-ttu-id="959e3-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="959e3-113">Symbolic Name</span></span>  |                                                      <span data-ttu-id="959e3-114">SSO_WARN_CRED_CACHE_FAILED</span><span class="sxs-lookup"><span data-stu-id="959e3-114">SSO_WARN_CRED_CACHE_FAILED</span></span>                                                       |
|  <span data-ttu-id="959e3-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="959e3-115">Message Text</span></span>   | <span data-ttu-id="959e3-116">資格情報のキャッシュでは、予期しないエラーが発生し、シャット ダウンします。</span><span class="sxs-lookup"><span data-stu-id="959e3-116">The credential cache has encountered an unexpected error and has shut down.</span></span> <span data-ttu-id="959e3-117">Performance.%r に影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="959e3-117">This may affect performance.%r</span></span><br /><br /> <span data-ttu-id="959e3-118">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="959e3-118">Error Code: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="959e3-119">説明</span><span class="sxs-lookup"><span data-stu-id="959e3-119">Explanation</span></span>  
 <span data-ttu-id="959e3-120">資格情報のキャッシュでは、予期しないエラーが発生し、シャット ダウンします。</span><span class="sxs-lookup"><span data-stu-id="959e3-120">The credential cache has encountered an unexpected error and has shut down.</span></span> <span data-ttu-id="959e3-121">これは、パフォーマンスに影響を与える、機能は影響しません。</span><span class="sxs-lookup"><span data-stu-id="959e3-121">While this may affect performance, it will not affect functionality.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="959e3-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="959e3-122">User Action</span></span>  
 <span data-ttu-id="959e3-123">適切なときに、SSO サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="959e3-123">Restart the SSO service when convenient.</span></span>