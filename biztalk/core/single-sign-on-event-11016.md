---
title: 'シングル サインオン: イベント 11016 |Microsoft Docs'
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
ms.openlocfilehash: 96f39cba26da1b3e03c7259643c3dcf2704bbdf3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974515"
---
# <a name="single-sign-on-event-11016"></a><span data-ttu-id="a01be-102">シングル サインオン: イベント 11016</span><span class="sxs-lookup"><span data-stu-id="a01be-102">Single Sign-On: Event 11016</span></span>
## <a name="details"></a><span data-ttu-id="a01be-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a01be-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a01be-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a01be-104">Product Name</span></span>   |                                                                                                                                                                   <span data-ttu-id="a01be-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="a01be-105">Enterprise Single Sign-On</span></span>                                                                                                                                                                    |
| <span data-ttu-id="a01be-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a01be-106">Product Version</span></span> |                                                                                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                   |
|    <span data-ttu-id="a01be-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a01be-107">Event ID</span></span>     |                                                                                                                                                                             <span data-ttu-id="a01be-108">11016</span><span class="sxs-lookup"><span data-stu-id="a01be-108">11016</span></span>                                                                                                                                                                              |
|  <span data-ttu-id="a01be-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a01be-109">Event Source</span></span>   |                                                                                                                                                                             <span data-ttu-id="a01be-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a01be-110">ENTSSO</span></span>                                                                                                                                                                             |
|    <span data-ttu-id="a01be-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a01be-111">Component</span></span>    |                                                                                                                                                                              <span data-ttu-id="a01be-112">なし</span><span class="sxs-lookup"><span data-stu-id="a01be-112">N/A</span></span>                                                                                                                                                                               |
|  <span data-ttu-id="a01be-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a01be-113">Symbolic Name</span></span>  |                                                                                                                                                                <span data-ttu-id="a01be-114">RPC 拡張エラー情報%r</span><span class="sxs-lookup"><span data-stu-id="a01be-114">RPC EXTENDED ERROR INFORMATION%r</span></span>                                                                                                                                                                |
|  <span data-ttu-id="a01be-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a01be-115">Message Text</span></span>   | <span data-ttu-id="a01be-116">%1%r</span><span class="sxs-lookup"><span data-stu-id="a01be-116">%1%r</span></span><br /><br /> <span data-ttu-id="a01be-117">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="a01be-117">Error Code: %2</span></span><br /><br /> <span data-ttu-id="a01be-118">AuthzInitializeContextFromSid 関数が ERROR_ACCESS_DENIED で失敗しました。</span><span class="sxs-lookup"><span data-stu-id="a01be-118">The AuthzInitializeContextFromSid function failed with ERROR_ACCESS_DENIED.</span></span> <span data-ttu-id="a01be-119">これは、SSO サーバーが実行されているサービス アカウントに、Active Directory 内のグループ メンバーシップを確認するのに十分なアクセス許可がないことを意味しています。</span><span class="sxs-lookup"><span data-stu-id="a01be-119">This means that the service account that the SSO server is running under does not have sufficient permissions to check group membership in Active Directory.</span></span> <span data-ttu-id="a01be-120">この問題の修正方法については、ドキュメントを確認してください。%r</span><span class="sxs-lookup"><span data-stu-id="a01be-120">Please check your documentation for details on how to fix this problem.%r</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="a01be-121">説明</span><span class="sxs-lookup"><span data-stu-id="a01be-121">Explanation</span></span>  
 <span data-ttu-id="a01be-122">SSO サーバーが実行されているサービス アカウントに、Active Directory 内のグループ メンバーシップを確認するのに十分なアクセス許可がないことを意味しています。</span><span class="sxs-lookup"><span data-stu-id="a01be-122">The service account that the SSO server is running under does not have sufficient permissions to check group membership in Active Directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a01be-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a01be-123">User Action</span></span>  
 <span data-ttu-id="a01be-124">参照してください[SSO サーバー](../core/sso-server.md) SSO ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="a01be-124">See [SSO Server](../core/sso-server.md) in the SSO documentation.</span></span>