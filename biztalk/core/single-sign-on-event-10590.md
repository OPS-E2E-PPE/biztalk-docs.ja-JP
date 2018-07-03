---
title: 'シングル サインオン: イベント 10590 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd8c3804-5c84-403f-881b-e4b101c2323a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc2ac48ecf1279c1a8347e8f1ab3bcd1367854ff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006772"
---
# <a name="single-sign-on-event-10590"></a><span data-ttu-id="1c0aa-102">シングル サインオン: イベント 10590</span><span class="sxs-lookup"><span data-stu-id="1c0aa-102">Single Sign-On: Event 10590</span></span>
## <a name="details"></a><span data-ttu-id="1c0aa-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1c0aa-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="1c0aa-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1c0aa-104">Product Name</span></span>   |                 <span data-ttu-id="1c0aa-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="1c0aa-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="1c0aa-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1c0aa-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="1c0aa-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1c0aa-107">Event ID</span></span>     |                           <span data-ttu-id="1c0aa-108">10590</span><span class="sxs-lookup"><span data-stu-id="1c0aa-108">10590</span></span>                            |
|  <span data-ttu-id="1c0aa-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1c0aa-109">Event Source</span></span>   |                           <span data-ttu-id="1c0aa-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1c0aa-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="1c0aa-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1c0aa-111">Component</span></span>    |                            <span data-ttu-id="1c0aa-112">なし</span><span class="sxs-lookup"><span data-stu-id="1c0aa-112">N/A</span></span>                             |
|  <span data-ttu-id="1c0aa-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1c0aa-113">Symbolic Name</span></span>  |                  <span data-ttu-id="1c0aa-114">SSO_ERROR_OUT_OF_SERVICE</span><span class="sxs-lookup"><span data-stu-id="1c0aa-114">SSO_ERROR_OUT_OF_SERVICE</span></span>                  |
|  <span data-ttu-id="1c0aa-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1c0aa-115">Message Text</span></span>   |        <span data-ttu-id="1c0aa-116">エンタープライズ シングル サインオンは、オフラインに移行しています。</span><span class="sxs-lookup"><span data-stu-id="1c0aa-116">Enterprise Single Sign-On is going offline.</span></span>         |
  
## <a name="explanation"></a><span data-ttu-id="1c0aa-117">説明</span><span class="sxs-lookup"><span data-stu-id="1c0aa-117">Explanation</span></span>  
 <span data-ttu-id="1c0aa-118">通常、ENTSSO システムは 30 秒ごとに ENTSSO データベースの更新を検査します。</span><span class="sxs-lookup"><span data-stu-id="1c0aa-118">The ENTSSO system usually checks for updates on the ENTSSO database every 30 seconds.</span></span> <span data-ttu-id="1c0aa-119">指定されている時間 (通常は 5 分) の間データベースが使用できない場合、システム自体がオフラインになります。</span><span class="sxs-lookup"><span data-stu-id="1c0aa-119">If the database is unavailable for a specified time (usually five minutes), the system itself goes offline.</span></span> <span data-ttu-id="1c0aa-120">この状態では、システムは資格情報の要求に応答しません。</span><span class="sxs-lookup"><span data-stu-id="1c0aa-120">In this state the system will not respond to requests for credentials.</span></span> <span data-ttu-id="1c0aa-121">一部のオフラインおよび管理アクティビティはこの状態でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c0aa-121">Some offline and administrative activities are still possible.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1c0aa-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1c0aa-122">User Action</span></span>  
 <span data-ttu-id="1c0aa-123">このエラーは、ENTSSO データベースがオフラインであることを示します。</span><span class="sxs-lookup"><span data-stu-id="1c0aa-123">This error indicates that the ENTSSO database is offline.</span></span> <span data-ttu-id="1c0aa-124">直ちに調査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c0aa-124">You should investigate immediately.</span></span>