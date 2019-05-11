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
ms.openlocfilehash: 3d9d49d4fe30f8e3dd85f32c17e834f45550024d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354362"
---
# <a name="could-not-find-business-identities-corresponding-to-batch"></a><span data-ttu-id="20f13-102">バッチに対応するビジネス Id が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="20f13-102">Could not find Business Identities corresponding to batch</span></span>
## <a name="details"></a><span data-ttu-id="20f13-103">詳細</span><span class="sxs-lookup"><span data-stu-id="20f13-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="20f13-104">製品名</span><span class="sxs-lookup"><span data-stu-id="20f13-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="20f13-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="20f13-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="20f13-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="20f13-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="20f13-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="20f13-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="20f13-108">EDI</span><span class="sxs-lookup"><span data-stu-id="20f13-108">EDI</span></span> |
|    <span data-ttu-id="20f13-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="20f13-109">Component</span></span>    |                                       <span data-ttu-id="20f13-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="20f13-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="20f13-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="20f13-111">Symbolic Name</span></span>  |                               <span data-ttu-id="20f13-112">IdentitiesNotFoundForBatch</span><span class="sxs-lookup"><span data-stu-id="20f13-112">IdentitiesNotFoundForBatch</span></span>                               |
|  <span data-ttu-id="20f13-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="20f13-113">Message Text</span></span>   |             <span data-ttu-id="20f13-114">バッチに対応するビジネス Id が見つかりませんでした。{0}します。</span><span class="sxs-lookup"><span data-stu-id="20f13-114">Could not find Business Identities corresponding to batch {0}.</span></span>             |
  
## <a name="explanation"></a><span data-ttu-id="20f13-115">説明</span><span class="sxs-lookup"><span data-stu-id="20f13-115">Explanation</span></span>  
 <span data-ttu-id="20f13-116">このエラー/警告/情報イベントは、データが不十分なために BizTalk Server がバッチ メッセージを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="20f13-116">This Error/Warning/Information event indicates BizTalk Server was not able to process a batch message because of insufficient data.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="20f13-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="20f13-117">User Action</span></span>  
 <span data-ttu-id="20f13-118">このエラーを解決するには、示された ID のバッチが親アグリーメントの [アグリーメントのプロパティ] に含まれていること、および正しいビジネス ID がアグリーメントに指定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="20f13-118">To resolve this error, ensure that a batch with the given Id is present in the Agreement properties of the containing Agreement and proper business identities are specified for the agreement.</span></span>