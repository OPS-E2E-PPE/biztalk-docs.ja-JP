---
title: 'シングル サインオン: イベント 10819 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ffa5e977-c8b9-4568-8963-0d4cf44b5637
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f196bb49cd0e5825551bbffe45757c327e2cbcca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972115"
---
# <a name="single-sign-on-event-10819"></a><span data-ttu-id="2941d-102">シングル サインオン: イベント 10819</span><span class="sxs-lookup"><span data-stu-id="2941d-102">Single Sign-On: Event 10819</span></span>
## <a name="details"></a><span data-ttu-id="2941d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="2941d-103">Details</span></span>  
  
|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="2941d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="2941d-104">Product Name</span></span>   |                         <span data-ttu-id="2941d-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="2941d-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="2941d-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="2941d-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="2941d-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2941d-107">Event ID</span></span>     |                                   <span data-ttu-id="2941d-108">10819</span><span class="sxs-lookup"><span data-stu-id="2941d-108">10819</span></span>                                   |
|  <span data-ttu-id="2941d-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="2941d-109">Event Source</span></span>   |                                  <span data-ttu-id="2941d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="2941d-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="2941d-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2941d-111">Component</span></span>    |                                    <span data-ttu-id="2941d-112">なし</span><span class="sxs-lookup"><span data-stu-id="2941d-112">N/A</span></span>                                    |
|  <span data-ttu-id="2941d-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="2941d-113">Symbolic Name</span></span>  |                         <span data-ttu-id="2941d-114">ENTSSO_E_MAPPING_CONFLICT</span><span class="sxs-lookup"><span data-stu-id="2941d-114">ENTSSO_E_MAPPING_CONFLICT</span></span>                         |
|  <span data-ttu-id="2941d-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="2941d-115">Message Text</span></span>   | <span data-ttu-id="2941d-116">マッピングの競合があるため、外部アカウントは更新されませんでした。</span><span class="sxs-lookup"><span data-stu-id="2941d-116">The external account was not updated because there is a mapping conflict.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="2941d-117">説明</span><span class="sxs-lookup"><span data-stu-id="2941d-117">Explanation</span></span>  
 <span data-ttu-id="2941d-118">マッピングの競合があるため、外部アカウントは更新されませんでした。</span><span class="sxs-lookup"><span data-stu-id="2941d-118">The external account was not updated because there is a mapping conflict.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2941d-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="2941d-119">User Action</span></span>  
 <span data-ttu-id="2941d-120">マッピングの競合が予想される動作の場合は、操作は必要ありません。このメッセージは情報のみです。</span><span class="sxs-lookup"><span data-stu-id="2941d-120">If this is expected behavior then no action is required, this message is informational only.</span></span> <span data-ttu-id="2941d-121">マッピングの競合を許可する必要がある場合は、アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="2941d-121">If mapping conflicts should be allowed then configure the application accordingly.</span></span>  
  
 <span data-ttu-id="2941d-122">マッピングの競合の詳細については、**パスワード同期アダプターのプロパティ: オプション**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2941d-122">For more information on mapping conflicts, see **Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>