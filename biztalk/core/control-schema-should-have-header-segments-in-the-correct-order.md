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
ms.openlocfilehash: fee939bb14b98dc66373d754af13d9f4bb327f2a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354461"
---
# <a name="control-schema-should-have-header-segments-in-the-correct-order"></a><span data-ttu-id="3dda9-102">コントロールのスキーマが正しい順序でのヘッダー セグメントがあります。</span><span class="sxs-lookup"><span data-stu-id="3dda9-102">Control schema should have header segments in the correct order</span></span>
## <a name="details"></a><span data-ttu-id="3dda9-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3dda9-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="3dda9-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3dda9-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="3dda9-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3dda9-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="3dda9-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3dda9-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="3dda9-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3dda9-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="3dda9-108">EDI</span><span class="sxs-lookup"><span data-stu-id="3dda9-108">EDI</span></span> |
|    <span data-ttu-id="3dda9-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3dda9-109">Component</span></span>    |                                       <span data-ttu-id="3dda9-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="3dda9-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="3dda9-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3dda9-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="3dda9-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3dda9-112">Message Text</span></span>   |  <span data-ttu-id="3dda9-113">コントロールのスキーマは、次の順序でセグメントが必要です。ISA GS ST.SE GE IEA</span><span class="sxs-lookup"><span data-stu-id="3dda9-113">Control schema should have segments in the following order: ISA GS ST .... SE GE IEA</span></span>  |
  
## <a name="explanation"></a><span data-ttu-id="3dda9-114">説明</span><span class="sxs-lookup"><span data-stu-id="3dda9-114">Explanation</span></span>  
 <span data-ttu-id="3dda9-115">このエラー/警告/情報イベントは、EDI が受信することを示します、インターチェンジに正しい順序でヘッダーと、インターチェンジ、グループ、およびトランザクション セットのトレーラーがないために、パイプラインは受信したインターチェンジを処理できませんでした。</span><span class="sxs-lookup"><span data-stu-id="3dda9-115">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming interchange because the headers and trailers for the interchange, groups, and transaction sets were not in the correct order in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3dda9-116">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3dda9-116">User Action</span></span>  
 <span data-ttu-id="3dda9-117">このエラーを解決するには、こと、インターチェンジに正しい順序では、ISA、GS、および ST ヘッダーと SE、GE、および IEA トレーラー、およびもらい、インターチェンジを確認します。</span><span class="sxs-lookup"><span data-stu-id="3dda9-117">To resolve this error, ensure that the ISA, GS, and ST headers, and the SE, GE, and IEA trailers, are in the correct order in the interchange, and then resend the interchange.</span></span>