---
title: 制御スキーマが正しい順序でヘッダー セグメントを持つ必要があります |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88f38e8f-243a-467f-84bd-a232ef148b4b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3362bce20e1e7d31fa870a5376128d2d721c11f9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237858"
---
# <a name="control-schema-should-have-header-segments-in-the-correct-order"></a><span data-ttu-id="0236a-102">制御スキーマにはヘッダー セグメントが正しい順序で記述されている必要があります</span><span class="sxs-lookup"><span data-stu-id="0236a-102">Control schema should have header segments in the correct order</span></span>
## <a name="details"></a><span data-ttu-id="0236a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0236a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0236a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0236a-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="0236a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0236a-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="0236a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0236a-106">Event ID</span></span>|-|  
|<span data-ttu-id="0236a-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0236a-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0236a-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0236a-108"> EDI</span></span>|  
|<span data-ttu-id="0236a-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0236a-109">Component</span></span>|<span data-ttu-id="0236a-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="0236a-110">EDI Engine</span></span>|  
|<span data-ttu-id="0236a-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0236a-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="0236a-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0236a-112">Message Text</span></span>|<span data-ttu-id="0236a-113">制御スキーマでは、次の順序でセグメントがあります: ISA GS ST.SE GE IEA</span><span class="sxs-lookup"><span data-stu-id="0236a-113">Control schema should have segments in the following order: ISA GS ST .... SE GE IEA</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0236a-114">説明</span><span class="sxs-lookup"><span data-stu-id="0236a-114">Explanation</span></span>  
 <span data-ttu-id="0236a-115">このエラー/警告/情報イベントは、インターチェンジ、グループ、およびトランザクション セットのヘッダーとトレーラーが、インターチェンジに正しい順序で記述されていなかったため、EDI 受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="0236a-115">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming interchange because the headers and trailers for the interchange, groups, and transaction sets were not in the correct order in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0236a-116">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0236a-116">User Action</span></span>  
 <span data-ttu-id="0236a-117">このエラーを解決するには、ISA、GS、および ST ヘッダーと、SE、GE、および IEA トレーラーが、インターチェンジに正しい順序で記述されていることを確認してから、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="0236a-117">To resolve this error, ensure that the ISA, GS, and ST headers, and the SE, GE, and IEA trailers, are in the correct order in the interchange, and then resend the interchange.</span></span>