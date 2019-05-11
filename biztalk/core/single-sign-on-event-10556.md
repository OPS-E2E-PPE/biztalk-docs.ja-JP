---
title: シングル サインオン:イベント 10556 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66661a77-e8b0-4972-a3bc-4bb717967699
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30e2f3f8e76f5b2b18aca176dfee1d77c7b1ff1f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398833"
---
# <a name="single-sign-on-event-10556"></a><span data-ttu-id="bae4e-102">シングル サインオン:イベント 10556</span><span class="sxs-lookup"><span data-stu-id="bae4e-102">Single Sign-On: Event 10556</span></span>
## <a name="details"></a><span data-ttu-id="bae4e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bae4e-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                   |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="bae4e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bae4e-104">Product Name</span></span>   |                                                                                                                             <span data-ttu-id="bae4e-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="bae4e-105">Enterprise Single Sign-On</span></span>                                                                                                                             |
| <span data-ttu-id="bae4e-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bae4e-106">Product Version</span></span> |                                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                             |
|    <span data-ttu-id="bae4e-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bae4e-107">Event ID</span></span>     |                                                                                                                                       <span data-ttu-id="bae4e-108">10556</span><span class="sxs-lookup"><span data-stu-id="bae4e-108">10556</span></span>                                                                                                                                       |
|  <span data-ttu-id="bae4e-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bae4e-109">Event Source</span></span>   |                                                                                                                                      <span data-ttu-id="bae4e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bae4e-110">ENTSSO</span></span>                                                                                                                                       |
|    <span data-ttu-id="bae4e-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bae4e-111">Component</span></span>    |                                                                                                                                        <span data-ttu-id="bae4e-112">なし</span><span class="sxs-lookup"><span data-stu-id="bae4e-112">N/A</span></span>                                                                                                                                        |
|  <span data-ttu-id="bae4e-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bae4e-113">Symbolic Name</span></span>  |                                                                                                                            <span data-ttu-id="bae4e-114">SSO_WARN_INVALID_GROUP_USER</span><span class="sxs-lookup"><span data-stu-id="bae4e-114">SSO_WARN_INVALID_GROUP_USER</span></span>                                                                                                                            |
|  <span data-ttu-id="bae4e-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bae4e-115">Message Text</span></span>   | <span data-ttu-id="bae4e-116">グループ アプリケーションの指定されたマッピングが無効です。</span><span class="sxs-lookup"><span data-stu-id="bae4e-116">The mapping specified for a Group application is not valid.</span></span> <span data-ttu-id="bae4e-117">マッピングは、この application.%r アプリケーション ユーザー アカウントのいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bae4e-117">The mapping must specify one of the Application Users accounts for this application.%r</span></span><br /><br /> <span data-ttu-id="bae4e-118">ドメイン名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="bae4e-118">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="bae4e-119">ユーザー名: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="bae4e-119">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="bae4e-120">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="bae4e-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="bae4e-121">アプリケーション ユーザー: %4</span><span class="sxs-lookup"><span data-stu-id="bae4e-121">Application Users: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="bae4e-122">説明</span><span class="sxs-lookup"><span data-stu-id="bae4e-122">Explanation</span></span>  
 <span data-ttu-id="bae4e-123">マッピングが無効です。</span><span class="sxs-lookup"><span data-stu-id="bae4e-123">The mapping is not valid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bae4e-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bae4e-124">User Action</span></span>  
 <span data-ttu-id="bae4e-125">マッピングが、このアプリケーションのアプリケーション ユーザー アカウントのいずれかを指定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="bae4e-125">Check that the mapping specifies one of the Application User accounts for this application.</span></span>