---
title: "区切り記号が一意ではありません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c37cc55-8923-4124-9004-91ee5093df9c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cc4f9c8eeb3a16fdd45222313bfb013dbf32ae5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="delimiters-are-not-unique"></a><span data-ttu-id="60812-102">区切り記号が一意ではありません</span><span class="sxs-lookup"><span data-stu-id="60812-102">Delimiters are not unique</span></span>
## <a name="details"></a><span data-ttu-id="60812-103">詳細</span><span class="sxs-lookup"><span data-stu-id="60812-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="60812-104">製品名</span><span class="sxs-lookup"><span data-stu-id="60812-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="60812-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="60812-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="60812-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="60812-106">Event ID</span></span>|-|  
|<span data-ttu-id="60812-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="60812-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="60812-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="60812-108"> EDI</span></span>|  
|<span data-ttu-id="60812-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="60812-109">Component</span></span>|<span data-ttu-id="60812-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="60812-110">EDI Engine</span></span>|  
|<span data-ttu-id="60812-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="60812-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="60812-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="60812-112">Message Text</span></span>|<span data-ttu-id="60812-113">区切り記号が一意ではありません</span><span class="sxs-lookup"><span data-stu-id="60812-113">Delimiters are not unique</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="60812-114">説明</span><span class="sxs-lookup"><span data-stu-id="60812-114">Explanation</span></span>  
 <span data-ttu-id="60812-115">このエラー/警告/情報イベントは、インターチェンジで識別されてインターチェンジのファセットを区切るために使用されている区切り記号のうち、複数が同じ記号であったため、EDI 送信パイプラインで送信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="60812-115">This Error/Warning/Information event indicates that the EDI send pipeline could not process an outgoing interchange because two or more of the separators identified in the interchange, and used to separate facets of the interchange, were the same.</span></span> <span data-ttu-id="60812-116">区切り記号は、X12 インターチェンジの ISA セグメントと EDIFACT インターチェンジの UNA セグメントで識別されます。</span><span class="sxs-lookup"><span data-stu-id="60812-116">The separators are identified in the ISA segment of an X12 interchange and in the UNA segment of an EDIFACT interchange.</span></span> <span data-ttu-id="60812-117">同じ値を持つ複数の区切り記号は、保存されたバッチ シナリオで発生することがあります。または、インターチェンジがパススルー送信を経由して受信され、その後、送信ポートによって MessageBox で XML ファイルとして取得される場合に、発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="60812-117">Two or more separators with the same value can occur in a preserved batch scenario, or if an interchange is received via a passthrough transmit and then picked up by the send port as an XML file in the MessageBox.</span></span> <span data-ttu-id="60812-118">このエラー状態が発生すると、インターチェンジの処理は失敗します。</span><span class="sxs-lookup"><span data-stu-id="60812-118">This error condition will cause processing of the interchange to fail.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="60812-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="60812-119">User Action</span></span>  
 <span data-ttu-id="60812-120">このエラーを解決するには、インターチェンジのどの区切り記号が同じ値を持っているかを特定し、いずれかの区切り記号の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="60812-120">To resolve this error, identify which separators in the interchange have the same value, and change the value of one of the separators.</span></span>