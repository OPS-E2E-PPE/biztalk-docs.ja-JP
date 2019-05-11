---
title: シングル サインオン:イベント 10552 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f85ae0b3-d8f8-4341-8bd3-423e85402d58
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 744ecbd42d4a62fd72b792e7491f3f127ebf14f3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398895"
---
# <a name="single-sign-on-event-10552"></a><span data-ttu-id="00b88-102">シングル サインオン:イベント 10552</span><span class="sxs-lookup"><span data-stu-id="00b88-102">Single Sign-On: Event 10552</span></span>
## <a name="details"></a><span data-ttu-id="00b88-103">詳細</span><span class="sxs-lookup"><span data-stu-id="00b88-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="00b88-104">製品名</span><span class="sxs-lookup"><span data-stu-id="00b88-104">Product Name</span></span>   |                 <span data-ttu-id="00b88-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="00b88-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="00b88-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="00b88-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="00b88-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="00b88-107">Event ID</span></span>     |                           <span data-ttu-id="00b88-108">10552</span><span class="sxs-lookup"><span data-stu-id="00b88-108">10552</span></span>                            |
|  <span data-ttu-id="00b88-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="00b88-109">Event Source</span></span>   |                           <span data-ttu-id="00b88-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="00b88-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="00b88-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="00b88-111">Component</span></span>    |                            <span data-ttu-id="00b88-112">なし</span><span class="sxs-lookup"><span data-stu-id="00b88-112">N/A</span></span>                             |
|  <span data-ttu-id="00b88-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="00b88-113">Symbolic Name</span></span>  |          <span data-ttu-id="00b88-114">SSO_ERROR_MAPPING_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="00b88-114">SSO_ERROR_MAPPING_CALLBACK_ACCESS_DENIED</span></span>          |
|  <span data-ttu-id="00b88-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="00b88-115">Message Text</span></span>   |              <span data-ttu-id="00b88-116">マッピング サーバー アクセス denied.%r</span><span class="sxs-lookup"><span data-stu-id="00b88-116">Mapping server access denied.%r</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="00b88-117">説明</span><span class="sxs-lookup"><span data-stu-id="00b88-117">Explanation</span></span>  
 <span data-ttu-id="00b88-118">呼び出しでは、マッピング サーバーにクライアントからしましたが、受け付けられませんでした。</span><span class="sxs-lookup"><span data-stu-id="00b88-118">A call was made from a client to the mapping server but was not accepted.</span></span> <span data-ttu-id="00b88-119">さまざまなプロトコルが正しくないや、クライアント上の不十分なセキュリティ アクセス許可など、さまざまな理由の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="00b88-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the client.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="00b88-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="00b88-120">User Action</span></span>  
 <span data-ttu-id="00b88-121">エラー ログの情報をメモし、製品サポート サービスにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="00b88-121">Note the information in the error log and contact product support services.</span></span>