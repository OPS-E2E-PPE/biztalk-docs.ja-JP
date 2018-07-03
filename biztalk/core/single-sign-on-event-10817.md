---
title: 'シングル サインオン: イベント 10817 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1668b81-e7f4-46d2-aebe-47007f70372b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e42873f0b56c43a7c997a2476ba2b15148d4639
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979195"
---
# <a name="single-sign-on-event-10817"></a><span data-ttu-id="fcaed-102">シングル サインオン: イベント 10817</span><span class="sxs-lookup"><span data-stu-id="fcaed-102">Single Sign-On: Event 10817</span></span>
## <a name="details"></a><span data-ttu-id="fcaed-103">詳細</span><span class="sxs-lookup"><span data-stu-id="fcaed-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="fcaed-104">製品名</span><span class="sxs-lookup"><span data-stu-id="fcaed-104">Product Name</span></span>   |                 <span data-ttu-id="fcaed-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="fcaed-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="fcaed-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="fcaed-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="fcaed-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="fcaed-107">Event ID</span></span>     |                           <span data-ttu-id="fcaed-108">10817</span><span class="sxs-lookup"><span data-stu-id="fcaed-108">10817</span></span>                            |
|  <span data-ttu-id="fcaed-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="fcaed-109">Event Source</span></span>   |                           <span data-ttu-id="fcaed-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fcaed-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="fcaed-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fcaed-111">Component</span></span>    |                            <span data-ttu-id="fcaed-112">なし</span><span class="sxs-lookup"><span data-stu-id="fcaed-112">N/A</span></span>                             |
|  <span data-ttu-id="fcaed-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="fcaed-113">Symbolic Name</span></span>  |              <span data-ttu-id="fcaed-114">ENTSSO_E_NOTIFICATION_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="fcaed-114">ENTSSO_E_NOTIFICATION_NOT_FOUND</span></span>               |
|  <span data-ttu-id="fcaed-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="fcaed-115">Message Text</span></span>   |         <span data-ttu-id="fcaed-116">指定された通知が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="fcaed-116">The specified notification was not found.</span></span>          |
  
## <a name="explanation"></a><span data-ttu-id="fcaed-117">説明</span><span class="sxs-lookup"><span data-stu-id="fcaed-117">Explanation</span></span>  
 <span data-ttu-id="fcaed-118">パスワード変更で指定された通知の GUID が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="fcaed-118">The password change specified a notification GUID which cannot be found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fcaed-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="fcaed-119">User Action</span></span>  
 <span data-ttu-id="fcaed-120">このパスワード同期アダプターの構成を調べて、通知の正しい GUID を確認します。</span><span class="sxs-lookup"><span data-stu-id="fcaed-120">See the configuration for this password sync adapter to determine the proper GUID of the notification.</span></span>