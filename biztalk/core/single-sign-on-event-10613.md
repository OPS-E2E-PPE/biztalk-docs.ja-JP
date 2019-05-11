---
title: シングル サインオン:イベント 10613 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a87ca19-24a0-4cf8-984f-2f70d7b5018c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9a2743e19ef393409df934c811698557e9b0078
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397701"
---
# <a name="single-sign-on-event-10613"></a><span data-ttu-id="d8a2a-102">シングル サインオン:イベント 10613</span><span class="sxs-lookup"><span data-stu-id="d8a2a-102">Single Sign-On: Event 10613</span></span>
## <a name="details"></a><span data-ttu-id="d8a2a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d8a2a-103">Details</span></span>  
  
|                 |                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d8a2a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d8a2a-104">Product Name</span></span>   |                                                   <span data-ttu-id="d8a2a-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d8a2a-105">Enterprise Single Sign-On</span></span>                                                    |
| <span data-ttu-id="d8a2a-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d8a2a-106">Product Version</span></span> |                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                   |
|    <span data-ttu-id="d8a2a-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d8a2a-107">Event ID</span></span>     |                                                             <span data-ttu-id="d8a2a-108">10613</span><span class="sxs-lookup"><span data-stu-id="d8a2a-108">10613</span></span>                                                              |
|  <span data-ttu-id="d8a2a-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d8a2a-109">Event Source</span></span>   |                                                             <span data-ttu-id="d8a2a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d8a2a-110">ENTSSO</span></span>                                                             |
|    <span data-ttu-id="d8a2a-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d8a2a-111">Component</span></span>    |                                                              <span data-ttu-id="d8a2a-112">なし</span><span class="sxs-lookup"><span data-stu-id="d8a2a-112">N/A</span></span>                                                               |
|  <span data-ttu-id="d8a2a-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d8a2a-113">Symbolic Name</span></span>  |                                                     <span data-ttu-id="d8a2a-114">SSO_ERROR_RPC_CALLBACK</span><span class="sxs-lookup"><span data-stu-id="d8a2a-114">SSO_ERROR_RPC_CALLBACK</span></span>                                                     |
|  <span data-ttu-id="d8a2a-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d8a2a-115">Message Text</span></span>   | <span data-ttu-id="d8a2a-116">SSO サーバー アクセス denied.%r</span><span class="sxs-lookup"><span data-stu-id="d8a2a-116">SSO server access denied.%r</span></span><br /><br /> <span data-ttu-id="d8a2a-117">クライアント ユーザー: 1 %r</span><span class="sxs-lookup"><span data-stu-id="d8a2a-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="d8a2a-118">RPC 呼び出し情報: %2: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="d8a2a-118">RPC call information: %2:%3%r</span></span><br /><br /> <span data-ttu-id="d8a2a-119">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="d8a2a-119">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d8a2a-120">説明</span><span class="sxs-lookup"><span data-stu-id="d8a2a-120">Explanation</span></span>  
 <span data-ttu-id="d8a2a-121">呼び出しは、SSO サーバーにクライアントからしましたが、受け付けられませんでした。</span><span class="sxs-lookup"><span data-stu-id="d8a2a-121">A call was made from a client to the SSO Server but was not accepted.</span></span> <span data-ttu-id="d8a2a-122">さまざまなプロトコルが正しくないや、クライアント上の不十分なセキュリティ アクセス許可など、さまざまな理由の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d8a2a-122">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the client.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d8a2a-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d8a2a-123">User Action</span></span>  
 <span data-ttu-id="d8a2a-124">このメッセージの情報と、イベント ログで関連情報をメモし、マイクロソフト製品サポート サービスにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="d8a2a-124">Note the information in this message, and any relevant information in the event log, and contact Microsoft Product Support Services.</span></span>