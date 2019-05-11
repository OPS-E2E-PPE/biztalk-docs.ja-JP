---
title: セグメント ID が認識されない |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a00fe451-0a84-4dca-980c-682243fc9804
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09c093eb9b6793dfd4b211bff67bb51f467f2a57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396040"
---
# <a name="unrecognized-segment-id"></a><span data-ttu-id="412f9-102">セグメント ID が認識されません</span><span class="sxs-lookup"><span data-stu-id="412f9-102">Unrecognized segment ID</span></span>
## <a name="details"></a><span data-ttu-id="412f9-103">詳細</span><span class="sxs-lookup"><span data-stu-id="412f9-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="412f9-104">製品名</span><span class="sxs-lookup"><span data-stu-id="412f9-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="412f9-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="412f9-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="412f9-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="412f9-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="412f9-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="412f9-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="412f9-108">EDI</span><span class="sxs-lookup"><span data-stu-id="412f9-108">EDI</span></span> |
|    <span data-ttu-id="412f9-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="412f9-109">Component</span></span>    |                                       <span data-ttu-id="412f9-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="412f9-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="412f9-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="412f9-111">Symbolic Name</span></span>  | <span data-ttu-id="412f9-112">EfactUnrecognizedSegmentIDDescription</span><span class="sxs-lookup"><span data-stu-id="412f9-112">EfactUnrecognizedSegmentIDDescription</span></span><br /><br /> <span data-ttu-id="412f9-113">X12UnrecognizedSegmentIDDescription</span><span class="sxs-lookup"><span data-stu-id="412f9-113">X12UnrecognizedSegmentIDDescription</span></span>  |
|  <span data-ttu-id="412f9-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="412f9-114">Message Text</span></span>   |                                <span data-ttu-id="412f9-115">セグメント ID が認識されません</span><span class="sxs-lookup"><span data-stu-id="412f9-115">Unrecognized segment ID</span></span>                                 |
  
## <a name="explanation"></a><span data-ttu-id="412f9-116">説明</span><span class="sxs-lookup"><span data-stu-id="412f9-116">Explanation</span></span>  
 <span data-ttu-id="412f9-117">このエラー/警告/情報イベントは、インターチェンジのトランザクション セットのセグメントが、対応するドキュメント スキーマで定義されていなかったため、受信パイプラインが受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="412f9-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because a segment in a transaction set in the interchange was not defined by the corresponding document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="412f9-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="412f9-118">User Action</span></span>  
 <span data-ttu-id="412f9-119">このエラーを解決するには、インターチェンジの送信者に対して、認識されないセグメントを削除し、インターチェンジを再送信するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="412f9-119">To resolve this error, have the sender of the interchange remove the unrecognized segment and resend the interchange.</span></span>