---
title: バッチに対応するアグリーメントが見つかりませんでした |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d1c0480-9a6f-481a-9143-e5a55707c3b5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b505c9c3919a11e0832ac88a8d20ad8f85d2706
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390176"
---
# <a name="could-not-find-an-agreement-corresponding-to-batch"></a><span data-ttu-id="637c1-102">バッチに対応するアグリーメントが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="637c1-102">Could not find an Agreement corresponding to batch</span></span>
## <a name="details"></a><span data-ttu-id="637c1-103">詳細</span><span class="sxs-lookup"><span data-stu-id="637c1-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="637c1-104">製品名</span><span class="sxs-lookup"><span data-stu-id="637c1-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="637c1-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="637c1-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="637c1-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="637c1-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="637c1-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="637c1-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="637c1-108">EDI</span><span class="sxs-lookup"><span data-stu-id="637c1-108">EDI</span></span> |
|    <span data-ttu-id="637c1-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="637c1-109">Component</span></span>    |                                       <span data-ttu-id="637c1-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="637c1-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="637c1-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="637c1-111">Symbolic Name</span></span>  |                               <span data-ttu-id="637c1-112">AgreementNotFoundForBatch</span><span class="sxs-lookup"><span data-stu-id="637c1-112">AgreementNotFoundForBatch</span></span>                                |
|  <span data-ttu-id="637c1-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="637c1-113">Message Text</span></span>   |                <span data-ttu-id="637c1-114">バッチに対応するアグリーメントが見つかりませんでした。{0}します。</span><span class="sxs-lookup"><span data-stu-id="637c1-114">Could not find an Agreement corresponding to batch {0}.</span></span>                 |
  
## <a name="explanation"></a><span data-ttu-id="637c1-115">説明</span><span class="sxs-lookup"><span data-stu-id="637c1-115">Explanation</span></span>  
 <span data-ttu-id="637c1-116">このエラー/警告/情報イベントは、バッチの開始/停止時またはバッチ メッセージの処理時に、BizTalk Server がこの ID に対応したバッチを見つけることができなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="637c1-116">This Error/Warning/Information event indicates BizTalk Server was unable to find a Batch corresponding to this Id while trying to start/stop a batch or process a batch message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="637c1-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="637c1-117">User Action</span></span>  
 <span data-ttu-id="637c1-118">このエラーを解決するには、指定された ID のバッチが親アグリーメントの [アグリーメントのプロパティ] に存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="637c1-118">To resolve this error, ensure that a batch with the given Id is present in the Agreement properties of the containing Agreement.</span></span>