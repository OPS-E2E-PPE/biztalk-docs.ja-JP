---
title: 'シングル サインオン: イベント 10762 |Microsoft Docs'
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
ms.openlocfilehash: 905c59062f8f4af397872f3f7d4434a67b19842e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996011"
---
# <a name="single-sign-on-event-10762"></a><span data-ttu-id="a79d5-102">シングル サインオン: イベント 10762</span><span class="sxs-lookup"><span data-stu-id="a79d5-102">Single Sign-On: Event 10762</span></span>
## <a name="details"></a><span data-ttu-id="a79d5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a79d5-103">Details</span></span>  
  
|                 |                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a79d5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a79d5-104">Product Name</span></span>   |                                                   <span data-ttu-id="a79d5-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="a79d5-105">Enterprise Single Sign-On</span></span>                                                    |
| <span data-ttu-id="a79d5-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a79d5-106">Product Version</span></span> |                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                   |
|    <span data-ttu-id="a79d5-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a79d5-107">Event ID</span></span>     |                                                             <span data-ttu-id="a79d5-108">10762</span><span class="sxs-lookup"><span data-stu-id="a79d5-108">10762</span></span>                                                              |
|  <span data-ttu-id="a79d5-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a79d5-109">Event Source</span></span>   |                                                             <span data-ttu-id="a79d5-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a79d5-110">ENTSSO</span></span>                                                             |
|    <span data-ttu-id="a79d5-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a79d5-111">Component</span></span>    |                                                              <span data-ttu-id="a79d5-112">なし</span><span class="sxs-lookup"><span data-stu-id="a79d5-112">N/A</span></span>                                                               |
|  <span data-ttu-id="a79d5-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a79d5-113">Symbolic Name</span></span>  |                                                     <span data-ttu-id="a79d5-114">ENTSSO_E_WRONG_THREAD</span><span class="sxs-lookup"><span data-stu-id="a79d5-114">ENTSSO_E_WRONG_THREAD</span></span>                                                      |
|  <span data-ttu-id="a79d5-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a79d5-115">Message Text</span></span>   | <span data-ttu-id="a79d5-116">SSO クライアント コンポーネントが不適切なスレッドで呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="a79d5-116">The SSO client component has been called on the wrong thread.</span></span> <span data-ttu-id="a79d5-117">コンポーネントにトランザクションがあるため、現在コンポーネントはスレッドにロックされています。</span><span class="sxs-lookup"><span data-stu-id="a79d5-117">It is currently locked to a thread because it has a transaction.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="a79d5-118">説明</span><span class="sxs-lookup"><span data-stu-id="a79d5-118">Explanation</span></span>  
 <span data-ttu-id="a79d5-119">コンポーネントは、トランザクションがない場合にのみマルチスレッド化することができます。</span><span class="sxs-lookup"><span data-stu-id="a79d5-119">Components can only be multi-threaded when they do not have a transaction.</span></span> <span data-ttu-id="a79d5-120">このコンポーネントにはトランザクションがあるので、スレッドにロックされています。</span><span class="sxs-lookup"><span data-stu-id="a79d5-120">This component has a transaction so it is locked to a thread.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a79d5-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a79d5-121">User Action</span></span>  
 <span data-ttu-id="a79d5-122">トランザクションを使用しているときには複数のスレッドで SSO クライアント コンポーネントを呼び出さないようにアプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="a79d5-122">Configure your application so that it will not call SSO client components on multiple threads when using transactions.</span></span>