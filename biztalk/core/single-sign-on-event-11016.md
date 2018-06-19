---
title: 'シングル サインオン: イベント 11016 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3963b706-168d-438d-a068-637f8a6b7b0c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f84bfef5dcef8e28bb3616ce30f1addc77f240c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276530"
---
# <a name="single-sign-on-event-11016"></a><span data-ttu-id="0254d-102">シングル サインオン: イベント 11016</span><span class="sxs-lookup"><span data-stu-id="0254d-102">Single Sign-On: Event 11016</span></span>
## <a name="details"></a><span data-ttu-id="0254d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0254d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0254d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0254d-104">Product Name</span></span>|<span data-ttu-id="0254d-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="0254d-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="0254d-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0254d-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="0254d-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0254d-107">Event ID</span></span>|<span data-ttu-id="0254d-108">11016</span><span class="sxs-lookup"><span data-stu-id="0254d-108">11016</span></span>|  
|<span data-ttu-id="0254d-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0254d-109">Event Source</span></span>|<span data-ttu-id="0254d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0254d-110">ENTSSO</span></span>|  
|<span data-ttu-id="0254d-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0254d-111">Component</span></span>|<span data-ttu-id="0254d-112">なし</span><span class="sxs-lookup"><span data-stu-id="0254d-112">N/A</span></span>|  
|<span data-ttu-id="0254d-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0254d-113">Symbolic Name</span></span>|<span data-ttu-id="0254d-114">RPC 拡張エラー情報%r</span><span class="sxs-lookup"><span data-stu-id="0254d-114">RPC EXTENDED ERROR INFORMATION%r</span></span>|  
|<span data-ttu-id="0254d-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0254d-115">Message Text</span></span>|<span data-ttu-id="0254d-116">%1%r</span><span class="sxs-lookup"><span data-stu-id="0254d-116">%1%r</span></span><br /><br /> <span data-ttu-id="0254d-117">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="0254d-117">Error Code: %2</span></span><br /><br /> <span data-ttu-id="0254d-118">AuthzInitializeContextFromSid 関数が ERROR_ACCESS_DENIED で失敗しました。</span><span class="sxs-lookup"><span data-stu-id="0254d-118">The AuthzInitializeContextFromSid function failed with ERROR_ACCESS_DENIED.</span></span> <span data-ttu-id="0254d-119">これは、SSO サーバーが実行されているサービス アカウントに、Active Directory 内のグループ メンバーシップを確認するのに十分なアクセス許可がないことを意味しています。</span><span class="sxs-lookup"><span data-stu-id="0254d-119">This means that the service account that the SSO server is running under does not have sufficient permissions to check group membership in Active Directory.</span></span> <span data-ttu-id="0254d-120">この問題の修正方法については、ドキュメントを確認してください。%r</span><span class="sxs-lookup"><span data-stu-id="0254d-120">Please check your documentation for details on how to fix this problem.%r</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0254d-121">説明</span><span class="sxs-lookup"><span data-stu-id="0254d-121">Explanation</span></span>  
 <span data-ttu-id="0254d-122">SSO サーバーが実行されているサービス アカウントに、Active Directory 内のグループ メンバーシップを確認するのに十分なアクセス許可がないことを意味しています。</span><span class="sxs-lookup"><span data-stu-id="0254d-122">The service account that the SSO server is running under does not have sufficient permissions to check group membership in Active Directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0254d-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0254d-123">User Action</span></span>  
 <span data-ttu-id="0254d-124">参照してください[SSO サーバー](../core/sso-server.md) SSO のドキュメントにします。</span><span class="sxs-lookup"><span data-stu-id="0254d-124">See [SSO Server](../core/sso-server.md) in the SSO documentation.</span></span>