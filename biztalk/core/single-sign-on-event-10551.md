---
title: 'シングル サインオン: イベント 10551 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33434989-08d8-4d13-a3cc-4c5543add69c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a014d9fa9adec99a05eba3f4a0f17047e2e1175
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973491"
---
# <a name="single-sign-on-event-10551"></a><span data-ttu-id="4cd73-102">シングル サインオン: イベント 10551</span><span class="sxs-lookup"><span data-stu-id="4cd73-102">Single Sign-On: Event 10551</span></span>
## <a name="details"></a><span data-ttu-id="4cd73-103">詳細</span><span class="sxs-lookup"><span data-stu-id="4cd73-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="4cd73-104">製品名</span><span class="sxs-lookup"><span data-stu-id="4cd73-104">Product Name</span></span>   |                                                                                                   <span data-ttu-id="4cd73-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="4cd73-105">Enterprise Single Sign-On</span></span>                                                                                                   |
| <span data-ttu-id="4cd73-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4cd73-106">Product Version</span></span> |                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                   |
|    <span data-ttu-id="4cd73-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4cd73-107">Event ID</span></span>     |                                                                                                             <span data-ttu-id="4cd73-108">10551</span><span class="sxs-lookup"><span data-stu-id="4cd73-108">10551</span></span>                                                                                                             |
|  <span data-ttu-id="4cd73-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4cd73-109">Event Source</span></span>   |                                                                                                            <span data-ttu-id="4cd73-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4cd73-110">ENTSSO</span></span>                                                                                                             |
|    <span data-ttu-id="4cd73-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4cd73-111">Component</span></span>    |                                                                                                              <span data-ttu-id="4cd73-112">なし</span><span class="sxs-lookup"><span data-stu-id="4cd73-112">N/A</span></span>                                                                                                              |
|  <span data-ttu-id="4cd73-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4cd73-113">Symbolic Name</span></span>  |                                                                                                     <span data-ttu-id="4cd73-114">SSO_WARN_INVALID_USER</span><span class="sxs-lookup"><span data-stu-id="4cd73-114">SSO_WARN_INVALID_USER</span></span>                                                                                                     |
|  <span data-ttu-id="4cd73-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4cd73-115">Message Text</span></span>   | <span data-ttu-id="4cd73-116">指定したユーザーがこのアプリケーションで有効ではないため、マッピングを作成できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="4cd73-116">A mapping could not be created because the specified user is not valid for this application.%r</span></span><br /><br /> <span data-ttu-id="4cd73-117">ドメイン名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="4cd73-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="4cd73-118">ユーザー名: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="4cd73-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="4cd73-119">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="4cd73-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="4cd73-120">アプリケーション ユーザー: %4</span><span class="sxs-lookup"><span data-stu-id="4cd73-120">Application Users: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="4cd73-121">説明</span><span class="sxs-lookup"><span data-stu-id="4cd73-121">Explanation</span></span>  
 <span data-ttu-id="4cd73-122">指定されたユーザーが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="4cd73-122">The specified user is not valid.</span></span> <span data-ttu-id="4cd73-123">これは入力の誤りである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4cd73-123">This could be a typing error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4cd73-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4cd73-124">User Action</span></span>  
 <span data-ttu-id="4cd73-125">警告情報に示されているユーザー名を調べて正しいことを確認し、マッピングを再作成します。</span><span class="sxs-lookup"><span data-stu-id="4cd73-125">Check the User Name listed in the warning information, confirm that it is correct, and then create the mapping again.</span></span>