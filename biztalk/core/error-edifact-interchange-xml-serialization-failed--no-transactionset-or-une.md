---
title: 無効な構造、ありません transactionSet または UNE のための Edifact インターチェンジの Xml シリアル化に失敗しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ce1c219-f2ed-46c1-ae4b-8a4206f7cd01
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f55bb6d0f5959a53781e7f48e69b89762a104377
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388918"
---
# <a name="edifact-interchange-xml-serialization-failed-due-to-invalid-structure-no-transactionset-or-une"></a><span data-ttu-id="20314-102">無効な構造、ありません transactionSet または UNE のための Edifact インターチェンジの Xml シリアル化に失敗しました</span><span class="sxs-lookup"><span data-stu-id="20314-102">Edifact interchange Xml serialization failed due to invalid structure, no transactionSet or UNE</span></span>
## <a name="details"></a><span data-ttu-id="20314-103">詳細</span><span class="sxs-lookup"><span data-stu-id="20314-103">Details</span></span>  
  
|                 |                                                                                                                         |
|-----------------|-------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="20314-104">製品名</span><span class="sxs-lookup"><span data-stu-id="20314-104">Product Name</span></span>   |                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                    |
| <span data-ttu-id="20314-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="20314-105">Product Version</span></span> |                               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                |
|    <span data-ttu-id="20314-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="20314-106">Event ID</span></span>     |                                                            -                                                            |
|  <span data-ttu-id="20314-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="20314-107">Event Source</span></span>   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="20314-108">EDI</span><span class="sxs-lookup"><span data-stu-id="20314-108">EDI</span></span>                  |
|    <span data-ttu-id="20314-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="20314-109">Component</span></span>    |                                                       <span data-ttu-id="20314-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="20314-110">EDI Engine</span></span>                                                        |
|  <span data-ttu-id="20314-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="20314-111">Symbolic Name</span></span>  |                                            <span data-ttu-id="20314-112">EfactTransactionSetOrUneNotFound</span><span class="sxs-lookup"><span data-stu-id="20314-112">EfactTransactionSetOrUneNotFound</span></span>                                             |
|  <span data-ttu-id="20314-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="20314-113">Message Text</span></span>   | <span data-ttu-id="20314-114">無効な構造により、EDIFACT インターチェンジの XML シリアル化に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="20314-114">Edifact interchange Xml serialization failed due to invalid structure.</span></span> <span data-ttu-id="20314-115">TransactionSet または UNE を検索しましたが、見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="20314-115">Looking for TransactionSet or UNE, but not found</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="20314-116">説明</span><span class="sxs-lookup"><span data-stu-id="20314-116">Explanation</span></span>  
 <span data-ttu-id="20314-117">このエラー/警告/情報イベントは、最初のセグメントが UNA または UNB のいずれのセグメントでもなかったため、EDI 受信パイプラインで受信 EDIFACT インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="20314-117">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming EDIFACT interchange because the first segment was neither a UNA or a UNB segment.</span></span> <span data-ttu-id="20314-118">UNA セグメントは省略可能ですが、UNB セグメントは必須です。</span><span class="sxs-lookup"><span data-stu-id="20314-118">The UNA segment is optional; the UNB segment is mandatory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="20314-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="20314-119">User Action</span></span>  
 <span data-ttu-id="20314-120">このエラーを解決するには、インターチェンジの送信者が、グループ内のトランザクション セットの後に別のトランザクション セットが続くか、または UNE セグメントが続くようにメッセージを構成していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="20314-120">To resolve this error, ensure that the sender of the interchange structures the message such that a transaction set in a group is either followed by another transaction set or a UNE segment.</span></span> <span data-ttu-id="20314-121">その後、送信者にインターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="20314-121">Have the sender then resend the interchange.</span></span>