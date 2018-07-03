---
title: バッチに対応するビジネス Id が見つかりませんでした |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c9baf11-e9c6-482d-a47d-aa99852939bf
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a5076bc5c4887e1819ab64a32bb987fb9b06248
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975827"
---
# <a name="could-not-find-business-identities-corresponding-to-batch"></a><span data-ttu-id="c5479-102">バッチに対応するビジネス ID が見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="c5479-102">Could not find Business Identities corresponding to batch</span></span>
## <a name="details"></a><span data-ttu-id="c5479-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c5479-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="c5479-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c5479-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="c5479-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c5479-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="c5479-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c5479-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="c5479-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c5479-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c5479-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="c5479-108"> EDI</span></span> |
|    <span data-ttu-id="c5479-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c5479-109">Component</span></span>    |                                       <span data-ttu-id="c5479-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="c5479-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="c5479-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c5479-111">Symbolic Name</span></span>  |                               <span data-ttu-id="c5479-112">IdentitiesNotFoundForBatch</span><span class="sxs-lookup"><span data-stu-id="c5479-112">IdentitiesNotFoundForBatch</span></span>                               |
|  <span data-ttu-id="c5479-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c5479-113">Message Text</span></span>   |             <span data-ttu-id="c5479-114">バッチに対応するビジネス Id が見つかりませんでした。{0}します。</span><span class="sxs-lookup"><span data-stu-id="c5479-114">Could not find Business Identities corresponding to batch {0}.</span></span>             |
  
## <a name="explanation"></a><span data-ttu-id="c5479-115">説明</span><span class="sxs-lookup"><span data-stu-id="c5479-115">Explanation</span></span>  
 <span data-ttu-id="c5479-116">このエラー/警告/情報イベントは、データが不十分なために BizTalk Server がバッチ メッセージを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="c5479-116">This Error/Warning/Information event indicates BizTalk Server was not able to process a batch message because of insufficient data.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c5479-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c5479-117">User Action</span></span>  
 <span data-ttu-id="c5479-118">このエラーを解決するには、示された ID のバッチが親アグリーメントの [アグリーメントのプロパティ] に含まれていること、および正しいビジネス ID がアグリーメントに指定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c5479-118">To resolve this error, ensure that a batch with the given Id is present in the Agreement properties of the containing Agreement and proper business identities are specified for the agreement.</span></span>