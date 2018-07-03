---
title: プロトコルが無効にに対して見つかったアグリーメントの状態を期限切れまたは |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b524f423-1325-495c-9499-33101f6388fc
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d7e4092b057b83caef252d63853ecf6791edbde
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014723"
---
# <a name="agreement-found-for-the-protocol-is-in-disabled-or-expired-state"></a><span data-ttu-id="b3c6d-102">プロトコルに対して見つかったアグリーメントの状態が "無効" または "期限切れ" です</span><span class="sxs-lookup"><span data-stu-id="b3c6d-102">Agreement found for the Protocol is in Disabled or Expired state</span></span>
## <a name="details"></a><span data-ttu-id="b3c6d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b3c6d-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="b3c6d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b3c6d-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="b3c6d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b3c6d-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="b3c6d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b3c6d-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="b3c6d-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b3c6d-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b3c6d-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="b3c6d-108"> EDI</span></span> |
|    <span data-ttu-id="b3c6d-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b3c6d-109">Component</span></span>    |                                       <span data-ttu-id="b3c6d-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="b3c6d-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="b3c6d-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b3c6d-111">Symbolic Name</span></span>  |                     <span data-ttu-id="b3c6d-112">AgreementResolutionAgreementDiasbledOrExpired</span><span class="sxs-lookup"><span data-stu-id="b3c6d-112">AgreementResolutionAgreementDiasbledOrExpired</span></span>                      |
|  <span data-ttu-id="b3c6d-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b3c6d-113">Message Text</span></span>   |      <span data-ttu-id="b3c6d-114">アグリーメントが見つかりませんでした、{0}プロトコルが無効または期限切れのいずれかの状態。</span><span class="sxs-lookup"><span data-stu-id="b3c6d-114">Agreement found for the {0} Protocol is in either Disabled or Expired state.</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="b3c6d-115">説明</span><span class="sxs-lookup"><span data-stu-id="b3c6d-115">Explanation</span></span>  
 <span data-ttu-id="b3c6d-116">このエラー/警告/情報イベントは、BizTalk Server がアグリーメントを解決できたが、アグリーメントの状態が無効または期限切れだったことを示します。</span><span class="sxs-lookup"><span data-stu-id="b3c6d-116">This Error/Warning/Information event indicates BizTalk Server was able to resolve to an agreement but it is in disabled or expired state.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b3c6d-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b3c6d-117">User Action</span></span>  
 <span data-ttu-id="b3c6d-118">このエラーを解決するには、アグリーメントを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="b3c6d-118">To resolve this error, please enable the agreement.</span></span>