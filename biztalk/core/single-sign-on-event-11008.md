---
title: 'シングル サインオン: イベント 11008 |Microsoft Docs'
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
ms.openlocfilehash: 7f3a77dcfb89a3040cf6c1acb71a053d57393591
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983731"
---
# <a name="single-sign-on-event-11008"></a><span data-ttu-id="56623-102">シングル サインオン: イベント 11008</span><span class="sxs-lookup"><span data-stu-id="56623-102">Single Sign-On: Event 11008</span></span>
## <a name="details"></a><span data-ttu-id="56623-103">詳細</span><span class="sxs-lookup"><span data-stu-id="56623-103">Details</span></span>  
  
|                 |                                                                                                                                                           |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="56623-104">製品名</span><span class="sxs-lookup"><span data-stu-id="56623-104">Product Name</span></span>   |                                                                 <span data-ttu-id="56623-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="56623-105">Enterprise Single Sign-On</span></span>                                                                 |
| <span data-ttu-id="56623-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="56623-106">Product Version</span></span> |                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                 |
|    <span data-ttu-id="56623-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="56623-107">Event ID</span></span>     |                                                                           <span data-ttu-id="56623-108">11008</span><span class="sxs-lookup"><span data-stu-id="56623-108">11008</span></span>                                                                           |
|  <span data-ttu-id="56623-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="56623-109">Event Source</span></span>   |                                                                          <span data-ttu-id="56623-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="56623-110">ENTSSO</span></span>                                                                           |
|    <span data-ttu-id="56623-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="56623-111">Component</span></span>    |                                                                            <span data-ttu-id="56623-112">なし</span><span class="sxs-lookup"><span data-stu-id="56623-112">N/A</span></span>                                                                            |
|  <span data-ttu-id="56623-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="56623-113">Symbolic Name</span></span>  |                                                                   <span data-ttu-id="56623-114">SSO_WARN_CHECK_GROUP</span><span class="sxs-lookup"><span data-stu-id="56623-114">SSO_WARN_CHECK_GROUP</span></span>                                                                    |
|  <span data-ttu-id="56623-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="56623-115">Message Text</span></span>   | <span data-ttu-id="56623-116">グループ メンバーシップの確認が失敗しました。%r</span><span class="sxs-lookup"><span data-stu-id="56623-116">Check group membership failed.%r</span></span><br /><br /> <span data-ttu-id="56623-117">グループ名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="56623-117">Group Name: %1%r</span></span><br /><br /> <span data-ttu-id="56623-118">アカウント名: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="56623-118">Account Name: %2%r</span></span><br /><br /> <span data-ttu-id="56623-119">追加データ: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="56623-119">Additional Data: %3%r</span></span><br /><br /> <span data-ttu-id="56623-120">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="56623-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="56623-121">説明</span><span class="sxs-lookup"><span data-stu-id="56623-121">Explanation</span></span>  
 <span data-ttu-id="56623-122">最も可能性が高い原因は、ネットワークの問題、クロスドメインの使用、またはドメイン コントローラーのレベルの混在 (たとえば、システムが [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] と [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] の両方のドメイン コントローラーを使用している場合) です。</span><span class="sxs-lookup"><span data-stu-id="56623-122">This is most likely caused by network issues, cross-domain use, or a mixed level of domain controllers (for example, if your system uses domain controllers from both [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] and [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="56623-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="56623-123">User Action</span></span>  
 <span data-ttu-id="56623-124">ネットワーク管理者と協力して、ネットワークに問題があるかどうか、またはシステムにクロスドメインの使用またはドメイン コントローラーのレベルの混在があるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="56623-124">Check with your network administrator to see if there are any network issues, or if your system has any cross-domain use or mixed level of domain controllers.</span></span>