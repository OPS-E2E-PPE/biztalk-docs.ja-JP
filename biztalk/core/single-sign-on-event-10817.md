---
title: "シングル サインオン: イベント 10817 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1668b81-e7f4-46d2-aebe-47007f70372b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c94f677ccd14dd821886210f9e4c55efd754a404
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10817"></a><span data-ttu-id="f7b86-102">シングル サインオン: イベント 10817</span><span class="sxs-lookup"><span data-stu-id="f7b86-102">Single Sign-On: Event 10817</span></span>
## <a name="details"></a><span data-ttu-id="f7b86-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f7b86-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f7b86-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f7b86-104">Product Name</span></span>|<span data-ttu-id="f7b86-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="f7b86-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="f7b86-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f7b86-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="f7b86-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f7b86-107">Event ID</span></span>|<span data-ttu-id="f7b86-108">10817</span><span class="sxs-lookup"><span data-stu-id="f7b86-108">10817</span></span>|  
|<span data-ttu-id="f7b86-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f7b86-109">Event Source</span></span>|<span data-ttu-id="f7b86-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f7b86-110">ENTSSO</span></span>|  
|<span data-ttu-id="f7b86-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f7b86-111">Component</span></span>|<span data-ttu-id="f7b86-112">なし</span><span class="sxs-lookup"><span data-stu-id="f7b86-112">N/A</span></span>|  
|<span data-ttu-id="f7b86-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f7b86-113">Symbolic Name</span></span>|<span data-ttu-id="f7b86-114">ENTSSO_E_NOTIFICATION_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="f7b86-114">ENTSSO_E_NOTIFICATION_NOT_FOUND</span></span>|  
|<span data-ttu-id="f7b86-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f7b86-115">Message Text</span></span>|<span data-ttu-id="f7b86-116">指定された通知が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="f7b86-116">The specified notification was not found.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f7b86-117">説明</span><span class="sxs-lookup"><span data-stu-id="f7b86-117">Explanation</span></span>  
 <span data-ttu-id="f7b86-118">パスワード変更で指定された通知の GUID が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="f7b86-118">The password change specified a notification GUID which cannot be found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f7b86-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f7b86-119">User Action</span></span>  
 <span data-ttu-id="f7b86-120">このパスワード同期アダプターの構成を調べて、通知の正しい GUID を確認します。</span><span class="sxs-lookup"><span data-stu-id="f7b86-120">See the configuration for this password sync adapter to determine the proper GUID of the notification.</span></span>