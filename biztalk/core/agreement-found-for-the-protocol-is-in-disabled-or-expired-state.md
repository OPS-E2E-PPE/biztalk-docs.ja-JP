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
ms.openlocfilehash: 8c1fe6f01b31d841c5d07bbae51a6a311bca28c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360080"
---
# <a name="agreement-found-for-the-protocol-is-in-disabled-or-expired-state"></a><span data-ttu-id="d12a3-102">プロトコルが無効にに対して見つかったアグリーメントまたは期限切れの状態</span><span class="sxs-lookup"><span data-stu-id="d12a3-102">Agreement found for the Protocol is in Disabled or Expired state</span></span>
## <a name="details"></a><span data-ttu-id="d12a3-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d12a3-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="d12a3-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d12a3-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="d12a3-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d12a3-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="d12a3-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d12a3-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="d12a3-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d12a3-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="d12a3-108">EDI</span><span class="sxs-lookup"><span data-stu-id="d12a3-108">EDI</span></span> |
|    <span data-ttu-id="d12a3-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d12a3-109">Component</span></span>    |                                       <span data-ttu-id="d12a3-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="d12a3-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="d12a3-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d12a3-111">Symbolic Name</span></span>  |                     <span data-ttu-id="d12a3-112">AgreementResolutionAgreementDiasbledOrExpired</span><span class="sxs-lookup"><span data-stu-id="d12a3-112">AgreementResolutionAgreementDiasbledOrExpired</span></span>                      |
|  <span data-ttu-id="d12a3-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d12a3-113">Message Text</span></span>   |      <span data-ttu-id="d12a3-114">アグリーメントが見つかりませんでした、{0}プロトコルが無効または期限切れのいずれかの状態。</span><span class="sxs-lookup"><span data-stu-id="d12a3-114">Agreement found for the {0} Protocol is in either Disabled or Expired state.</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="d12a3-115">説明</span><span class="sxs-lookup"><span data-stu-id="d12a3-115">Explanation</span></span>  
 <span data-ttu-id="d12a3-116">このエラー/警告/情報イベントは、BizTalk Server がアグリーメントに解決するのにが無効または期限切れの状態にあることを示します。</span><span class="sxs-lookup"><span data-stu-id="d12a3-116">This Error/Warning/Information event indicates BizTalk Server was able to resolve to an agreement but it is in disabled or expired state.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d12a3-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d12a3-117">User Action</span></span>  
 <span data-ttu-id="d12a3-118">このエラーを解決するには、アグリーメントを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="d12a3-118">To resolve this error, please enable the agreement.</span></span>