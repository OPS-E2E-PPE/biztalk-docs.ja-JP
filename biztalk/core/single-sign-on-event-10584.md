---
title: シングル サインオン:イベント 10584 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8af9377d-b4fd-48a6-961a-3629b3db644a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 478d33b1ef00930617a32f18dc7cf942210e0162
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395252"
---
# <a name="single-sign-on-event-10584"></a><span data-ttu-id="698ca-102">シングル サインオン:イベント 10584</span><span class="sxs-lookup"><span data-stu-id="698ca-102">Single Sign-On: Event 10584</span></span>
## <a name="details"></a><span data-ttu-id="698ca-103">詳細</span><span class="sxs-lookup"><span data-stu-id="698ca-103">Details</span></span>  
  
|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  <span data-ttu-id="698ca-104">製品名</span><span class="sxs-lookup"><span data-stu-id="698ca-104">Product Name</span></span>   |                   <span data-ttu-id="698ca-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="698ca-105">Enterprise Single Sign-On</span></span>                    |
| <span data-ttu-id="698ca-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="698ca-106">Product Version</span></span> |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    <span data-ttu-id="698ca-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="698ca-107">Event ID</span></span>     |                             <span data-ttu-id="698ca-108">10584</span><span class="sxs-lookup"><span data-stu-id="698ca-108">10584</span></span>                              |
|  <span data-ttu-id="698ca-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="698ca-109">Event Source</span></span>   |                             <span data-ttu-id="698ca-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="698ca-110">ENTSSO</span></span>                             |
|    <span data-ttu-id="698ca-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="698ca-111">Component</span></span>    |                              <span data-ttu-id="698ca-112">なし</span><span class="sxs-lookup"><span data-stu-id="698ca-112">N/A</span></span>                               |
|  <span data-ttu-id="698ca-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="698ca-113">Symbolic Name</span></span>  |                   <span data-ttu-id="698ca-114">SSO_WARN_NO_IMPERSONATION</span><span class="sxs-lookup"><span data-stu-id="698ca-114">SSO_WARN_NO_IMPERSONATION</span></span>                    |
|  <span data-ttu-id="698ca-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="698ca-115">Message Text</span></span>   | <span data-ttu-id="698ca-116">Client.%r を偽装できませんでした。</span><span class="sxs-lookup"><span data-stu-id="698ca-116">Could not impersonate the client.%r</span></span><br /><br /> <span data-ttu-id="698ca-117">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="698ca-117">Error Code: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="698ca-118">説明</span><span class="sxs-lookup"><span data-stu-id="698ca-118">Explanation</span></span>  
 <span data-ttu-id="698ca-119">クライアントの偽装は、ENTSSO システムでは、クライアントの身元を確認します。</span><span class="sxs-lookup"><span data-stu-id="698ca-119">Impersonating the client is something the ENTSSO System does to verify the client’s identity.</span></span> <span data-ttu-id="698ca-120">システムは、クライアントを偽装することは、次の 3 つのいずれかが発生した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="698ca-120">When the system is unable to impersonate a client, one of three things may have occurred.</span></span> <span data-ttu-id="698ca-121">クライアントが通常のアクティビティを実行しよう、クライアントがシステムのセキュリティに侵入しようまたはクライアント アプリケーションが偽装をブロックする設計されています。</span><span class="sxs-lookup"><span data-stu-id="698ca-121">The client may be attempting to perform an usual activity, the client may be attempting to infiltrate system security, or the client application may have been designed to block impersonation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="698ca-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="698ca-122">User Action</span></span>  
 <span data-ttu-id="698ca-123">クライアント アプリケーションを見つけて、試行を行うには、権限借用でブロックされるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="698ca-123">Locate the client application and determine what it is attempting to do, and whether or not it is blocking impersonation.</span></span>