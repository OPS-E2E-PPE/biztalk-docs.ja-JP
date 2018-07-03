---
title: 'シングル サインオン: イベント 11057 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e165e24-fe43-4899-ab6e-1437f639f534
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bce17e6659867d8bcf8c39408ec24d8e79052aa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967659"
---
# <a name="single-sign-on-event-11057"></a><span data-ttu-id="014c3-102">シングル サインオン: イベント 11057</span><span class="sxs-lookup"><span data-stu-id="014c3-102">Single Sign-On: Event 11057</span></span>
## <a name="details"></a><span data-ttu-id="014c3-103">詳細</span><span class="sxs-lookup"><span data-stu-id="014c3-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="014c3-104">製品名</span><span class="sxs-lookup"><span data-stu-id="014c3-104">Product Name</span></span>   |                                                                                                                <span data-ttu-id="014c3-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="014c3-105">Enterprise Single Sign-On</span></span>                                                                                                                |
| <span data-ttu-id="014c3-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="014c3-106">Product Version</span></span> |                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                |
|    <span data-ttu-id="014c3-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="014c3-107">Event ID</span></span>     |                                                                                                                          <span data-ttu-id="014c3-108">11057</span><span class="sxs-lookup"><span data-stu-id="014c3-108">11057</span></span>                                                                                                                          |
|  <span data-ttu-id="014c3-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="014c3-109">Event Source</span></span>   |                                                                                                                         <span data-ttu-id="014c3-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="014c3-110">ENTSSO</span></span>                                                                                                                          |
|    <span data-ttu-id="014c3-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="014c3-111">Component</span></span>    |                                                                                                                           <span data-ttu-id="014c3-112">なし</span><span class="sxs-lookup"><span data-stu-id="014c3-112">N/A</span></span>                                                                                                                           |
|  <span data-ttu-id="014c3-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="014c3-113">Symbolic Name</span></span>  |                                                                                                        <span data-ttu-id="014c3-114">SSO_WARN_PS_DIRECT_MISSING_INITIAL_CREDS</span><span class="sxs-lookup"><span data-stu-id="014c3-114">SSO_WARN_PS_DIRECT_MISSING_INITIAL_CREDS</span></span>                                                                                                         |
|  <span data-ttu-id="014c3-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="014c3-115">Message Text</span></span>   | <span data-ttu-id="014c3-116">直接パスワード変更。</span><span class="sxs-lookup"><span data-stu-id="014c3-116">Direct password change.</span></span> <span data-ttu-id="014c3-117">このマッピングで不足する外部資格情報フィールドの一部は既定値に設定されています。%r</span><span class="sxs-lookup"><span data-stu-id="014c3-117">Some missing external credential fields for this mapping have been set to default values.%r</span></span><br /><br /> <span data-ttu-id="014c3-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="014c3-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="014c3-119">アプリケーション名: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="014c3-119">Application Name: %2%r</span></span><br /><br /> <span data-ttu-id="014c3-120">Windows アカウント: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="014c3-120">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="014c3-121">外部アカウント: %4</span><span class="sxs-lookup"><span data-stu-id="014c3-121">External Account: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="014c3-122">説明</span><span class="sxs-lookup"><span data-stu-id="014c3-122">Explanation</span></span>  
 <span data-ttu-id="014c3-123">直接パスワード同期を使用してパスワードを変更できますが、この機能は外部資格情報フィールドを 1 つだけサポートしています。</span><span class="sxs-lookup"><span data-stu-id="014c3-123">While it is possible to change passwords using Direct Password Sync, this feature only supports one external credential field.</span></span> <span data-ttu-id="014c3-124">この場合、ENTSSO システムで複数の外部資格情報フィールドが検出されたため、これらのフィールドは既定 (空白) 値に設定されました。</span><span class="sxs-lookup"><span data-stu-id="014c3-124">In this case the ENTSSO System has encountered more than one external credential field, and has set those fields to default (blank) values.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="014c3-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="014c3-125">User Action</span></span>  
 <span data-ttu-id="014c3-126">ユーザーの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="014c3-126">No user action is necessary.</span></span>