---
title: シングル サインオン:イベント 11037 |Microsoft Docs
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
ms.openlocfilehash: 6d64605fbdd4cb470fc6dec060650bd78b581f84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401030"
---
# <a name="single-sign-on-event-11037"></a><span data-ttu-id="3c970-102">シングル サインオン:イベント 11037</span><span class="sxs-lookup"><span data-stu-id="3c970-102">Single Sign-On: Event 11037</span></span>
## <a name="details"></a><span data-ttu-id="3c970-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3c970-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3c970-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3c970-104">Product Name</span></span>   |                                                                                                               <span data-ttu-id="3c970-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="3c970-105">Enterprise Single Sign-On</span></span>                                                                                                               |
| <span data-ttu-id="3c970-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3c970-106">Product Version</span></span> |                                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                               |
|    <span data-ttu-id="3c970-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3c970-107">Event ID</span></span>     |                                                                                                                         <span data-ttu-id="3c970-108">11037</span><span class="sxs-lookup"><span data-stu-id="3c970-108">11037</span></span>                                                                                                                         |
|  <span data-ttu-id="3c970-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3c970-109">Event Source</span></span>   |                                                                                                                        <span data-ttu-id="3c970-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3c970-110">ENTSSO</span></span>                                                                                                                         |
|    <span data-ttu-id="3c970-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3c970-111">Component</span></span>    |                                                                                                                          <span data-ttu-id="3c970-112">なし</span><span class="sxs-lookup"><span data-stu-id="3c970-112">N/A</span></span>                                                                                                                          |
|  <span data-ttu-id="3c970-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3c970-113">Symbolic Name</span></span>  |                                                                                                              <span data-ttu-id="3c970-114">SSO_INFO_PS_MAPPING_INVALID</span><span class="sxs-lookup"><span data-stu-id="3c970-114">SSO_INFO_PS_MAPPING_INVALID</span></span>                                                                                                              |
|  <span data-ttu-id="3c970-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3c970-115">Message Text</span></span>   | <span data-ttu-id="3c970-116">外部パスワード変更。</span><span class="sxs-lookup"><span data-stu-id="3c970-116">External password change.</span></span> <span data-ttu-id="3c970-117">マッピングが valid.%r ではなくなったため、外部アカウントのパスワードが変更されませんでした。</span><span class="sxs-lookup"><span data-stu-id="3c970-117">The password was not changed for the external account because the mapping is no longer valid.%r</span></span><br /><br /> <span data-ttu-id="3c970-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="3c970-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="3c970-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="3c970-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="3c970-120">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="3c970-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="3c970-121">外部アカウント: %4</span><span class="sxs-lookup"><span data-stu-id="3c970-121">External Account: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="3c970-122">説明</span><span class="sxs-lookup"><span data-stu-id="3c970-122">Explanation</span></span>  
 <span data-ttu-id="3c970-123">マッピングは、アプリケーション ユーザー グループの一部ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="3c970-123">The mapping is no longer a part of the Application Users group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3c970-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3c970-124">User Action</span></span>  
 <span data-ttu-id="3c970-125">メッセージには、外部アカウントとアプリケーションの名前が一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="3c970-125">The message lists the name of the external account and application.</span></span> <span data-ttu-id="3c970-126">この情報を使用して、理由、マッピングが無効になったを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="3c970-126">You can use this information to find out why the mapping is no longer valid.</span></span>