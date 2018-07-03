---
title: 区切り記号が一意ではありません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c37cc55-8923-4124-9004-91ee5093df9c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d724533fb89d3f4d43654aadaf43094adb80e06
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966745"
---
# <a name="delimiters-are-not-unique"></a><span data-ttu-id="2044f-102">区切り記号が一意ではありません</span><span class="sxs-lookup"><span data-stu-id="2044f-102">Delimiters are not unique</span></span>
## <a name="details"></a><span data-ttu-id="2044f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="2044f-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="2044f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="2044f-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="2044f-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="2044f-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="2044f-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2044f-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="2044f-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="2044f-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2044f-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="2044f-108"> EDI</span></span> |
|    <span data-ttu-id="2044f-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2044f-109">Component</span></span>    |                                       <span data-ttu-id="2044f-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="2044f-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="2044f-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="2044f-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="2044f-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="2044f-112">Message Text</span></span>   |                               <span data-ttu-id="2044f-113">区切り記号が一意ではありません</span><span class="sxs-lookup"><span data-stu-id="2044f-113">Delimiters are not unique</span></span>                                |
  
## <a name="explanation"></a><span data-ttu-id="2044f-114">説明</span><span class="sxs-lookup"><span data-stu-id="2044f-114">Explanation</span></span>  
 <span data-ttu-id="2044f-115">このエラー/警告/情報イベントは、インターチェンジで識別されてインターチェンジのファセットを区切るために使用されている区切り記号のうち、複数が同じ記号であったため、EDI 送信パイプラインで送信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="2044f-115">This Error/Warning/Information event indicates that the EDI send pipeline could not process an outgoing interchange because two or more of the separators identified in the interchange, and used to separate facets of the interchange, were the same.</span></span> <span data-ttu-id="2044f-116">区切り記号は、X12 インターチェンジの ISA セグメントと EDIFACT インターチェンジの UNA セグメントで識別されます。</span><span class="sxs-lookup"><span data-stu-id="2044f-116">The separators are identified in the ISA segment of an X12 interchange and in the UNA segment of an EDIFACT interchange.</span></span> <span data-ttu-id="2044f-117">同じ値を持つ複数の区切り記号は、保存されたバッチ シナリオで発生することがあります。または、インターチェンジがパススルー送信を経由して受信され、その後、送信ポートによって MessageBox で XML ファイルとして取得される場合に、発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="2044f-117">Two or more separators with the same value can occur in a preserved batch scenario, or if an interchange is received via a passthrough transmit and then picked up by the send port as an XML file in the MessageBox.</span></span> <span data-ttu-id="2044f-118">このエラー状態が発生すると、インターチェンジの処理は失敗します。</span><span class="sxs-lookup"><span data-stu-id="2044f-118">This error condition will cause processing of the interchange to fail.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2044f-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="2044f-119">User Action</span></span>  
 <span data-ttu-id="2044f-120">このエラーを解決するには、インターチェンジのどの区切り記号が同じ値を持っているかを特定し、いずれかの区切り記号の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="2044f-120">To resolve this error, identify which separators in the interchange have the same value, and change the value of one of the separators.</span></span>