---
title: 'シングル サインオン: イベント 10557 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f29bc394-4c56-4ded-93a1-004afb3a054a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 612231da7c3098eca4d3cc901b83b66e48e09c9f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997531"
---
# <a name="single-sign-on-event-10557"></a><span data-ttu-id="d39ae-102">シングル サインオン: イベント 10557</span><span class="sxs-lookup"><span data-stu-id="d39ae-102">Single Sign-On: Event 10557</span></span>
## <a name="details"></a><span data-ttu-id="d39ae-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d39ae-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d39ae-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d39ae-104">Product Name</span></span>   |                                                                                        <span data-ttu-id="d39ae-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d39ae-105">Enterprise Single Sign-On</span></span>                                                                                         |
| <span data-ttu-id="d39ae-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d39ae-106">Product Version</span></span> |                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                        |
|    <span data-ttu-id="d39ae-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d39ae-107">Event ID</span></span>     |                                                                                                  <span data-ttu-id="d39ae-108">10557</span><span class="sxs-lookup"><span data-stu-id="d39ae-108">10557</span></span>                                                                                                   |
|  <span data-ttu-id="d39ae-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d39ae-109">Event Source</span></span>   |                                                                                                  <span data-ttu-id="d39ae-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d39ae-110">ENTSSO</span></span>                                                                                                  |
|    <span data-ttu-id="d39ae-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d39ae-111">Component</span></span>    |                                                                                                   <span data-ttu-id="d39ae-112">なし</span><span class="sxs-lookup"><span data-stu-id="d39ae-112">N/A</span></span>                                                                                                    |
|  <span data-ttu-id="d39ae-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d39ae-113">Symbolic Name</span></span>  |                                                                                   <span data-ttu-id="d39ae-114">SSO_WARN_USER_NOT_ALLOWED_FOR_GROUPS</span><span class="sxs-lookup"><span data-stu-id="d39ae-114">SSO_WARN_USER_NOT_ALLOWED_FOR_GROUPS</span></span>                                                                                   |
|  <span data-ttu-id="d39ae-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d39ae-115">Message Text</span></span>   | <span data-ttu-id="d39ae-116">アプリケーション ユーザーはグループ アプリケーションのマッピングの制御を許可されていません。%r</span><span class="sxs-lookup"><span data-stu-id="d39ae-116">Application Users are not allowed to control mappings for Group applications.%r</span></span><br /><br /> <span data-ttu-id="d39ae-117">ドメイン名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d39ae-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="d39ae-118">ユーザー名: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="d39ae-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="d39ae-119">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="d39ae-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="d39ae-120">クライアント ユーザー: %4</span><span class="sxs-lookup"><span data-stu-id="d39ae-120">Client User: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d39ae-121">説明</span><span class="sxs-lookup"><span data-stu-id="d39ae-121">Explanation</span></span>  
 <span data-ttu-id="d39ae-122">アプリケーション ユーザーには、グループ アプリケーションのマッピングを作成または制御するのに十分な特権がありません。</span><span class="sxs-lookup"><span data-stu-id="d39ae-122">An Application User does not have sufficient privileges to create or control mappings for Group applications.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d39ae-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d39ae-123">User Action</span></span>  
 <span data-ttu-id="d39ae-124">このアクティビティはアプリケーション管理者が実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d39ae-124">This activity must be performed by an Application Administrator.</span></span>