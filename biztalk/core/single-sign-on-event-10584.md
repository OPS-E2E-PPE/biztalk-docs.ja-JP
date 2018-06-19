---
title: 'シングル サインオン: イベント 10584 |Microsoft ドキュメント'
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
ms.openlocfilehash: d08be0100d53f081eb7d8f4faa27d1e7f46f6f46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270370"
---
# <a name="single-sign-on-event-10584"></a><span data-ttu-id="a2867-102">シングル サインオン: イベント 10584</span><span class="sxs-lookup"><span data-stu-id="a2867-102">Single Sign-On: Event 10584</span></span>
## <a name="details"></a><span data-ttu-id="a2867-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a2867-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a2867-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a2867-104">Product Name</span></span>|<span data-ttu-id="a2867-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="a2867-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="a2867-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a2867-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="a2867-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a2867-107">Event ID</span></span>|<span data-ttu-id="a2867-108">10584</span><span class="sxs-lookup"><span data-stu-id="a2867-108">10584</span></span>|  
|<span data-ttu-id="a2867-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a2867-109">Event Source</span></span>|<span data-ttu-id="a2867-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a2867-110">ENTSSO</span></span>|  
|<span data-ttu-id="a2867-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a2867-111">Component</span></span>|<span data-ttu-id="a2867-112">なし</span><span class="sxs-lookup"><span data-stu-id="a2867-112">N/A</span></span>|  
|<span data-ttu-id="a2867-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a2867-113">Symbolic Name</span></span>|<span data-ttu-id="a2867-114">SSO_WARN_NO_IMPERSONATION</span><span class="sxs-lookup"><span data-stu-id="a2867-114">SSO_WARN_NO_IMPERSONATION</span></span>|  
|<span data-ttu-id="a2867-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a2867-115">Message Text</span></span>|<span data-ttu-id="a2867-116">クライアントを偽装できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="a2867-116">Could not impersonate the client.%r</span></span><br /><br /> <span data-ttu-id="a2867-117">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="a2867-117">Error Code: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a2867-118">説明</span><span class="sxs-lookup"><span data-stu-id="a2867-118">Explanation</span></span>  
 <span data-ttu-id="a2867-119">クライアントの偽装は、クライアントの ID を確認するために ENTSSO システムで行う処理です。</span><span class="sxs-lookup"><span data-stu-id="a2867-119">Impersonating the client is something the ENTSSO System does to verify the client’s identity.</span></span> <span data-ttu-id="a2867-120">システムがクライアントを偽装できない場合、3 つのいずれかの状況が発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2867-120">When the system is unable to impersonate a client, one of three things may have occurred.</span></span> <span data-ttu-id="a2867-121">クライアントが通常のアクティビティを実行しようとしたか、クライアントがシステムのセキュリティに侵入しようとしたか、またはクライアント アプリケーションが偽装をブロックするように設計されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2867-121">The client may be attempting to perform an usual activity, the client may be attempting to infiltrate system security, or the client application may have been designed to block impersonation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a2867-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a2867-122">User Action</span></span>  
 <span data-ttu-id="a2867-123">クライアント アプリケーションを探し、どのような処理が行われようとしているか、およびクライアント アプリケーションが偽装をブロックしているかどうかを特定します。</span><span class="sxs-lookup"><span data-stu-id="a2867-123">Locate the client application and determine what it is attempting to do, and whether or not it is blocking impersonation.</span></span>