---
title: 'シングル サインオン: イベント 10594 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f4c6041-39a8-49bc-b39e-66cb6eb2efae
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 804b2616080ceee0b6a31f7623e19e05c11481f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270562"
---
# <a name="single-sign-on-event-10594"></a><span data-ttu-id="8dd9c-102">シングル サインオン: イベント 10594</span><span class="sxs-lookup"><span data-stu-id="8dd9c-102">Single Sign-On: Event 10594</span></span>
## <a name="details"></a><span data-ttu-id="8dd9c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="8dd9c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8dd9c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="8dd9c-104">Product Name</span></span>|<span data-ttu-id="8dd9c-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="8dd9c-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="8dd9c-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8dd9c-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="8dd9c-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8dd9c-107">Event ID</span></span>|<span data-ttu-id="8dd9c-108">10594</span><span class="sxs-lookup"><span data-stu-id="8dd9c-108">10594</span></span>|  
|<span data-ttu-id="8dd9c-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8dd9c-109">Event Source</span></span>|<span data-ttu-id="8dd9c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8dd9c-110">ENTSSO</span></span>|  
|<span data-ttu-id="8dd9c-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8dd9c-111">Component</span></span>|<span data-ttu-id="8dd9c-112">なし</span><span class="sxs-lookup"><span data-stu-id="8dd9c-112">N/A</span></span>|  
|<span data-ttu-id="8dd9c-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8dd9c-113">Symbolic Name</span></span>|<span data-ttu-id="8dd9c-114">SSO_WARN_TICKET_VALIDATE_FAILED</span><span class="sxs-lookup"><span data-stu-id="8dd9c-114">SSO_WARN_TICKET_VALIDATE_FAILED</span></span>|  
|<span data-ttu-id="8dd9c-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8dd9c-115">Message Text</span></span>|<span data-ttu-id="8dd9c-116">チケットの検証に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="8dd9c-116">Validation of the ticket failed.</span></span> <span data-ttu-id="8dd9c-117">送信者名はチケット発行者名と一致している必要があります。%r</span><span class="sxs-lookup"><span data-stu-id="8dd9c-117">The sender name must match that of the ticket issuer.%r</span></span><br /><br /> <span data-ttu-id="8dd9c-118">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="8dd9c-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="8dd9c-119">%2 のによってチケットが発行された %r。</span><span class="sxs-lookup"><span data-stu-id="8dd9c-119">Ticket Issued By: %2%r</span></span><br /><br /> <span data-ttu-id="8dd9c-120">送信者名: %3</span><span class="sxs-lookup"><span data-stu-id="8dd9c-120">Sender Name: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8dd9c-121">説明</span><span class="sxs-lookup"><span data-stu-id="8dd9c-121">Explanation</span></span>  
 <span data-ttu-id="8dd9c-122">チケットを検証するには、(警告メッセージに表示される) "チケット発行者" フィールドと "送信者名" フィールドが一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8dd9c-122">In order for a ticket to be validated, the Ticket Issued By and Sender Name fields (in the warning message) must match.</span></span> <span data-ttu-id="8dd9c-123">しかし、メッセージが BizTalk で信頼されていないホストを介して送信される場合、"送信者名" が BizTalk で信頼されていないホストの名前に変更され、チケットは検証されません。</span><span class="sxs-lookup"><span data-stu-id="8dd9c-123">If, however, the message is sent through a BizTalk untrusted host, the Sender Name gets changed to the name of the BizTalk untrusted host, and the ticket will not validate.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8dd9c-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8dd9c-124">User Action</span></span>  
 <span data-ttu-id="8dd9c-125">エンタープライズ シングル サインオンを使用している場合は、メッセージが BizTalk で信頼されているホストのみを介して送信されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8dd9c-125">If you are using Enterprise Single Sign-On, ensure that your message is flowing only through BizTalk trusted hosts.</span></span> <span data-ttu-id="8dd9c-126">メッセージのデータ改ざんのリスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="8dd9c-126">This will reduce the risk of tampering with the data in the message.</span></span>  
  
 <span data-ttu-id="8dd9c-127">使用環境のシナリオにおけるセキュリティの意味を十分に理解している場合は、このアプリケーションの検証を無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8dd9c-127">If you fully understand the security implications for your scenario, you can turn off validation for this application.</span></span> <span data-ttu-id="8dd9c-128">検証は管理オプションであり、システム全体で無効にすることも、この特定のアプリケーションについてのみ無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8dd9c-128">Note that validation is an administration option which can be turned off for the system or just for this particular application.</span></span>