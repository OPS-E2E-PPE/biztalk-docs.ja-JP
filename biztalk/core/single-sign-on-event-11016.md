---
title: シングル サインオン:イベント 11016 |Microsoft Docs
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
ms.openlocfilehash: 01bf4d34a68680b391e49b465e44138fca81b210
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267074"
---
# <a name="single-sign-on-event-11016"></a><span data-ttu-id="6832f-102">シングル サインオン:イベント 11016</span><span class="sxs-lookup"><span data-stu-id="6832f-102">Single Sign-On: Event 11016</span></span>
## <a name="details"></a><span data-ttu-id="6832f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6832f-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="6832f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6832f-104">Product Name</span></span>   |                                                                                                                                                                   <span data-ttu-id="6832f-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="6832f-105">Enterprise Single Sign-On</span></span>                                                                                                                                                                    |
| <span data-ttu-id="6832f-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6832f-106">Product Version</span></span> |                                                                                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                   |
|    <span data-ttu-id="6832f-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6832f-107">Event ID</span></span>     |                                                                                                                                                                             <span data-ttu-id="6832f-108">11016</span><span class="sxs-lookup"><span data-stu-id="6832f-108">11016</span></span>                                                                                                                                                                              |
|  <span data-ttu-id="6832f-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6832f-109">Event Source</span></span>   |                                                                                                                                                                             <span data-ttu-id="6832f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6832f-110">ENTSSO</span></span>                                                                                                                                                                             |
|    <span data-ttu-id="6832f-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6832f-111">Component</span></span>    |                                                                                                                                                                              <span data-ttu-id="6832f-112">なし</span><span class="sxs-lookup"><span data-stu-id="6832f-112">N/A</span></span>                                                                                                                                                                               |
|  <span data-ttu-id="6832f-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6832f-113">Symbolic Name</span></span>  |                                                                                                                                                                <span data-ttu-id="6832f-114">RPC 拡張エラー情報 %r</span><span class="sxs-lookup"><span data-stu-id="6832f-114">RPC EXTENDED ERROR INFORMATION%r</span></span>                                                                                                                                                                |
|  <span data-ttu-id="6832f-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6832f-115">Message Text</span></span>   | <span data-ttu-id="6832f-116">% 1 %r</span><span class="sxs-lookup"><span data-stu-id="6832f-116">%1%r</span></span><br /><br /> <span data-ttu-id="6832f-117">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="6832f-117">Error Code: %2</span></span><br /><br /> <span data-ttu-id="6832f-118">AuthzInitializeContextFromSid 関数は、ERROR_ACCESS_DENIED で失敗しました。</span><span class="sxs-lookup"><span data-stu-id="6832f-118">The AuthzInitializeContextFromSid function failed with ERROR_ACCESS_DENIED.</span></span> <span data-ttu-id="6832f-119">これは、SSO サーバーが実行されているサービス アカウントに Active Directory でグループ メンバーシップを確認するための十分なアクセス許可がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="6832f-119">This means that the service account that the SSO server is running under does not have sufficient permissions to check group membership in Active Directory.</span></span> <span data-ttu-id="6832f-120">この problem.%r を修正する方法の詳細について、ドキュメントを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6832f-120">Please check your documentation for details on how to fix this problem.%r</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="6832f-121">説明</span><span class="sxs-lookup"><span data-stu-id="6832f-121">Explanation</span></span>  
 <span data-ttu-id="6832f-122">SSO サーバーが実行されているサービス アカウントには、Active Directory でグループ メンバーシップを確認するための十分なアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="6832f-122">The service account that the SSO server is running under does not have sufficient permissions to check group membership in Active Directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6832f-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6832f-123">User Action</span></span>  
 <span data-ttu-id="6832f-124">参照してください[SSO サーバー](../core/sso-server.md) SSO ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="6832f-124">See [SSO Server](../core/sso-server.md) in the SSO documentation.</span></span>