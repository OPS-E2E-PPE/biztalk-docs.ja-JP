---
title: コントロールのスキーマが正しい順序でのヘッダー セグメントが必要 |Microsoft Docs
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
ms.openlocfilehash: 2c86b8d66526c0406faedeac0aedbbe0e1b270ad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967923"
---
# <a name="control-schema-should-have-header-segments-in-the-correct-order"></a><span data-ttu-id="35733-102">制御スキーマにはヘッダー セグメントが正しい順序で記述されている必要があります</span><span class="sxs-lookup"><span data-stu-id="35733-102">Control schema should have header segments in the correct order</span></span>
## <a name="details"></a><span data-ttu-id="35733-103">詳細</span><span class="sxs-lookup"><span data-stu-id="35733-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="35733-104">製品名</span><span class="sxs-lookup"><span data-stu-id="35733-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="35733-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="35733-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="35733-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="35733-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="35733-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="35733-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="35733-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="35733-108"> EDI</span></span> |
|    <span data-ttu-id="35733-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="35733-109">Component</span></span>    |                                       <span data-ttu-id="35733-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="35733-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="35733-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="35733-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="35733-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="35733-112">Message Text</span></span>   |  <span data-ttu-id="35733-113">制御スキーマでは、次の順序でセグメントがあります: ISA GS ST.SE GE IEA</span><span class="sxs-lookup"><span data-stu-id="35733-113">Control schema should have segments in the following order: ISA GS ST .... SE GE IEA</span></span>  |
  
## <a name="explanation"></a><span data-ttu-id="35733-114">説明</span><span class="sxs-lookup"><span data-stu-id="35733-114">Explanation</span></span>  
 <span data-ttu-id="35733-115">このエラー/警告/情報イベントは、インターチェンジ、グループ、およびトランザクション セットのヘッダーとトレーラーが、インターチェンジに正しい順序で記述されていなかったため、EDI 受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="35733-115">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming interchange because the headers and trailers for the interchange, groups, and transaction sets were not in the correct order in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="35733-116">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="35733-116">User Action</span></span>  
 <span data-ttu-id="35733-117">このエラーを解決するには、ISA、GS、および ST ヘッダーと、SE、GE、および IEA トレーラーが、インターチェンジに正しい順序で記述されていることを確認してから、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="35733-117">To resolve this error, ensure that the ISA, GS, and ST headers, and the SE, GE, and IEA trailers, are in the correct order in the interchange, and then resend the interchange.</span></span>