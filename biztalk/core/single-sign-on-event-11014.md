---
title: 'シングル サインオン: イベント 11014 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71e4c9bd-8bda-46ca-9e76-f7b4fa033167
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e86642a7f62b53d45f20e140131d6a12d0771ec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001137"
---
# <a name="single-sign-on-event-11014"></a><span data-ttu-id="d0c93-102">シングル サインオン: イベント 11014</span><span class="sxs-lookup"><span data-stu-id="d0c93-102">Single Sign-On: Event 11014</span></span>
## <a name="details"></a><span data-ttu-id="d0c93-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d0c93-103">Details</span></span>  
  
|                 |                                                                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d0c93-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d0c93-104">Product Name</span></span>   |                                                                <span data-ttu-id="d0c93-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d0c93-105">Enterprise Single Sign-On</span></span>                                                                 |
| <span data-ttu-id="d0c93-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d0c93-106">Product Version</span></span> |                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                |
|    <span data-ttu-id="d0c93-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d0c93-107">Event ID</span></span>     |                                                                          <span data-ttu-id="d0c93-108">11014</span><span class="sxs-lookup"><span data-stu-id="d0c93-108">11014</span></span>                                                                           |
|  <span data-ttu-id="d0c93-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d0c93-109">Event Source</span></span>   |                                                                          <span data-ttu-id="d0c93-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d0c93-110">ENTSSO</span></span>                                                                          |
|    <span data-ttu-id="d0c93-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d0c93-111">Component</span></span>    |                                                                           <span data-ttu-id="d0c93-112">なし</span><span class="sxs-lookup"><span data-stu-id="d0c93-112">N/A</span></span>                                                                            |
|  <span data-ttu-id="d0c93-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d0c93-113">Symbolic Name</span></span>  |                                                                  <span data-ttu-id="d0c93-114">SSO_ERROR_ACCESS_CHECK</span><span class="sxs-lookup"><span data-stu-id="d0c93-114">SSO_ERROR_ACCESS_CHECK</span></span>                                                                  |
|  <span data-ttu-id="d0c93-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d0c93-115">Message Text</span></span>   | <span data-ttu-id="d0c93-116">アクセス確認が失敗しました。%r</span><span class="sxs-lookup"><span data-stu-id="d0c93-116">Access check failed.%r</span></span><br /><br /> <span data-ttu-id="d0c93-117">クライアント ユーザー: %1\\% 2 %r</span><span class="sxs-lookup"><span data-stu-id="d0c93-117">Client User: %1\\%2%r</span></span><br /><br /> <span data-ttu-id="d0c93-118">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="d0c93-118">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="d0c93-119">追加データ: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="d0c93-119">Additional Data: %4%r</span></span><br /><br /> <span data-ttu-id="d0c93-120">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="d0c93-120">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d0c93-121">説明</span><span class="sxs-lookup"><span data-stu-id="d0c93-121">Explanation</span></span>  
 <span data-ttu-id="d0c93-122">表示されたクライアントおよびアプリケーションについてアクセス確認が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="d0c93-122">The access check failed for the client and application listed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d0c93-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d0c93-123">User Action</span></span>  
 <span data-ttu-id="d0c93-124">追加情報によって、問題を解決できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d0c93-124">The additional information should enable you to fix the problem.</span></span> <span data-ttu-id="d0c93-125">今後、このエラーを回避するために、監査レベルを低くすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d0c93-125">To avoid this error in the future, you can also lower the audit level.</span></span>