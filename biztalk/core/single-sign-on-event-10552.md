---
title: "シングル サインオン: イベント 10552 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f85ae0b3-d8f8-4341-8bd3-423e85402d58
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fa08100af7a7d324c7a84d15ac741ba858f60d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10552"></a><span data-ttu-id="31783-102">シングル サインオン: イベント 10552</span><span class="sxs-lookup"><span data-stu-id="31783-102">Single Sign-On: Event 10552</span></span>
## <a name="details"></a><span data-ttu-id="31783-103">詳細</span><span class="sxs-lookup"><span data-stu-id="31783-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="31783-104">製品名</span><span class="sxs-lookup"><span data-stu-id="31783-104">Product Name</span></span>|<span data-ttu-id="31783-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="31783-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="31783-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="31783-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="31783-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="31783-107">Event ID</span></span>|<span data-ttu-id="31783-108">10552</span><span class="sxs-lookup"><span data-stu-id="31783-108">10552</span></span>|  
|<span data-ttu-id="31783-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="31783-109">Event Source</span></span>|<span data-ttu-id="31783-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="31783-110">ENTSSO</span></span>|  
|<span data-ttu-id="31783-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="31783-111">Component</span></span>|<span data-ttu-id="31783-112">なし</span><span class="sxs-lookup"><span data-stu-id="31783-112">N/A</span></span>|  
|<span data-ttu-id="31783-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="31783-113">Symbolic Name</span></span>|<span data-ttu-id="31783-114">SSO_ERROR_MAPPING_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="31783-114">SSO_ERROR_MAPPING_CALLBACK_ACCESS_DENIED</span></span>|  
|<span data-ttu-id="31783-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="31783-115">Message Text</span></span>|<span data-ttu-id="31783-116">マッピング サーバーのアクセスが拒否されました。%r</span><span class="sxs-lookup"><span data-stu-id="31783-116">Mapping server access denied.%r</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="31783-117">説明</span><span class="sxs-lookup"><span data-stu-id="31783-117">Explanation</span></span>  
 <span data-ttu-id="31783-118">クライアントがマッピング サーバーを呼び出しましたが、受け付けられませんでした。</span><span class="sxs-lookup"><span data-stu-id="31783-118">A call was made from a client to the mapping server but was not accepted.</span></span> <span data-ttu-id="31783-119">原因として、プロトコルが正しくない、クライアントのセキュリティ アクセス許可が不十分など、さまざまな理由が考えられます。</span><span class="sxs-lookup"><span data-stu-id="31783-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the client.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="31783-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="31783-120">User Action</span></span>  
 <span data-ttu-id="31783-121">エラー ログの情報をメモに取り、製品サポート サービスにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="31783-121">Note the information in the error log and contact product support services.</span></span>