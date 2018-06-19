---
title: トランザクション セットのスキーマを 1 つまたは複数のコントロールのセグメント ISA、IEA、GS、GE |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7589d8f0-c727-47df-afbc-77b0f190f3e2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff90a7ea80208f0a69ee8aca5c7593c7b6253c53
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241826"
---
# <a name="transaction-set-schema-contains-one-or-more-of-control-segments-isa-iea-gs-ge"></a><span data-ttu-id="e3a0f-102">トランザクション セットのスキーマに制御セグメント ISA、IEA、GS、および GE のうち 1 つ以上のセグメントが含まれています</span><span class="sxs-lookup"><span data-stu-id="e3a0f-102">Transaction set schema contains one or more of control segments ISA, IEA, GS, GE</span></span>
## <a name="details"></a><span data-ttu-id="e3a0f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e3a0f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e3a0f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e3a0f-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e3a0f-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e3a0f-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="e3a0f-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e3a0f-106">Event ID</span></span>|-|  
|<span data-ttu-id="e3a0f-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e3a0f-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e3a0f-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="e3a0f-108"> EDI</span></span>|  
|<span data-ttu-id="e3a0f-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e3a0f-109">Component</span></span>|<span data-ttu-id="e3a0f-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="e3a0f-110">EDI Engine</span></span>|  
|<span data-ttu-id="e3a0f-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e3a0f-111">Symbolic Name</span></span>|<span data-ttu-id="e3a0f-112">SchemaCode114EOtherControlSegmentsPresent</span><span class="sxs-lookup"><span data-stu-id="e3a0f-112">SchemaCode114EOtherControlSegmentsPresent</span></span>|  
|<span data-ttu-id="e3a0f-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e3a0f-113">Message Text</span></span>|<span data-ttu-id="e3a0f-114">トランザクション セットのスキーマに制御セグメント ISA、IEA、GS、および GE のうち 1 つ以上のセグメントが含まれています</span><span class="sxs-lookup"><span data-stu-id="e3a0f-114">Transaction set schema contains one or more of control segments ISA, IEA, GS, GE</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e3a0f-115">説明</span><span class="sxs-lookup"><span data-stu-id="e3a0f-115">Explanation</span></span>  
 <span data-ttu-id="e3a0f-116">このエラー/警告/情報イベントは、トランザクション セットのドキュメント スキーマで、少なくとも 1 つの ISA、IEA、GS、または GE セグメントが定義されていたため、受信パイプラインで受信トランザクション セットを処理できなかったか、または送信パイプラインで送信トランザクション セットを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="e3a0f-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming transaction set or the send pipeline could not process the outgoing transaction set because the document schema for the transaction set defined at least one ISA, IEA, GS, or GE segment.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e3a0f-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e3a0f-117">User Action</span></span>  
 <span data-ttu-id="e3a0f-118">このエラーを解決するには、ドキュメント スキーマの展開を解除し、スキーマから ISA、IEA、GS、または GE セグメントを削除して、スキーマを再展開します。</span><span class="sxs-lookup"><span data-stu-id="e3a0f-118">To resolve this error, undeploy the document schema, remove the ISA, IEA, GS, or GE segment from the schema, and then redeploy the schema.</span></span>