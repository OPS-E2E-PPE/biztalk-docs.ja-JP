---
title: "シングル サインオン: イベント 10530 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4bb37305-26fe-46a7-958d-3ed7f6876a7b
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cf8759d2fe3b2281b87ffe9841bdd4e6b44081a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10530"></a><span data-ttu-id="4ce2d-102">シングル サインオン: イベント 10530</span><span class="sxs-lookup"><span data-stu-id="4ce2d-102">Single Sign-On: Event 10530</span></span>
## <a name="details"></a><span data-ttu-id="4ce2d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="4ce2d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4ce2d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="4ce2d-104">Product Name</span></span>|<span data-ttu-id="4ce2d-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="4ce2d-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="4ce2d-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4ce2d-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="4ce2d-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4ce2d-107">Event ID</span></span>|<span data-ttu-id="4ce2d-108">10530</span><span class="sxs-lookup"><span data-stu-id="4ce2d-108">10530</span></span>|  
|<span data-ttu-id="4ce2d-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4ce2d-109">Event Source</span></span>|<span data-ttu-id="4ce2d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4ce2d-110">ENTSSO</span></span>|  
|<span data-ttu-id="4ce2d-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4ce2d-111">Component</span></span>|<span data-ttu-id="4ce2d-112">N\A</span><span class="sxs-lookup"><span data-stu-id="4ce2d-112">N\A</span></span>|  
|<span data-ttu-id="4ce2d-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4ce2d-113">Symbolic Name</span></span>|<span data-ttu-id="4ce2d-114">SSO_INFO_GOT_PREVIOUS_SECRET</span><span class="sxs-lookup"><span data-stu-id="4ce2d-114">SSO_INFO_GOT_PREVIOUS_SECRET</span></span>|  
|<span data-ttu-id="4ce2d-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4ce2d-115">Message Text</span></span>|<span data-ttu-id="4ce2d-116">マスター シークレット サーバーから以前のシークレットを取得しました。%r</span><span class="sxs-lookup"><span data-stu-id="4ce2d-116">Got the previous secret from the master secret server.%r</span></span><br /><br /> <span data-ttu-id="4ce2d-117">シークレット サーバー名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="4ce2d-117">Secret Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="4ce2d-118">MSID: %2</span><span class="sxs-lookup"><span data-stu-id="4ce2d-118">MSID: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4ce2d-119">説明</span><span class="sxs-lookup"><span data-stu-id="4ce2d-119">Explanation</span></span>  
 <span data-ttu-id="4ce2d-120">この情報イベントは、SSO が以前のマスター シークレットを取得したことを示します。</span><span class="sxs-lookup"><span data-stu-id="4ce2d-120">This Information event indicates that SSO has the previous master secret.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4ce2d-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4ce2d-121">User Action</span></span>  
  
-   <span data-ttu-id="4ce2d-122">ユーザーの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="4ce2d-122">No user action is necessary.</span></span>  
  
 <span data-ttu-id="4ce2d-123">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="4ce2d-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="4ce2d-124">マスター シークレットを生成する方法</span><span class="sxs-lookup"><span data-stu-id="4ce2d-124">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  
  
-   [<span data-ttu-id="4ce2d-125">マスタ シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="4ce2d-125">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)