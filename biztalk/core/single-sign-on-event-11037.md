---
title: 'シングル サインオン: イベント 11037 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b523ff56-112e-4798-97d2-b1b19e130ec7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ceec837a53d4cad3c236373a907497795efbd12a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998899"
---
# <a name="single-sign-on-event-11037"></a><span data-ttu-id="d52ff-102">シングル サインオン: イベント 11037</span><span class="sxs-lookup"><span data-stu-id="d52ff-102">Single Sign-On: Event 11037</span></span>
## <a name="details"></a><span data-ttu-id="d52ff-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d52ff-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d52ff-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d52ff-104">Product Name</span></span>   |                                                                                                               <span data-ttu-id="d52ff-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d52ff-105">Enterprise Single Sign-On</span></span>                                                                                                               |
| <span data-ttu-id="d52ff-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d52ff-106">Product Version</span></span> |                                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                               |
|    <span data-ttu-id="d52ff-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d52ff-107">Event ID</span></span>     |                                                                                                                         <span data-ttu-id="d52ff-108">11037</span><span class="sxs-lookup"><span data-stu-id="d52ff-108">11037</span></span>                                                                                                                         |
|  <span data-ttu-id="d52ff-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d52ff-109">Event Source</span></span>   |                                                                                                                        <span data-ttu-id="d52ff-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d52ff-110">ENTSSO</span></span>                                                                                                                         |
|    <span data-ttu-id="d52ff-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d52ff-111">Component</span></span>    |                                                                                                                          <span data-ttu-id="d52ff-112">なし</span><span class="sxs-lookup"><span data-stu-id="d52ff-112">N/A</span></span>                                                                                                                          |
|  <span data-ttu-id="d52ff-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d52ff-113">Symbolic Name</span></span>  |                                                                                                              <span data-ttu-id="d52ff-114">SSO_INFO_PS_MAPPING_INVALID</span><span class="sxs-lookup"><span data-stu-id="d52ff-114">SSO_INFO_PS_MAPPING_INVALID</span></span>                                                                                                              |
|  <span data-ttu-id="d52ff-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d52ff-115">Message Text</span></span>   | <span data-ttu-id="d52ff-116">外部パスワードが変更されています。</span><span class="sxs-lookup"><span data-stu-id="d52ff-116">External password change.</span></span> <span data-ttu-id="d52ff-117">マッピングが有効ではなくなっているため、外部アカウントのパスワードは変更されませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="d52ff-117">The password was not changed for the external account because the mapping is no longer valid.%r</span></span><br /><br /> <span data-ttu-id="d52ff-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d52ff-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="d52ff-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="d52ff-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="d52ff-120">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="d52ff-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="d52ff-121">外部アカウント: %4</span><span class="sxs-lookup"><span data-stu-id="d52ff-121">External Account: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d52ff-122">説明</span><span class="sxs-lookup"><span data-stu-id="d52ff-122">Explanation</span></span>  
 <span data-ttu-id="d52ff-123">マッピングがアプリケーション ユーザー グループに含まれなくなっています。</span><span class="sxs-lookup"><span data-stu-id="d52ff-123">The mapping is no longer a part of the Application Users group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d52ff-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d52ff-124">User Action</span></span>  
 <span data-ttu-id="d52ff-125">このメッセージには、外部アカウントとアプリケーションの名前が示されます。</span><span class="sxs-lookup"><span data-stu-id="d52ff-125">The message lists the name of the external account and application.</span></span> <span data-ttu-id="d52ff-126">この情報を使用して、マッピングが有効ではなくなった理由を調べます。</span><span class="sxs-lookup"><span data-stu-id="d52ff-126">You can use this information to find out why the mapping is no longer valid.</span></span>