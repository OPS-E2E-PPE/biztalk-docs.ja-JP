---
title: "この要素には無効な構造 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb94843c-cd21-48e3-ba30-aed0518b4d78
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b825fb0d2f5b4fe985a2024b1c97e21f4308b58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-element-has-an-invalid-structure"></a><span data-ttu-id="d5b2a-102">要素の構造が無効です</span><span class="sxs-lookup"><span data-stu-id="d5b2a-102">The element has an invalid structure</span></span>
## <a name="details"></a><span data-ttu-id="d5b2a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d5b2a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d5b2a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d5b2a-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d5b2a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d5b2a-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="d5b2a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d5b2a-106">Event ID</span></span>|-|  
|<span data-ttu-id="d5b2a-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d5b2a-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d5b2a-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="d5b2a-108"> EDI</span></span>|  
|<span data-ttu-id="d5b2a-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d5b2a-109">Component</span></span>|<span data-ttu-id="d5b2a-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="d5b2a-110">EDI Engine</span></span>|  
|<span data-ttu-id="d5b2a-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d5b2a-111">Symbolic Name</span></span>|<span data-ttu-id="d5b2a-112">X12NseStructurallyInvalidElementDescription</span><span class="sxs-lookup"><span data-stu-id="d5b2a-112">X12NseStructurallyInvalidElementDescription</span></span>|  
|<span data-ttu-id="d5b2a-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d5b2a-113">Message Text</span></span>|<span data-ttu-id="d5b2a-114">要素 '{0}' の構造が無効です</span><span class="sxs-lookup"><span data-stu-id="d5b2a-114">The element '{0}' has an invalid structure</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d5b2a-115">説明</span><span class="sxs-lookup"><span data-stu-id="d5b2a-115">Explanation</span></span>  
 <span data-ttu-id="d5b2a-116">このエラー/警告/情報イベントは、データ要素に、該当するスキーマで指定されている構造がなかったため、受信パイプラインで受信インターチェンジを処理できなかったか、または送信パイプラインで送信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="d5b2a-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange, or the send pipeline could not process the outgoing interchange, because a data element did not have the structure specified by the applicable schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d5b2a-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d5b2a-117">User Action</span></span>  
 <span data-ttu-id="d5b2a-118">このエラーを解決するには、送信インターチェンジのデータ要素の構造を修正するか、またはインターチェンジの送信者に対して、受信インターチェンジのデータ要素の構造を変更し、ドキュメント スキーマに準拠するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="d5b2a-118">To resolve this error, fix the structure of the data element in the outgoing interchange, or have the sender of the interchange fix the structure of the data element in the incoming interchange, so that it conforms to the document schema.</span></span>