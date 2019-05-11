---
title: シングル サインオン:イベント 10553 |Microsoft Docs
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
ms.openlocfilehash: d5c2448180e963f7ecf0b0f9da694f2d31bb94f5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398870"
---
# <a name="single-sign-on-event-10553"></a><span data-ttu-id="96bb9-102">シングル サインオン:イベント 10553</span><span class="sxs-lookup"><span data-stu-id="96bb9-102">Single Sign-On: Event 10553</span></span>
## <a name="details"></a><span data-ttu-id="96bb9-103">詳細</span><span class="sxs-lookup"><span data-stu-id="96bb9-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="96bb9-104">製品名</span><span class="sxs-lookup"><span data-stu-id="96bb9-104">Product Name</span></span>   |                 <span data-ttu-id="96bb9-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="96bb9-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="96bb9-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="96bb9-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="96bb9-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="96bb9-107">Event ID</span></span>     |                           <span data-ttu-id="96bb9-108">10553</span><span class="sxs-lookup"><span data-stu-id="96bb9-108">10553</span></span>                            |
|  <span data-ttu-id="96bb9-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="96bb9-109">Event Source</span></span>   |                           <span data-ttu-id="96bb9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="96bb9-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="96bb9-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="96bb9-111">Component</span></span>    |                            <span data-ttu-id="96bb9-112">なし</span><span class="sxs-lookup"><span data-stu-id="96bb9-112">N/A</span></span>                             |
|  <span data-ttu-id="96bb9-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="96bb9-113">Symbolic Name</span></span>  |           <span data-ttu-id="96bb9-114">SSO_ERROR_ADMIN_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="96bb9-114">SSO_ERROR_ADMIN_CALLBACK_ACCESS_DENIED</span></span>           |
|  <span data-ttu-id="96bb9-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="96bb9-115">Message Text</span></span>   |               <span data-ttu-id="96bb9-116">管理サーバーへのアクセス denied.%r</span><span class="sxs-lookup"><span data-stu-id="96bb9-116">Admin server access denied.%r</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="96bb9-117">説明</span><span class="sxs-lookup"><span data-stu-id="96bb9-117">Explanation</span></span>  
 <span data-ttu-id="96bb9-118">呼び出しでは、管理サーバーにクライアントからしましたが、受け付けられませんでした。</span><span class="sxs-lookup"><span data-stu-id="96bb9-118">A call was made from a client to the Admin server but was not accepted.</span></span> <span data-ttu-id="96bb9-119">さまざまなプロトコルが正しくないや、クライアント上の不十分なセキュリティ アクセス許可など、さまざまな理由の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="96bb9-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the client.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="96bb9-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="96bb9-120">User Action</span></span>  
 <span data-ttu-id="96bb9-121">エラー ログの情報をメモし、製品サポート サービスにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="96bb9-121">Note the information in the error log and contact product support services.</span></span>