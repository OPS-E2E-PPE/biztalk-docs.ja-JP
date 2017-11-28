---
title: "シングル サインオン: イベント 11022 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c65ca12b-dda8-408b-9512-39df6f8e035b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccae36e9beef672e6c5fb7917c88341ce4bb3c08
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11022"></a><span data-ttu-id="ccc18-102">シングル サインオン: イベント 11022</span><span class="sxs-lookup"><span data-stu-id="ccc18-102">Single Sign-On: Event 11022</span></span>
## <a name="details"></a><span data-ttu-id="ccc18-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ccc18-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ccc18-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ccc18-104">Product Name</span></span>|<span data-ttu-id="ccc18-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="ccc18-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="ccc18-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ccc18-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="ccc18-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ccc18-107">Event ID</span></span>|<span data-ttu-id="ccc18-108">11022</span><span class="sxs-lookup"><span data-stu-id="ccc18-108">11022</span></span>|  
|<span data-ttu-id="ccc18-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ccc18-109">Event Source</span></span>|<span data-ttu-id="ccc18-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ccc18-110">ENTSSO</span></span>|  
|<span data-ttu-id="ccc18-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ccc18-111">Component</span></span>|<span data-ttu-id="ccc18-112">なし</span><span class="sxs-lookup"><span data-stu-id="ccc18-112">N/A</span></span>|  
|<span data-ttu-id="ccc18-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ccc18-113">Symbolic Name</span></span>|<span data-ttu-id="ccc18-114">SSO_WARN_EXTERNAL_TO_EXTERNAL_MAPPING_CONFLICT_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="ccc18-114">SSO_WARN_EXTERNAL_TO_EXTERNAL_MAPPING_CONFLICT_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="ccc18-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ccc18-115">Message Text</span></span>|<span data-ttu-id="ccc18-116">外部パスワード変更により、異なる外部アカウントが変更される可能性がありました。%r</span><span class="sxs-lookup"><span data-stu-id="ccc18-116">An external password change would have caused a different external account to be changed.%r</span></span><br /><br /> <span data-ttu-id="ccc18-117">この外部システムのアダプターは、マッピングの競合を許可しないよう構成されているため、実行できません。%r</span><span class="sxs-lookup"><span data-stu-id="ccc18-117">This has been prevented because the adapter for this external system is configured to not allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="ccc18-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ccc18-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="ccc18-119">アダプター: %2 %r</span><span class="sxs-lookup"><span data-stu-id="ccc18-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="ccc18-120">Windows アカウント: %3 %r</span><span class="sxs-lookup"><span data-stu-id="ccc18-120">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="ccc18-121">外部アカウント 1: %4 %r</span><span class="sxs-lookup"><span data-stu-id="ccc18-121">External Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="ccc18-122">外部アカウント 2: %5</span><span class="sxs-lookup"><span data-stu-id="ccc18-122">External Account 2: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ccc18-123">説明</span><span class="sxs-lookup"><span data-stu-id="ccc18-123">Explanation</span></span>  
 <span data-ttu-id="ccc18-124">これは、別の外部アカウントを変更する可能性があった外部パスワード変更の失敗を通知する情報メッセージです。</span><span class="sxs-lookup"><span data-stu-id="ccc18-124">This is an informational message reporting the failure of an external password change which would have caused a different external account to be changed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ccc18-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ccc18-125">User Action</span></span>  
 <span data-ttu-id="ccc18-126">変更は行われませんでしたが (このシステムはマッピングの競合を許可しないように構成されているため)、この試みが事前にわかっていて承認したものであることを直ちに確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccc18-126">Although no change was made (because this system is configured to not allow mapping conflicts) you should confirm immediately that this attempt was made with your knowledge and authorization.</span></span> <span data-ttu-id="ccc18-127">そうである場合は、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ccc18-127">If so, no action is required.</span></span> <span data-ttu-id="ccc18-128">そうでなかった場合は、この変更がどこで行われたのかを調べ、システム内の安全な場所であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ccc18-128">If not, find out where the change initiated, and confirm that it was a location safely within the system.</span></span>