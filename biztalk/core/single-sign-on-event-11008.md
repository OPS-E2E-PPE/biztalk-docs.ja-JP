---
title: シングル サインオン:イベント 11008 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7e11dbc-7596-45fa-ae54-a6e79498e60e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 367bb91906d659f0848e1745796c639d5e08f0b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306654"
---
# <a name="single-sign-on-event-11008"></a><span data-ttu-id="a47e4-102">シングル サインオン:イベント 11008</span><span class="sxs-lookup"><span data-stu-id="a47e4-102">Single Sign-On: Event 11008</span></span>
## <a name="details"></a><span data-ttu-id="a47e4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a47e4-103">Details</span></span>  
  
|                 |                                                                                                                                                           |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a47e4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a47e4-104">Product Name</span></span>   |                                                                 <span data-ttu-id="a47e4-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="a47e4-105">Enterprise Single Sign-On</span></span>                                                                 |
| <span data-ttu-id="a47e4-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a47e4-106">Product Version</span></span> |                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                 |
|    <span data-ttu-id="a47e4-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a47e4-107">Event ID</span></span>     |                                                                           <span data-ttu-id="a47e4-108">11008</span><span class="sxs-lookup"><span data-stu-id="a47e4-108">11008</span></span>                                                                           |
|  <span data-ttu-id="a47e4-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a47e4-109">Event Source</span></span>   |                                                                          <span data-ttu-id="a47e4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a47e4-110">ENTSSO</span></span>                                                                           |
|    <span data-ttu-id="a47e4-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a47e4-111">Component</span></span>    |                                                                            <span data-ttu-id="a47e4-112">なし</span><span class="sxs-lookup"><span data-stu-id="a47e4-112">N/A</span></span>                                                                            |
|  <span data-ttu-id="a47e4-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a47e4-113">Symbolic Name</span></span>  |                                                                   <span data-ttu-id="a47e4-114">SSO_WARN_CHECK_GROUP</span><span class="sxs-lookup"><span data-stu-id="a47e4-114">SSO_WARN_CHECK_GROUP</span></span>                                                                    |
|  <span data-ttu-id="a47e4-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a47e4-115">Message Text</span></span>   | <span data-ttu-id="a47e4-116">グループ メンバーシップ failed.%r を確認してください。</span><span class="sxs-lookup"><span data-stu-id="a47e4-116">Check group membership failed.%r</span></span><br /><br /> <span data-ttu-id="a47e4-117">グループ名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="a47e4-117">Group Name: %1%r</span></span><br /><br /> <span data-ttu-id="a47e4-118">アカウント名: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="a47e4-118">Account Name: %2%r</span></span><br /><br /> <span data-ttu-id="a47e4-119">追加データ: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="a47e4-119">Additional Data: %3%r</span></span><br /><br /> <span data-ttu-id="a47e4-120">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="a47e4-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="a47e4-121">説明</span><span class="sxs-lookup"><span data-stu-id="a47e4-121">Explanation</span></span>  
 <span data-ttu-id="a47e4-122">最も可能性の高い原因は、ネットワークの問題、クロス ドメインの使用、またはドメイン コント ローラーのレベルが混在 (システムは、両方のドメイン コント ローラーを使用している場合など、[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]と[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="a47e4-122">This is most likely caused by network issues, cross-domain use, or a mixed level of domain controllers (for example, if your system uses domain controllers from both [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] and [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a47e4-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a47e4-123">User Action</span></span>  
 <span data-ttu-id="a47e4-124">ネットワークの問題がある場合、または任意のクロス ドメインの使用またはレベルのドメイン コント ローラーの混在がある場合、ネットワーク管理者に確認してください。</span><span class="sxs-lookup"><span data-stu-id="a47e4-124">Check with your network administrator to see if there are any network issues, or if your system has any cross-domain use or mixed level of domain controllers.</span></span>