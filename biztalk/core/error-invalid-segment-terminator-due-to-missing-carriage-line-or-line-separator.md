---
title: インターチェンジで構造エラーが。 可能性の高い原因は復帰がないため、無効なセグメントの終端記号と、または改行区切り |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 035e37d5-d4a8-49d0-8d75-3bcf2426cac7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49281421130fad2a28f829efda2b8be14adededc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388745"
---
# <a name="the-interchange-had-structural-error-a-likely-cause-is-invalid-segment-terminator-due-to-missing-carriage-line-and-or-line-feed-seperators"></a><span data-ttu-id="051f2-103">インターチェンジで構造エラーが。</span><span class="sxs-lookup"><span data-stu-id="051f2-103">The interchange had structural error.</span></span> <span data-ttu-id="051f2-104">可能性の高い原因は復帰がないため、無効なセグメントの終端記号と、または改行区切り</span><span class="sxs-lookup"><span data-stu-id="051f2-104">A likely cause is invalid segment terminator due to missing Carriage Line and-or Line Feed seperators</span></span>
## <a name="details"></a><span data-ttu-id="051f2-105">詳細</span><span class="sxs-lookup"><span data-stu-id="051f2-105">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="051f2-106">製品名</span><span class="sxs-lookup"><span data-stu-id="051f2-106">Product Name</span></span>   |                                                                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                                   |
| <span data-ttu-id="051f2-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="051f2-107">Product Version</span></span> |                                                                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                                               |
|    <span data-ttu-id="051f2-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="051f2-108">Event ID</span></span>     |                                                                                                                                           -                                                                                                                                           |
|  <span data-ttu-id="051f2-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="051f2-109">Event Source</span></span>   |                                                                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="051f2-110">EDI</span><span class="sxs-lookup"><span data-stu-id="051f2-110">EDI</span></span>                                                                                                 |
|    <span data-ttu-id="051f2-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="051f2-111">Component</span></span>    |                                                                                                                                      <span data-ttu-id="051f2-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="051f2-112">EDI Engine</span></span>                                                                                                                                       |
|  <span data-ttu-id="051f2-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="051f2-113">Symbolic Name</span></span>  |                                                                                                                        <span data-ttu-id="051f2-114">EfactInterchangeStructuralErrorAfterUnb</span><span class="sxs-lookup"><span data-stu-id="051f2-114">EfactInterchangeStructuralErrorAfterUnb</span></span>                                                                                                                        |
|  <span data-ttu-id="051f2-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="051f2-115">Message Text</span></span>   | <span data-ttu-id="051f2-116">Id を持つインターチェンジ '{0}'、送信者 id'{1}'、受信者 id '{2}' 構造エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="051f2-116">The interchange with id '{0}', with sender id '{1}', receiver id '{2}' had structural error.</span></span> <span data-ttu-id="051f2-117">可能性の高い原因は、復帰や改行の区切りがないため、無効なセグメント終端記号です。</span><span class="sxs-lookup"><span data-stu-id="051f2-117">A likely cause is invalid segment terminator due to missing Carriage Line and/or Line Feed seperators.</span></span> <span data-ttu-id="051f2-118">詳細については、エラーが中断されていますが後の部分が保留キューを参照します。</span><span class="sxs-lookup"><span data-stu-id="051f2-118">The part after the error is being suspended, refer to Suspended Queue for details</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="051f2-119">説明</span><span class="sxs-lookup"><span data-stu-id="051f2-119">Explanation</span></span>  
 <span data-ttu-id="051f2-120">このエラー/警告/情報イベントは、受信パイプラインのことを示します、インターチェンジ内のセグメントに必要なセグメント終端記号がないため、パイプライン、またはバッチ処理オーケストレーション、EDIFACT インターチェンジを処理できなかったを送信します。</span><span class="sxs-lookup"><span data-stu-id="051f2-120">This Error/Warning/Information event indicates that the receive pipeline, send pipeline, or batching orchestration could not process the EDIFACT interchange, because a segment in the interchange did not have the required segment terminator.</span></span> <span data-ttu-id="051f2-121">受信インターチェンジの区切り記号は UNA セグメントで識別されます。 または UNA セグメントが存在しない場合は、EfactDelimiters パイプライン プロパティ。</span><span class="sxs-lookup"><span data-stu-id="051f2-121">For an incoming interchange, the separators are identified in the UNA Segment, or if the UNA segment is not present, the EfactDelimiters pipeline property.</span></span> <span data-ttu-id="051f2-122">送信インターチェンジの場合は、区切り記号は、EDI のプロパティ ダイアログ ボックスの UNA セグメントの定義 ページで識別されます。</span><span class="sxs-lookup"><span data-stu-id="051f2-122">For an outgoing interchange, the separators are identified in the UNA Segment Definition page of the EDI Properties dialog box.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="051f2-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="051f2-123">User Action</span></span>  
 <span data-ttu-id="051f2-124">このエラーを解決するのには、インターチェンジ内のすべてのセグメントが必要なセグメント終端記号があるし、インターチェンジを再送信があるを確認します。</span><span class="sxs-lookup"><span data-stu-id="051f2-124">To resolve this error, ensure that all segments in the interchange have the required segment terminator, and then have the interchange resent.</span></span>