---
title: シングル サインオン:イベント 10594 |Microsoft Docs
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
ms.openlocfilehash: 5c2f70c563113b7b7473d86046f2ac78eec4ea4a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397853"
---
# <a name="single-sign-on-event-10594"></a><span data-ttu-id="fc6d3-102">シングル サインオン:イベント 10594</span><span class="sxs-lookup"><span data-stu-id="fc6d3-102">Single Sign-On: Event 10594</span></span>
## <a name="details"></a><span data-ttu-id="fc6d3-103">詳細</span><span class="sxs-lookup"><span data-stu-id="fc6d3-103">Details</span></span>  
  
|                 |                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="fc6d3-104">製品名</span><span class="sxs-lookup"><span data-stu-id="fc6d3-104">Product Name</span></span>   |                                                                                 <span data-ttu-id="fc6d3-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="fc6d3-105">Enterprise Single Sign-On</span></span>                                                                                  |
| <span data-ttu-id="fc6d3-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="fc6d3-106">Product Version</span></span> |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                 |
|    <span data-ttu-id="fc6d3-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="fc6d3-107">Event ID</span></span>     |                                                                                           <span data-ttu-id="fc6d3-108">10594</span><span class="sxs-lookup"><span data-stu-id="fc6d3-108">10594</span></span>                                                                                            |
|  <span data-ttu-id="fc6d3-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="fc6d3-109">Event Source</span></span>   |                                                                                           <span data-ttu-id="fc6d3-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fc6d3-110">ENTSSO</span></span>                                                                                           |
|    <span data-ttu-id="fc6d3-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fc6d3-111">Component</span></span>    |                                                                                            <span data-ttu-id="fc6d3-112">なし</span><span class="sxs-lookup"><span data-stu-id="fc6d3-112">N/A</span></span>                                                                                             |
|  <span data-ttu-id="fc6d3-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="fc6d3-113">Symbolic Name</span></span>  |                                                                              <span data-ttu-id="fc6d3-114">SSO_WARN_TICKET_VALIDATE_FAILED</span><span class="sxs-lookup"><span data-stu-id="fc6d3-114">SSO_WARN_TICKET_VALIDATE_FAILED</span></span>                                                                               |
|  <span data-ttu-id="fc6d3-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="fc6d3-115">Message Text</span></span>   | <span data-ttu-id="fc6d3-116">チケットの検証に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="fc6d3-116">Validation of the ticket failed.</span></span> <span data-ttu-id="fc6d3-117">送信者名はチケット issuer.%r の一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc6d3-117">The sender name must match that of the ticket issuer.%r</span></span><br /><br /> <span data-ttu-id="fc6d3-118">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="fc6d3-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="fc6d3-119">%2 のチケットの発行元: %r</span><span class="sxs-lookup"><span data-stu-id="fc6d3-119">Ticket Issued By: %2%r</span></span><br /><br /> <span data-ttu-id="fc6d3-120">送信者名: %3</span><span class="sxs-lookup"><span data-stu-id="fc6d3-120">Sender Name: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="fc6d3-121">説明</span><span class="sxs-lookup"><span data-stu-id="fc6d3-121">Explanation</span></span>  
 <span data-ttu-id="fc6d3-122">チケットを検証するためには、(警告メッセージ) にチケットの発行元"と"送信者名フィールドに一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc6d3-122">In order for a ticket to be validated, the Ticket Issued By and Sender Name fields (in the warning message) must match.</span></span> <span data-ttu-id="fc6d3-123">ただし、BizTalk の信頼されていないホストを介してメッセージを送信する場合は、送信者名は、信頼されていない BizTalk ホストの名前に変更を取得し、チケットは検証されません。</span><span class="sxs-lookup"><span data-stu-id="fc6d3-123">If, however, the message is sent through a BizTalk untrusted host, the Sender Name gets changed to the name of the BizTalk untrusted host, and the ticket will not validate.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fc6d3-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="fc6d3-124">User Action</span></span>  
 <span data-ttu-id="fc6d3-125">エンタープライズ シングル サインオンを使用する場合は、メッセージが信頼されている BizTalk ホストのみを介して送信されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fc6d3-125">If you are using Enterprise Single Sign-On, ensure that your message is flowing only through BizTalk trusted hosts.</span></span> <span data-ttu-id="fc6d3-126">これにより、メッセージのデータの改ざんのリスクが低減されます。</span><span class="sxs-lookup"><span data-stu-id="fc6d3-126">This will reduce the risk of tampering with the data in the message.</span></span>  
  
 <span data-ttu-id="fc6d3-127">シナリオでは、セキュリティへの影響を完全に理解している場合は、このアプリケーションの検証をオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="fc6d3-127">If you fully understand the security implications for your scenario, you can turn off validation for this application.</span></span> <span data-ttu-id="fc6d3-128">検証は管理オプションであり、システムまたはこの特定のアプリケーションに対してだけ、オフにすることであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fc6d3-128">Note that validation is an administration option which can be turned off for the system or just for this particular application.</span></span>