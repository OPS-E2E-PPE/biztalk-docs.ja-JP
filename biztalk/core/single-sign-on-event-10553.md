---
title: 'シングル サインオン: イベント 10553 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f0da8faf-8127-4d2e-a2ef-e5af20aff34f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0103305692cfb978820cd94e9a42a3b384f5ba4d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013459"
---
# <a name="single-sign-on-event-10553"></a><span data-ttu-id="7b5d7-102">シングル サインオン: イベント 10553</span><span class="sxs-lookup"><span data-stu-id="7b5d7-102">Single Sign-On: Event 10553</span></span>
## <a name="details"></a><span data-ttu-id="7b5d7-103">詳細</span><span class="sxs-lookup"><span data-stu-id="7b5d7-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="7b5d7-104">製品名</span><span class="sxs-lookup"><span data-stu-id="7b5d7-104">Product Name</span></span>   |                 <span data-ttu-id="7b5d7-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="7b5d7-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="7b5d7-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7b5d7-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="7b5d7-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7b5d7-107">Event ID</span></span>     |                           <span data-ttu-id="7b5d7-108">10553</span><span class="sxs-lookup"><span data-stu-id="7b5d7-108">10553</span></span>                            |
|  <span data-ttu-id="7b5d7-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7b5d7-109">Event Source</span></span>   |                           <span data-ttu-id="7b5d7-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7b5d7-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="7b5d7-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7b5d7-111">Component</span></span>    |                            <span data-ttu-id="7b5d7-112">なし</span><span class="sxs-lookup"><span data-stu-id="7b5d7-112">N/A</span></span>                             |
|  <span data-ttu-id="7b5d7-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7b5d7-113">Symbolic Name</span></span>  |           <span data-ttu-id="7b5d7-114">SSO_ERROR_ADMIN_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="7b5d7-114">SSO_ERROR_ADMIN_CALLBACK_ACCESS_DENIED</span></span>           |
|  <span data-ttu-id="7b5d7-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7b5d7-115">Message Text</span></span>   |               <span data-ttu-id="7b5d7-116">管理サーバーのアクセスが拒否されました。%r</span><span class="sxs-lookup"><span data-stu-id="7b5d7-116">Admin server access denied.%r</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="7b5d7-117">説明</span><span class="sxs-lookup"><span data-stu-id="7b5d7-117">Explanation</span></span>  
 <span data-ttu-id="7b5d7-118">クライアントが管理サーバーを呼び出しましたが、受け付けられませんでした。</span><span class="sxs-lookup"><span data-stu-id="7b5d7-118">A call was made from a client to the Admin server but was not accepted.</span></span> <span data-ttu-id="7b5d7-119">原因として、プロトコルが正しくない、クライアントのセキュリティ アクセス許可が不十分など、さまざまな理由が考えられます。</span><span class="sxs-lookup"><span data-stu-id="7b5d7-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the client.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7b5d7-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7b5d7-120">User Action</span></span>  
 <span data-ttu-id="7b5d7-121">エラー ログの情報をメモに取り、製品サポート サービスにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="7b5d7-121">Note the information in the error log and contact product support services.</span></span>