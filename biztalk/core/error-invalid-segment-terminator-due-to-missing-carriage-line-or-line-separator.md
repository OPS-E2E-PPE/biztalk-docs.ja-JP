---
title: インターチェンジで構造エラーが見つかりました。 考えられる原因は、復帰行がないための無効なセグメント終端記号と -改行のライン フィード、または |Microsoft ドキュメント
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
ms.openlocfilehash: 6e983e44b1284bf16e06dbfc90159afc0ed5608c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241746"
---
# <a name="the-interchange-had-structural-error-a-likely-cause-is-invalid-segment-terminator-due-to-missing-carriage-line-and-or-line-feed-seperators"></a><span data-ttu-id="64c86-103">インターチェンジで構造エラーが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="64c86-103">The interchange had structural error.</span></span> <span data-ttu-id="64c86-104">考えられる原因は、復帰行がないための無効なセグメント終端記号と- や改行のライン フィード</span><span class="sxs-lookup"><span data-stu-id="64c86-104">A likely cause is invalid segment terminator due to missing Carriage Line and-or Line Feed seperators</span></span>
## <a name="details"></a><span data-ttu-id="64c86-105">詳細</span><span class="sxs-lookup"><span data-stu-id="64c86-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="64c86-106">製品名</span><span class="sxs-lookup"><span data-stu-id="64c86-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="64c86-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="64c86-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="64c86-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="64c86-108">Event ID</span></span>|-|  
|<span data-ttu-id="64c86-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="64c86-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="64c86-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="64c86-110"> EDI</span></span>|  
|<span data-ttu-id="64c86-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="64c86-111">Component</span></span>|<span data-ttu-id="64c86-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="64c86-112">EDI Engine</span></span>|  
|<span data-ttu-id="64c86-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="64c86-113">Symbolic Name</span></span>|<span data-ttu-id="64c86-114">EfactInterchangeStructuralErrorAfterUnb</span><span class="sxs-lookup"><span data-stu-id="64c86-114">EfactInterchangeStructuralErrorAfterUnb</span></span>|  
|<span data-ttu-id="64c86-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="64c86-115">Message Text</span></span>|<span data-ttu-id="64c86-116">Id '{0}'、送信者 id '{1}' で、インターチェンジ受信者 id '{2}' には、構造エラーが必要があります。</span><span class="sxs-lookup"><span data-stu-id="64c86-116">The interchange with id '{0}', with sender id '{1}', receiver id '{2}' had structural error.</span></span> <span data-ttu-id="64c86-117">復帰や改行の区切り記号がないため、セグメント終端記号が無効になっていることが原因として考えられます。</span><span class="sxs-lookup"><span data-stu-id="64c86-117">A likely cause is invalid segment terminator due to missing Carriage Line and/or Line Feed seperators.</span></span> <span data-ttu-id="64c86-118">エラー発生後の部分は中断されています。詳細については、保留キューを参照してください。</span><span class="sxs-lookup"><span data-stu-id="64c86-118">The part after the error is being suspended, refer to Suspended Queue for details</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="64c86-119">説明</span><span class="sxs-lookup"><span data-stu-id="64c86-119">Explanation</span></span>  
 <span data-ttu-id="64c86-120">このエラー/警告/情報イベントは、インターチェンジ内のセグメントに必要なセグメント終端記号がなかったため、受信パイプライン、送信パイプライン、またはバッチ処理オーケストレーションで EDIFACT インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="64c86-120">This Error/Warning/Information event indicates that the receive pipeline, send pipeline, or batching orchestration could not process the EDIFACT interchange, because a segment in the interchange did not have the required segment terminator.</span></span> <span data-ttu-id="64c86-121">受信インターチェンジの場合、区切り記号は UNA セグメントで識別されます。UNA セグメントがない場合は、EfactDelimiters パイプライン プロパティで識別されます。</span><span class="sxs-lookup"><span data-stu-id="64c86-121">For an incoming interchange, the separators are identified in the UNA Segment, or if the UNA segment is not present, the EfactDelimiters pipeline property.</span></span> <span data-ttu-id="64c86-122">送信インターチェンジの場合、区切り記号は [EDI のプロパティ] ダイアログ ボックスの [UNA セグメントの定義] ページで識別されます。</span><span class="sxs-lookup"><span data-stu-id="64c86-122">For an outgoing interchange, the separators are identified in the UNA Segment Definition page of the EDI Properties dialog box.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="64c86-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="64c86-123">User Action</span></span>  
 <span data-ttu-id="64c86-124">このエラーを解決するには、インターチェンジのすべてのセグメントに必要なセグメント終端記号が含まれていることを確認し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="64c86-124">To resolve this error, ensure that all segments in the interchange have the required segment terminator, and then have the interchange resent.</span></span>