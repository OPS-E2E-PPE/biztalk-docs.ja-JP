---
title: "バッチに対応するビジネス Id が見つかりませんでした |。Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c9baf11-e9c6-482d-a47d-aa99852939bf
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f1027186e5b001d21e08bbabcfc100400a02d5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="could-not-find-business-identities-corresponding-to-batch"></a><span data-ttu-id="02198-102">バッチに対応するビジネス ID が見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="02198-102">Could not find Business Identities corresponding to batch</span></span>
## <a name="details"></a><span data-ttu-id="02198-103">詳細</span><span class="sxs-lookup"><span data-stu-id="02198-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="02198-104">製品名</span><span class="sxs-lookup"><span data-stu-id="02198-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="02198-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="02198-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="02198-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="02198-106">Event ID</span></span>|-|  
|<span data-ttu-id="02198-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="02198-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="02198-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="02198-108"> EDI</span></span>|  
|<span data-ttu-id="02198-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="02198-109">Component</span></span>|<span data-ttu-id="02198-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="02198-110">EDI Engine</span></span>|  
|<span data-ttu-id="02198-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="02198-111">Symbolic Name</span></span>|<span data-ttu-id="02198-112">IdentitiesNotFoundForBatch</span><span class="sxs-lookup"><span data-stu-id="02198-112">IdentitiesNotFoundForBatch</span></span>|  
|<span data-ttu-id="02198-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="02198-113">Message Text</span></span>|<span data-ttu-id="02198-114">バッチ {0} に対応するビジネス ID が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="02198-114">Could not find Business Identities corresponding to batch {0}.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="02198-115">説明</span><span class="sxs-lookup"><span data-stu-id="02198-115">Explanation</span></span>  
 <span data-ttu-id="02198-116">このエラー/警告/情報イベントは、データが不十分なために BizTalk Server がバッチ メッセージを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="02198-116">This Error/Warning/Information event indicates BizTalk Server was not able to process a batch message because of insufficient data.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="02198-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="02198-117">User Action</span></span>  
 <span data-ttu-id="02198-118">このエラーを解決するには、示された ID のバッチが親アグリーメントの [アグリーメントのプロパティ] に含まれていること、および正しいビジネス ID がアグリーメントに指定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="02198-118">To resolve this error, ensure that a batch with the given Id is present in the Agreement properties of the containing Agreement and proper business identities are specified for the agreement.</span></span>