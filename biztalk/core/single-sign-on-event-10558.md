---
title: シングル サインオン:イベント 10558 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84637b67-09df-4c1e-b9f2-85a738ba0d7a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7161e732fc95aa2fb62ee2ba5e8f188266804206
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398820"
---
# <a name="single-sign-on-event-10558"></a><span data-ttu-id="5457a-102">シングル サインオン:イベント 10558</span><span class="sxs-lookup"><span data-stu-id="5457a-102">Single Sign-On: Event 10558</span></span>
## <a name="details"></a><span data-ttu-id="5457a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5457a-103">Details</span></span>  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="5457a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5457a-104">Product Name</span></span>   |                                                                                  <span data-ttu-id="5457a-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="5457a-105">Enterprise Single Sign-On</span></span>                                                                                   |
| <span data-ttu-id="5457a-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5457a-106">Product Version</span></span> |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    <span data-ttu-id="5457a-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5457a-107">Event ID</span></span>     |                                                                                            <span data-ttu-id="5457a-108">10558</span><span class="sxs-lookup"><span data-stu-id="5457a-108">10558</span></span>                                                                                             |
|  <span data-ttu-id="5457a-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5457a-109">Event Source</span></span>   |                                                                                            <span data-ttu-id="5457a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5457a-110">ENTSSO</span></span>                                                                                            |
|    <span data-ttu-id="5457a-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5457a-111">Component</span></span>    |                                                                                             <span data-ttu-id="5457a-112">なし</span><span class="sxs-lookup"><span data-stu-id="5457a-112">N/A</span></span>                                                                                              |
|  <span data-ttu-id="5457a-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5457a-113">Symbolic Name</span></span>  |                                                                                  <span data-ttu-id="5457a-114">SSO_WARN_USER_OWN_MAPPINGS</span><span class="sxs-lookup"><span data-stu-id="5457a-114">SSO_WARN_USER_OWN_MAPPINGS</span></span>                                                                                  |
|  <span data-ttu-id="5457a-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5457a-115">Message Text</span></span>   | <span data-ttu-id="5457a-116">アプリケーションのユーザーが独自の mappings.%r を制御するのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="5457a-116">Application Users are only allowed to control their own mappings.%r</span></span><br /><br /> <span data-ttu-id="5457a-117">ドメイン名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="5457a-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="5457a-118">ユーザー名: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="5457a-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="5457a-119">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="5457a-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="5457a-120">クライアント ユーザー: %4</span><span class="sxs-lookup"><span data-stu-id="5457a-120">Client User: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="5457a-121">説明</span><span class="sxs-lookup"><span data-stu-id="5457a-121">Explanation</span></span>  
 <span data-ttu-id="5457a-122">試行を別のユーザーのマッピングを制御するアプリケーションのユーザーによってしました。</span><span class="sxs-lookup"><span data-stu-id="5457a-122">An attempt was made by an Application User to control the mappings of a different user.</span></span> <span data-ttu-id="5457a-123">これは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="5457a-123">This is not allowed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5457a-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5457a-124">User Action</span></span>  
 <span data-ttu-id="5457a-125">マッピングは、それらの特定のマッピングに対してアプリケーションのユーザーによってのみ制御できます。</span><span class="sxs-lookup"><span data-stu-id="5457a-125">Mappings can only be controlled by the Application Users for those specific mappings.</span></span>