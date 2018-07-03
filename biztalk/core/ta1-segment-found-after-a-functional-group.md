---
title: TA1 セグメントの機能グループの後に見つかった |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee3d090a-0916-4a0e-82dc-2c9af9f97683
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87613f9482c5c54e99544b96ddd0d1cfc94d3c85
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018140"
---
# <a name="ta1-segment-found-after-a-functional-group"></a><span data-ttu-id="37a2a-102">機能グループの後に TA1 セグメントが見つかりました</span><span class="sxs-lookup"><span data-stu-id="37a2a-102">TA1 segment found after a functional group</span></span>
## <a name="details"></a><span data-ttu-id="37a2a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="37a2a-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="37a2a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="37a2a-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="37a2a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="37a2a-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="37a2a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="37a2a-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="37a2a-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="37a2a-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="37a2a-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="37a2a-108"> EDI</span></span> |
|    <span data-ttu-id="37a2a-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="37a2a-109">Component</span></span>    |                                       <span data-ttu-id="37a2a-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="37a2a-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="37a2a-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="37a2a-111">Symbolic Name</span></span>  |                              <span data-ttu-id="37a2a-112">TA1FoundAfterFunctionalGroup</span><span class="sxs-lookup"><span data-stu-id="37a2a-112">TA1FoundAfterFunctionalGroup</span></span>                              |
|  <span data-ttu-id="37a2a-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="37a2a-113">Message Text</span></span>   |     <span data-ttu-id="37a2a-114">機能グループの後に TA1 セグメントが見つかったため、</span><span class="sxs-lookup"><span data-stu-id="37a2a-114">TA1 segment found after a functional group.</span></span> <span data-ttu-id="37a2a-115">メッセージは拒否されています</span><span class="sxs-lookup"><span data-stu-id="37a2a-115">So, the message is being rejected</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="37a2a-116">説明</span><span class="sxs-lookup"><span data-stu-id="37a2a-116">Explanation</span></span>  
 <span data-ttu-id="37a2a-117">このエラー/警告/情報イベントは、受信確認に機能グループに続いて TA1 セグメントが含まれていたため、受信パイプラインで受信確認を処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="37a2a-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming acknowledgment because the acknowledgment contained a functional group and then a TA1 segment.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="37a2a-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="37a2a-118">User Action</span></span>  
 <span data-ttu-id="37a2a-119">このエラーを解決するには、TA1 受信確認の送信者に対して、インターチェンジで TA1 セグメントの前に機能グループが含まれていないことを確認するよう依頼し、受信確認を再送信します。</span><span class="sxs-lookup"><span data-stu-id="37a2a-119">To resolve this error, have the sender of the TA1 acknowledgment ensure that the interchange does not contain a functional group before the TA1 segment, and then resend the acknowledgment.</span></span>