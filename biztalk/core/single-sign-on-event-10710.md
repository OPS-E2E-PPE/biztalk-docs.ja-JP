---
title: 'シングル サインオン: イベント 10710 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 469dc407-be7a-45a1-bcf5-2ba7060a19e2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1a3dafe3dd5b7dbdf0e5934218af6539427184f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271570"
---
# <a name="single-sign-on-event-10710"></a><span data-ttu-id="77a14-102">シングル サインオン: イベント 10710</span><span class="sxs-lookup"><span data-stu-id="77a14-102">Single Sign-On: Event 10710</span></span>
## <a name="details"></a><span data-ttu-id="77a14-103">詳細</span><span class="sxs-lookup"><span data-stu-id="77a14-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="77a14-104">製品名</span><span class="sxs-lookup"><span data-stu-id="77a14-104">Product Name</span></span>|<span data-ttu-id="77a14-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="77a14-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="77a14-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="77a14-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="77a14-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="77a14-107">Event ID</span></span>|<span data-ttu-id="77a14-108">10710</span><span class="sxs-lookup"><span data-stu-id="77a14-108">10710</span></span>|  
|<span data-ttu-id="77a14-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="77a14-109">Event Source</span></span>|<span data-ttu-id="77a14-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="77a14-110">ENTSSO</span></span>|  
|<span data-ttu-id="77a14-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="77a14-111">Component</span></span>|<span data-ttu-id="77a14-112">N\A</span><span class="sxs-lookup"><span data-stu-id="77a14-112">N\A</span></span>|  
|<span data-ttu-id="77a14-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="77a14-113">Symbolic Name</span></span>|<span data-ttu-id="77a14-114">SSO_INFO_PS_WIN_CHANGE_DAMPED</span><span class="sxs-lookup"><span data-stu-id="77a14-114">SSO_INFO_PS_WIN_CHANGE_DAMPED</span></span>|  
|<span data-ttu-id="77a14-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="77a14-115">Message Text</span></span>|<span data-ttu-id="77a14-116">Windows パスワードの変更は抑制されました (重複として検出され、破棄されました)。%r</span><span class="sxs-lookup"><span data-stu-id="77a14-116">A Windows password change was damped (detected as a duplicate and discarded).%r</span></span><br /><br /> <span data-ttu-id="77a14-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="77a14-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="77a14-118">Windows アカウント: %2 %r</span><span class="sxs-lookup"><span data-stu-id="77a14-118">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="77a14-119">クライアント ユーザー: %3</span><span class="sxs-lookup"><span data-stu-id="77a14-119">Client User: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="77a14-120">説明</span><span class="sxs-lookup"><span data-stu-id="77a14-120">Explanation</span></span>  
 <span data-ttu-id="77a14-121">この情報イベントは、Windows パスワードの変更が重複として検出されたため、破棄されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="77a14-121">This Information event indicates that a Windows password change was discarded because it was detected as a duplicate.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="77a14-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="77a14-122">User Action</span></span>  
  
-   <span data-ttu-id="77a14-123">ユーザーの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="77a14-123">No user action is necessary.</span></span>  
  
 <span data-ttu-id="77a14-124">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77a14-124">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="77a14-125">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="77a14-125">Password Synchronization</span></span>](../core/password-synchronization2.md)