---
title: "シングル サインオン: イベント 10613 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a87ca19-24a0-4cf8-984f-2f70d7b5018c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf7230a0d6400a7265ef9f3cedb6bb47cc23aade
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10613"></a><span data-ttu-id="6a10e-102">シングル サインオン: イベント 10613</span><span class="sxs-lookup"><span data-stu-id="6a10e-102">Single Sign-On: Event 10613</span></span>
## <a name="details"></a><span data-ttu-id="6a10e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6a10e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6a10e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6a10e-104">Product Name</span></span>|<span data-ttu-id="6a10e-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="6a10e-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="6a10e-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6a10e-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="6a10e-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6a10e-107">Event ID</span></span>|<span data-ttu-id="6a10e-108">10613</span><span class="sxs-lookup"><span data-stu-id="6a10e-108">10613</span></span>|  
|<span data-ttu-id="6a10e-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6a10e-109">Event Source</span></span>|<span data-ttu-id="6a10e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6a10e-110">ENTSSO</span></span>|  
|<span data-ttu-id="6a10e-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6a10e-111">Component</span></span>|<span data-ttu-id="6a10e-112">なし</span><span class="sxs-lookup"><span data-stu-id="6a10e-112">N/A</span></span>|  
|<span data-ttu-id="6a10e-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6a10e-113">Symbolic Name</span></span>|<span data-ttu-id="6a10e-114">SSO_ERROR_RPC_CALLBACK</span><span class="sxs-lookup"><span data-stu-id="6a10e-114">SSO_ERROR_RPC_CALLBACK</span></span>|  
|<span data-ttu-id="6a10e-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6a10e-115">Message Text</span></span>|<span data-ttu-id="6a10e-116">SSO サーバー アクセスが拒否されました。%r</span><span class="sxs-lookup"><span data-stu-id="6a10e-116">SSO server access denied.%r</span></span><br /><br /> <span data-ttu-id="6a10e-117">クライアント ユーザー: %1 %r</span><span class="sxs-lookup"><span data-stu-id="6a10e-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="6a10e-118">RPC 呼び出し情報: %n%n 2: %3 %r</span><span class="sxs-lookup"><span data-stu-id="6a10e-118">RPC call information: %2:%3%r</span></span><br /><br /> <span data-ttu-id="6a10e-119">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="6a10e-119">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6a10e-120">説明</span><span class="sxs-lookup"><span data-stu-id="6a10e-120">Explanation</span></span>  
 <span data-ttu-id="6a10e-121">クライアントから SSO サーバーに対して呼び出しが実行されましたが、受け付けられませんでした。</span><span class="sxs-lookup"><span data-stu-id="6a10e-121">A call was made from a client to the SSO Server but was not accepted.</span></span> <span data-ttu-id="6a10e-122">原因として、プロトコルが正しくない、クライアントのセキュリティ アクセス許可が不十分など、さまざまな理由が考えられます。</span><span class="sxs-lookup"><span data-stu-id="6a10e-122">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the client.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6a10e-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6a10e-123">User Action</span></span>  
 <span data-ttu-id="6a10e-124">このメッセージの情報と、イベント ログで関連情報に注意してください、マイクロソフト製品サポート サービスにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="6a10e-124">Note the information in this message, and any relevant information in the event log, and contact Microsoft Product Support Services.</span></span>