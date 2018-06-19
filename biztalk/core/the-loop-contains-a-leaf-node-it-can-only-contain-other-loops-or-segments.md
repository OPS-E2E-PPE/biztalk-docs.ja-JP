---
title: ループにリーフ ノードが含まれています。 その他のループまたはセグメントを含めることができますのみ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a0ee5e6-519d-4c95-8681-de5a37741d56
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d03349389fb108d434cce67afc5be13fd2a3d513
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278834"
---
# <a name="the-loop-contains-a-leaf-node-it-can-only-contain-other-loops-or-segments"></a><span data-ttu-id="d63dd-103">ループにリーフ ノードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d63dd-103">The loop contains a leaf node.</span></span> <span data-ttu-id="d63dd-104">ループに含めることができるのは、他のループまたはセグメントのみです</span><span class="sxs-lookup"><span data-stu-id="d63dd-104">It can only contain other Loops or Segments</span></span>
## <a name="details"></a><span data-ttu-id="d63dd-105">詳細</span><span class="sxs-lookup"><span data-stu-id="d63dd-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d63dd-106">製品名</span><span class="sxs-lookup"><span data-stu-id="d63dd-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d63dd-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d63dd-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="d63dd-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d63dd-108">Event ID</span></span>|-|  
|<span data-ttu-id="d63dd-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d63dd-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d63dd-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="d63dd-110"> EDI</span></span>|  
|<span data-ttu-id="d63dd-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d63dd-111">Component</span></span>|<span data-ttu-id="d63dd-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="d63dd-112">EDI Engine</span></span>|  
|<span data-ttu-id="d63dd-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d63dd-113">Symbolic Name</span></span>|<span data-ttu-id="d63dd-114">SchemaCode125ELoopContainsLeafNode</span><span class="sxs-lookup"><span data-stu-id="d63dd-114">SchemaCode125ELoopContainsLeafNode</span></span>|  
|<span data-ttu-id="d63dd-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d63dd-115">Message Text</span></span>|<span data-ttu-id="d63dd-116">ループにリーフ ノードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d63dd-116">The loop contains a leaf node.</span></span> <span data-ttu-id="d63dd-117">ループに含めることができるのは、他のループまたはセグメントのみです</span><span class="sxs-lookup"><span data-stu-id="d63dd-117">It can only contain other Loops or Segments</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d63dd-118">説明</span><span class="sxs-lookup"><span data-stu-id="d63dd-118">Explanation</span></span>  
 <span data-ttu-id="d63dd-119">このエラー/警告/情報イベントは、インターチェンジがドキュメントのスキーマに準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="d63dd-119">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange, because the interchange did not conform to the document schema.</span></span> <span data-ttu-id="d63dd-120">この場合、ループには子のないリーフ ノードが含まれていましたが、スキーマではループには他のループまたはセグメントのみを含むことができると指定されています。</span><span class="sxs-lookup"><span data-stu-id="d63dd-120">In this case, a loop contained a childless leaf node, whereas the schema specified that the loop could only contain other loops or segments.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d63dd-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d63dd-121">User Action</span></span>  
 <span data-ttu-id="d63dd-122">このエラーを解決するには、ループにリーフ ノードが含まれないようにインターチェンジの送信者にループを修正してもらい、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="d63dd-122">To resolve this error, have the sender of the interchange fix the loop so that it does not contain leaf nodes, and then resend the interchange.</span></span>