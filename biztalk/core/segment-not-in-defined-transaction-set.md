---
title: ないで定義されているトランザクション セットのセグメント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 914e333f-96e4-4094-880d-51a5f25915c3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3db84f1ae6fda183799b0344d95da7b395aaee8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991699"
---
# <a name="segment-not-in-defined-transaction-set"></a><span data-ttu-id="05b60-102">定義されたトランザクション セットにセグメントがありません</span><span class="sxs-lookup"><span data-stu-id="05b60-102">Segment Not In Defined Transaction set</span></span>
## <a name="details"></a><span data-ttu-id="05b60-103">詳細</span><span class="sxs-lookup"><span data-stu-id="05b60-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="05b60-104">製品名</span><span class="sxs-lookup"><span data-stu-id="05b60-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="05b60-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="05b60-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="05b60-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="05b60-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="05b60-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="05b60-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="05b60-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="05b60-108"> EDI</span></span> |
|    <span data-ttu-id="05b60-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="05b60-109">Component</span></span>    |                                       <span data-ttu-id="05b60-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="05b60-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="05b60-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="05b60-111">Symbolic Name</span></span>  |                          <span data-ttu-id="05b60-112">X12SegmentNotInDefinedTSDescription</span><span class="sxs-lookup"><span data-stu-id="05b60-112">X12SegmentNotInDefinedTSDescription</span></span>                           |
|  <span data-ttu-id="05b60-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="05b60-113">Message Text</span></span>   |                         <span data-ttu-id="05b60-114">定義されたトランザクション セットにセグメントがありません</span><span class="sxs-lookup"><span data-stu-id="05b60-114">Segment Not In Defined Transaction set</span></span>                         |
  
## <a name="explanation"></a><span data-ttu-id="05b60-115">説明</span><span class="sxs-lookup"><span data-stu-id="05b60-115">Explanation</span></span>  
 <span data-ttu-id="05b60-116">このエラー/警告/情報イベントは、インターチェンジのトランザクション セットに、ドキュメント スキーマで必要なセグメントが含まれていないため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="05b60-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because a transaction set in that interchange does not contain a segment required by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="05b60-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="05b60-117">User Action</span></span>  
 <span data-ttu-id="05b60-118">このエラーを解決するには、インターチェンジの送信者が必要なセグメントをインターチェンジのトランザクション セットに追加した上で、インターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="05b60-118">To resolve this error, have the sender of the interchange add the required segment to the transaction set in the interchange, and then resend the interchange.</span></span>