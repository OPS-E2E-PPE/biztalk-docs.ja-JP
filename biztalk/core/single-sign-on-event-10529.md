---
title: 'シングル サインオン: イベント 10529 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75ed70e0-8458-4736-883f-a4536f094dc0
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f33c0e475f9b54b5fc0a5d5415736d9717ccdf9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270570"
---
# <a name="single-sign-on-event-10529"></a><span data-ttu-id="19e86-102">シングル サインオン: イベント 10529</span><span class="sxs-lookup"><span data-stu-id="19e86-102">Single Sign-On: Event 10529</span></span>
## <a name="details"></a><span data-ttu-id="19e86-103">詳細</span><span class="sxs-lookup"><span data-stu-id="19e86-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="19e86-104">製品名</span><span class="sxs-lookup"><span data-stu-id="19e86-104">Product Name</span></span>|<span data-ttu-id="19e86-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="19e86-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="19e86-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="19e86-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="19e86-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="19e86-107">Event ID</span></span>|<span data-ttu-id="19e86-108">10529</span><span class="sxs-lookup"><span data-stu-id="19e86-108">10529</span></span>|  
|<span data-ttu-id="19e86-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="19e86-109">Event Source</span></span>|<span data-ttu-id="19e86-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="19e86-110">ENTSSO</span></span>|  
|<span data-ttu-id="19e86-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="19e86-111">Component</span></span>|<span data-ttu-id="19e86-112">N\A</span><span class="sxs-lookup"><span data-stu-id="19e86-112">N\A</span></span>|  
|<span data-ttu-id="19e86-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="19e86-113">Symbolic Name</span></span>|<span data-ttu-id="19e86-114">SSO_INFO_GOT_CURRENT_SECRET</span><span class="sxs-lookup"><span data-stu-id="19e86-114">SSO_INFO_GOT_CURRENT_SECRET</span></span>|  
|<span data-ttu-id="19e86-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="19e86-115">Message Text</span></span>|<span data-ttu-id="19e86-116">マスター シークレット サーバーから現在のシークレットを取得しました。%r</span><span class="sxs-lookup"><span data-stu-id="19e86-116">Got the current secret from the master secret server.%r</span></span><br /><br /> <span data-ttu-id="19e86-117">シークレット サーバー名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="19e86-117">Secret Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="19e86-118">MSID: %2</span><span class="sxs-lookup"><span data-stu-id="19e86-118">MSID: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="19e86-119">説明</span><span class="sxs-lookup"><span data-stu-id="19e86-119">Explanation</span></span>  
 <span data-ttu-id="19e86-120">この情報イベントは、SSO がマスター シークレット サーバーにマスター シークレットを要求したことを示します。</span><span class="sxs-lookup"><span data-stu-id="19e86-120">This Information event indicates that SSO has the requested master secret from the master secret server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="19e86-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="19e86-121">User Action</span></span>  
  
-   <span data-ttu-id="19e86-122">ユーザーの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="19e86-122">No user action is necessary.</span></span>  
  
 <span data-ttu-id="19e86-123">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="19e86-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="19e86-124">マスター シークレットを生成する方法</span><span class="sxs-lookup"><span data-stu-id="19e86-124">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  
  
-   [<span data-ttu-id="19e86-125">マスタ シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="19e86-125">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)