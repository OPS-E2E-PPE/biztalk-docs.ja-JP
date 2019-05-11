---
title: シングル サインオン:イベント 10590 |Microsoft Docs
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
ms.openlocfilehash: 21e9ed1ffdee369ccb357cb7b7f20424cb61b474
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271028"
---
# <a name="single-sign-on-event-10590"></a><span data-ttu-id="56525-102">シングル サインオン:イベント 10590</span><span class="sxs-lookup"><span data-stu-id="56525-102">Single Sign-On: Event 10590</span></span>
## <a name="details"></a><span data-ttu-id="56525-103">詳細</span><span class="sxs-lookup"><span data-stu-id="56525-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="56525-104">製品名</span><span class="sxs-lookup"><span data-stu-id="56525-104">Product Name</span></span>   |                 <span data-ttu-id="56525-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="56525-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="56525-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="56525-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="56525-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="56525-107">Event ID</span></span>     |                           <span data-ttu-id="56525-108">10590</span><span class="sxs-lookup"><span data-stu-id="56525-108">10590</span></span>                            |
|  <span data-ttu-id="56525-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="56525-109">Event Source</span></span>   |                           <span data-ttu-id="56525-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="56525-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="56525-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="56525-111">Component</span></span>    |                            <span data-ttu-id="56525-112">なし</span><span class="sxs-lookup"><span data-stu-id="56525-112">N/A</span></span>                             |
|  <span data-ttu-id="56525-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="56525-113">Symbolic Name</span></span>  |                  <span data-ttu-id="56525-114">SSO_ERROR_OUT_OF_SERVICE</span><span class="sxs-lookup"><span data-stu-id="56525-114">SSO_ERROR_OUT_OF_SERVICE</span></span>                  |
|  <span data-ttu-id="56525-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="56525-115">Message Text</span></span>   |        <span data-ttu-id="56525-116">エンタープライズ シングル サインオンはオフラインになります。</span><span class="sxs-lookup"><span data-stu-id="56525-116">Enterprise Single Sign-On is going offline.</span></span>         |
  
## <a name="explanation"></a><span data-ttu-id="56525-117">説明</span><span class="sxs-lookup"><span data-stu-id="56525-117">Explanation</span></span>  
 <span data-ttu-id="56525-118">ENTSSO システムは、通常更新プログラムをチェック ENTSSO データベースで 30 秒ごとです。</span><span class="sxs-lookup"><span data-stu-id="56525-118">The ENTSSO system usually checks for updates on the ENTSSO database every 30 seconds.</span></span> <span data-ttu-id="56525-119">データベース利用できない場合、指定した時間 (通常は 5 分)、システム自体がオフラインになります。</span><span class="sxs-lookup"><span data-stu-id="56525-119">If the database is unavailable for a specified time (usually five minutes), the system itself goes offline.</span></span> <span data-ttu-id="56525-120">この状態で、システムは資格情報の要求に応答しません。</span><span class="sxs-lookup"><span data-stu-id="56525-120">In this state the system will not respond to requests for credentials.</span></span> <span data-ttu-id="56525-121">一部のオフラインおよび管理アクティビティは引き続き可能です。</span><span class="sxs-lookup"><span data-stu-id="56525-121">Some offline and administrative activities are still possible.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="56525-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="56525-122">User Action</span></span>  
 <span data-ttu-id="56525-123">このエラーは、ENTSSO データベースがオフラインであることを示します。</span><span class="sxs-lookup"><span data-stu-id="56525-123">This error indicates that the ENTSSO database is offline.</span></span> <span data-ttu-id="56525-124">すぐに調査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56525-124">You should investigate immediately.</span></span>