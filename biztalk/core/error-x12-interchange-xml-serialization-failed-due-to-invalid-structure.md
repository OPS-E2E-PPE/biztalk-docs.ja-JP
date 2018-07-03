---
title: 無効な構造により、X12 インターチェンジの XML シリアル化に失敗しました。 TransactionSet または GE、ですが、見つかりません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d058fdbb-6be5-499f-86f7-0eb8a85c5fb2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05608a6e38d90a9e18004fa650ee6d5f7911109c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977555"
---
# <a name="x12-interchange-xml-serialization-failed-due-to-invalid-structure-looking-for-transactionset-or-ge-but-not-found"></a><span data-ttu-id="b4e78-103">無効な構造により、X12 インターチェンジの XML シリアル化に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="b4e78-103">X12 interchange Xml serialization failed due to invalid structure.</span></span> <span data-ttu-id="b4e78-104">TransactionSet または GE を検索しましたが、見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="b4e78-104">Looking for TransactionSet or GE, but not found</span></span>
## <a name="details"></a><span data-ttu-id="b4e78-105">詳細</span><span class="sxs-lookup"><span data-stu-id="b4e78-105">Details</span></span>  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b4e78-106">製品名</span><span class="sxs-lookup"><span data-stu-id="b4e78-106">Product Name</span></span>   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| <span data-ttu-id="b4e78-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b4e78-107">Product Version</span></span> |                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                             |
|    <span data-ttu-id="b4e78-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b4e78-108">Event ID</span></span>     |                                                         -                                                          |
|  <span data-ttu-id="b4e78-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b4e78-109">Event Source</span></span>   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b4e78-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="b4e78-110"> EDI</span></span>               |
|    <span data-ttu-id="b4e78-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b4e78-111">Component</span></span>    |                                                     <span data-ttu-id="b4e78-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="b4e78-112">EDI Engine</span></span>                                                     |
|  <span data-ttu-id="b4e78-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b4e78-113">Symbolic Name</span></span>  |                                           <span data-ttu-id="b4e78-114">X12TransactionSetOrGeNotFound</span><span class="sxs-lookup"><span data-stu-id="b4e78-114">X12TransactionSetOrGeNotFound</span></span>                                            |
|  <span data-ttu-id="b4e78-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b4e78-115">Message Text</span></span>   | <span data-ttu-id="b4e78-116">無効な構造により、X12 インターチェンジの XML シリアル化に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="b4e78-116">X12 interchange Xml serialization failed due to invalid structure.</span></span> <span data-ttu-id="b4e78-117">TransactionSet または GE を検索しましたが、見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="b4e78-117">Looking for TransactionSet or GE, but not found</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b4e78-118">説明</span><span class="sxs-lookup"><span data-stu-id="b4e78-118">Explanation</span></span>  
 <span data-ttu-id="b4e78-119">このエラー/警告/情報イベントは、インターチェンジの構造が無効だったため、送信パイプラインで送信インターチェンジをシリアル化できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="b4e78-119">This Error/Warning/Information event indicates that the send pipeline could not serialize the outgoing interchange because the structure of the interchange was invalid.</span></span> <span data-ttu-id="b4e78-120">この理由として、必要なヘッダーまたはトレーラーが存在しないか、無効だった可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b4e78-120">The reason could be that the required headers or trailers are not present or are invalid.</span></span> <span data-ttu-id="b4e78-121">これが発生するのは、グループのトランザクション セットの後に、別のトランザクション セットまたはグループ トレーラーが続いていない場合が考えられます。</span><span class="sxs-lookup"><span data-stu-id="b4e78-121">It could occur if a transaction set in a group is not followed by another transaction set or the group trailer.</span></span> <span data-ttu-id="b4e78-122">また、構造的整合性チェックに失敗した可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="b4e78-122">It could also occur if structural integrity checks failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b4e78-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b4e78-123">User Action</span></span>  
 <span data-ttu-id="b4e78-124">このエラーを解決するには、インターチェンジの構造を検証し、グループまたはトランザクション セットのヘッダーとトレーラーが有効であることを確認し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="b4e78-124">To resolve this error, verify the structure of the interchange, ensuring that the group or transaction set headers and trailers are valid, and then resend the interchange.</span></span>