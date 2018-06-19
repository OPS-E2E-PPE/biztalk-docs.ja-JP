---
title: 無効な構造体、ありません transactionSet または UNE により Edifact インターチェンジ Xml シリアル化が失敗しました |。Microsoft ドキュメント
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
ms.openlocfilehash: f5c6aae4bc3ed16afffadec774eaeac9ed64808d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241730"
---
# <a name="edifact-interchange-xml-serialization-failed-due-to-invalid-structure-no-transactionset-or-une"></a><span data-ttu-id="0db3c-102">無効な構造により、EDIFACT インターチェンジの XML シリアル化に失敗しました。TransactionSet または UNE はありません</span><span class="sxs-lookup"><span data-stu-id="0db3c-102">Edifact interchange Xml serialization failed due to invalid structure, no transactionSet or UNE</span></span>
## <a name="details"></a><span data-ttu-id="0db3c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0db3c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0db3c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0db3c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="0db3c-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0db3c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="0db3c-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0db3c-106">Event ID</span></span>|-|  
|<span data-ttu-id="0db3c-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0db3c-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0db3c-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0db3c-108"> EDI</span></span>|  
|<span data-ttu-id="0db3c-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0db3c-109">Component</span></span>|<span data-ttu-id="0db3c-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="0db3c-110">EDI Engine</span></span>|  
|<span data-ttu-id="0db3c-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0db3c-111">Symbolic Name</span></span>|<span data-ttu-id="0db3c-112">EfactTransactionSetOrUneNotFound</span><span class="sxs-lookup"><span data-stu-id="0db3c-112">EfactTransactionSetOrUneNotFound</span></span>|  
|<span data-ttu-id="0db3c-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0db3c-113">Message Text</span></span>|<span data-ttu-id="0db3c-114">無効な構造により、EDIFACT インターチェンジの XML シリアル化に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="0db3c-114">Edifact interchange Xml serialization failed due to invalid structure.</span></span> <span data-ttu-id="0db3c-115">TransactionSet または UNE を検索しましたが、見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="0db3c-115">Looking for TransactionSet or UNE, but not found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0db3c-116">説明</span><span class="sxs-lookup"><span data-stu-id="0db3c-116">Explanation</span></span>  
 <span data-ttu-id="0db3c-117">このエラー/警告/情報イベントは、最初のセグメントが UNA または UNB のいずれのセグメントでもなかったため、EDI 受信パイプラインで受信 EDIFACT インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="0db3c-117">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming EDIFACT interchange because the first segment was neither a UNA or a UNB segment.</span></span> <span data-ttu-id="0db3c-118">UNA セグメントは省略可能ですが、UNB セグメントは必須です。</span><span class="sxs-lookup"><span data-stu-id="0db3c-118">The UNA segment is optional; the UNB segment is mandatory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0db3c-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0db3c-119">User Action</span></span>  
 <span data-ttu-id="0db3c-120">このエラーを解決するには、インターチェンジの送信者が、グループ内のトランザクション セットの後に別のトランザクション セットが続くか、または UNE セグメントが続くようにメッセージを構成していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0db3c-120">To resolve this error, ensure that the sender of the interchange structures the message such that a transaction set in a group is either followed by another transaction set or a UNE segment.</span></span> <span data-ttu-id="0db3c-121">その後、送信者にインターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="0db3c-121">Have the sender then resend the interchange.</span></span>