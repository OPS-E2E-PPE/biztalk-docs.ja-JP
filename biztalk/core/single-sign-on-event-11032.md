---
title: 'シングル サインオン: イベント 11032 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d58cf9d-6806-4580-8014-7eff88d5cc5f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4dc69ecf447f0917f843a0f80a0a25b1ed0b6e0a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022048"
---
# <a name="single-sign-on-event-11032"></a><span data-ttu-id="9638c-102">シングル サインオン: イベント 11032</span><span class="sxs-lookup"><span data-stu-id="9638c-102">Single Sign-On: Event 11032</span></span>
## <a name="details"></a><span data-ttu-id="9638c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9638c-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                  |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="9638c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9638c-104">Product Name</span></span>   |                                                                                                                            <span data-ttu-id="9638c-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="9638c-105">Enterprise Single Sign-On</span></span>                                                                                                                             |
| <span data-ttu-id="9638c-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9638c-106">Product Version</span></span> |                                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                            |
|    <span data-ttu-id="9638c-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9638c-107">Event ID</span></span>     |                                                                                                                                      <span data-ttu-id="9638c-108">11032</span><span class="sxs-lookup"><span data-stu-id="9638c-108">11032</span></span>                                                                                                                                       |
|  <span data-ttu-id="9638c-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9638c-109">Event Source</span></span>   |                                                                                                                                      <span data-ttu-id="9638c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9638c-110">ENTSSO</span></span>                                                                                                                                      |
|    <span data-ttu-id="9638c-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9638c-111">Component</span></span>    |                                                                                                                                       <span data-ttu-id="9638c-112">なし</span><span class="sxs-lookup"><span data-stu-id="9638c-112">N/A</span></span>                                                                                                                                        |
|  <span data-ttu-id="9638c-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9638c-113">Symbolic Name</span></span>  |                                                                                                                     <span data-ttu-id="9638c-114">SSO_INFO_PS_WIN_CHANGE_MAPPING_DISABLED</span><span class="sxs-lookup"><span data-stu-id="9638c-114">SSO_INFO_PS_WIN_CHANGE_MAPPING_DISABLED</span></span>                                                                                                                      |
|  <span data-ttu-id="9638c-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9638c-115">Message Text</span></span>   | <span data-ttu-id="9638c-116">Windows パスワードが変更されています。</span><span class="sxs-lookup"><span data-stu-id="9638c-116">Windows password change.</span></span> <span data-ttu-id="9638c-117">この Windows アカウントのマッピングが検出されましたが、無効になっているために無視されました。%r</span><span class="sxs-lookup"><span data-stu-id="9638c-117">A mapping for this Windows account has been detected but ignored because it is disabled.%r</span></span><br /><br /> <span data-ttu-id="9638c-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="9638c-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="9638c-119">Windows アカウント: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="9638c-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="9638c-120">アプリケーションの場合: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="9638c-120">Application: %3%r</span></span><br /><br /> <span data-ttu-id="9638c-121">外部アカウント: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="9638c-121">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="9638c-122">クライアント ユーザー: %5</span><span class="sxs-lookup"><span data-stu-id="9638c-122">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="9638c-123">説明</span><span class="sxs-lookup"><span data-stu-id="9638c-123">Explanation</span></span>  
 <span data-ttu-id="9638c-124">この Windows アカウントのマッピングが検出されましたが、無効になっているために無視されました。</span><span class="sxs-lookup"><span data-stu-id="9638c-124">A mapping for this Windows account has been detected but ignored because it is disabled.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9638c-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9638c-125">User Action</span></span>  
  
-   <span data-ttu-id="9638c-126">マッピングを有効にするのを参照してください。[ユーザー マッピングを有効にする方法](../core/how-to-enable-a-user-mapping.md)します。</span><span class="sxs-lookup"><span data-stu-id="9638c-126">To enable the mapping, see [How to Enable a User Mapping](../core/how-to-enable-a-user-mapping.md).</span></span>