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
ms.openlocfilehash: d2a3990ce9a1d913cdb9840605c6f0e34623db8b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007545"
---
# <a name="unrecognized-segment-id"></a><span data-ttu-id="6fe9f-102">セグメント ID が認識されません</span><span class="sxs-lookup"><span data-stu-id="6fe9f-102">Unrecognized segment ID</span></span>
## <a name="details"></a><span data-ttu-id="6fe9f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6fe9f-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="6fe9f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6fe9f-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="6fe9f-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6fe9f-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="6fe9f-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6fe9f-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="6fe9f-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6fe9f-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6fe9f-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="6fe9f-108"> EDI</span></span> |
|    <span data-ttu-id="6fe9f-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6fe9f-109">Component</span></span>    |                                       <span data-ttu-id="6fe9f-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="6fe9f-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="6fe9f-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6fe9f-111">Symbolic Name</span></span>  | <span data-ttu-id="6fe9f-112">EfactUnrecognizedSegmentIDDescription</span><span class="sxs-lookup"><span data-stu-id="6fe9f-112">EfactUnrecognizedSegmentIDDescription</span></span><br /><br /> <span data-ttu-id="6fe9f-113">X12UnrecognizedSegmentIDDescription</span><span class="sxs-lookup"><span data-stu-id="6fe9f-113">X12UnrecognizedSegmentIDDescription</span></span>  |
|  <span data-ttu-id="6fe9f-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6fe9f-114">Message Text</span></span>   |                                <span data-ttu-id="6fe9f-115">セグメント ID が認識されません</span><span class="sxs-lookup"><span data-stu-id="6fe9f-115">Unrecognized segment ID</span></span>                                 |
  
## <a name="explanation"></a><span data-ttu-id="6fe9f-116">説明</span><span class="sxs-lookup"><span data-stu-id="6fe9f-116">Explanation</span></span>  
 <span data-ttu-id="6fe9f-117">このエラー/警告/情報イベントは、インターチェンジのトランザクション セットのセグメントが、対応するドキュメント スキーマで定義されていなかったため、受信パイプラインが受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="6fe9f-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because a segment in a transaction set in the interchange was not defined by the corresponding document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6fe9f-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6fe9f-118">User Action</span></span>  
 <span data-ttu-id="6fe9f-119">このエラーを解決するには、インターチェンジの送信者に対して、認識されないセグメントを削除し、インターチェンジを再送信するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="6fe9f-119">To resolve this error, have the sender of the interchange remove the unrecognized segment and resend the interchange.</span></span>