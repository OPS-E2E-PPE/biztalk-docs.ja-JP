---
title: シングル サインオン:イベント 10762 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 516e120d-e72b-4f40-9a81-9131ea247dd0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b26f196e2431f0229ac28b9d8f2718b551a58b1c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396652"
---
# <a name="single-sign-on-event-10762"></a><span data-ttu-id="c73d0-102">シングル サインオン:イベント 10762</span><span class="sxs-lookup"><span data-stu-id="c73d0-102">Single Sign-On: Event 10762</span></span>
## <a name="details"></a><span data-ttu-id="c73d0-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c73d0-103">Details</span></span>  
  
|                 |                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c73d0-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c73d0-104">Product Name</span></span>   |                                                   <span data-ttu-id="c73d0-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="c73d0-105">Enterprise Single Sign-On</span></span>                                                    |
| <span data-ttu-id="c73d0-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c73d0-106">Product Version</span></span> |                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                   |
|    <span data-ttu-id="c73d0-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c73d0-107">Event ID</span></span>     |                                                             <span data-ttu-id="c73d0-108">10762</span><span class="sxs-lookup"><span data-stu-id="c73d0-108">10762</span></span>                                                              |
|  <span data-ttu-id="c73d0-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c73d0-109">Event Source</span></span>   |                                                             <span data-ttu-id="c73d0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c73d0-110">ENTSSO</span></span>                                                             |
|    <span data-ttu-id="c73d0-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c73d0-111">Component</span></span>    |                                                              <span data-ttu-id="c73d0-112">なし</span><span class="sxs-lookup"><span data-stu-id="c73d0-112">N/A</span></span>                                                               |
|  <span data-ttu-id="c73d0-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c73d0-113">Symbolic Name</span></span>  |                                                     <span data-ttu-id="c73d0-114">ENTSSO_E_WRONG_THREAD</span><span class="sxs-lookup"><span data-stu-id="c73d0-114">ENTSSO_E_WRONG_THREAD</span></span>                                                      |
|  <span data-ttu-id="c73d0-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c73d0-115">Message Text</span></span>   | <span data-ttu-id="c73d0-116">SSO クライアント コンポーネントは間違ったスレッドで呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="c73d0-116">The SSO client component has been called on the wrong thread.</span></span> <span data-ttu-id="c73d0-117">トランザクションがあるため、現在のスレッドにロックします。</span><span class="sxs-lookup"><span data-stu-id="c73d0-117">It is currently locked to a thread because it has a transaction.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c73d0-118">説明</span><span class="sxs-lookup"><span data-stu-id="c73d0-118">Explanation</span></span>  
 <span data-ttu-id="c73d0-119">コンポーネントはできるトランザクションがあるない場合、マルチ スレッドにのみ。</span><span class="sxs-lookup"><span data-stu-id="c73d0-119">Components can only be multi-threaded when they do not have a transaction.</span></span> <span data-ttu-id="c73d0-120">このコンポーネントでは、スレッドにロックされているため、トランザクションがあります。</span><span class="sxs-lookup"><span data-stu-id="c73d0-120">This component has a transaction so it is locked to a thread.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c73d0-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c73d0-121">User Action</span></span>  
 <span data-ttu-id="c73d0-122">呼び出さない SSO クライアント コンポーネント複数のスレッドでトランザクションを使用する場合、アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="c73d0-122">Configure your application so that it will not call SSO client components on multiple threads when using transactions.</span></span>