---
title: "シングル サインオン: イベント 10807 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 882c01c6-70db-4986-9f4b-f08335424250
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e269b22bc8ea2fec013123d515ac04bd3f60d46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10807"></a><span data-ttu-id="70f47-102">シングル サインオン: イベント 10807</span><span class="sxs-lookup"><span data-stu-id="70f47-102">Single Sign-On: Event 10807</span></span>
## <a name="details"></a><span data-ttu-id="70f47-103">詳細</span><span class="sxs-lookup"><span data-stu-id="70f47-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="70f47-104">製品名</span><span class="sxs-lookup"><span data-stu-id="70f47-104">Product Name</span></span>|<span data-ttu-id="70f47-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="70f47-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="70f47-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="70f47-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="70f47-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="70f47-107">Event ID</span></span>|<span data-ttu-id="70f47-108">10807</span><span class="sxs-lookup"><span data-stu-id="70f47-108">10807</span></span>|  
|<span data-ttu-id="70f47-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="70f47-109">Event Source</span></span>|<span data-ttu-id="70f47-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="70f47-110">ENTSSO</span></span>|  
|<span data-ttu-id="70f47-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="70f47-111">Component</span></span>|<span data-ttu-id="70f47-112">なし</span><span class="sxs-lookup"><span data-stu-id="70f47-112">N/A</span></span>|  
|<span data-ttu-id="70f47-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="70f47-113">Symbolic Name</span></span>|<span data-ttu-id="70f47-114">ENTSSO_E_TOO_MANY_UNCONFIRMED_NOTIFICATIONS</span><span class="sxs-lookup"><span data-stu-id="70f47-114">ENTSSO_E_TOO_MANY_UNCONFIRMED_NOTIFICATIONS</span></span>|  
|<span data-ttu-id="70f47-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="70f47-115">Message Text</span></span>|<span data-ttu-id="70f47-116">未確認の通知が多すぎます。</span><span class="sxs-lookup"><span data-stu-id="70f47-116">Too many unconfirmed notifications.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="70f47-117">説明</span><span class="sxs-lookup"><span data-stu-id="70f47-117">Explanation</span></span>  
 <span data-ttu-id="70f47-118">パスワード変更通知が送信されるたびに、確認メッセージが受信されます。</span><span class="sxs-lookup"><span data-stu-id="70f47-118">Each time a password change notification is sent, a confirmation message is received.</span></span> <span data-ttu-id="70f47-119">この場合、確認されていない通知の制限値を超えています。</span><span class="sxs-lookup"><span data-stu-id="70f47-119">In this case, the limit for notifications without confirmation has been exceeded.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="70f47-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="70f47-120">User Action</span></span>  
 <span data-ttu-id="70f47-121">パスワード同期アダプターを確認します。</span><span class="sxs-lookup"><span data-stu-id="70f47-121">Check the password sync adapter.</span></span>