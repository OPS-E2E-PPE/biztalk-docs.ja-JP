---
title: "存在しないか無効なトランザクション セット制御番号 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6064b974-e8cd-4486-abc2-010afe0d956e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e9448c9be2cd05c7f7d8c18c13730933c1b5824
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="missing-or-invalid-transaction-set-control-number"></a><span data-ttu-id="8d04e-102">トランザクション セット制御番号が見つからないか無効です</span><span class="sxs-lookup"><span data-stu-id="8d04e-102">Missing or invalid transaction set control number</span></span>
## <a name="details"></a><span data-ttu-id="8d04e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="8d04e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8d04e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="8d04e-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="8d04e-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8d04e-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="8d04e-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8d04e-106">Event ID</span></span>|-|  
|<span data-ttu-id="8d04e-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8d04e-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="8d04e-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="8d04e-108"> EDI</span></span>|  
|<span data-ttu-id="8d04e-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8d04e-109">Component</span></span>|<span data-ttu-id="8d04e-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="8d04e-110">EDI Engine</span></span>|  
|<span data-ttu-id="8d04e-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8d04e-111">Symbolic Name</span></span>|<span data-ttu-id="8d04e-112">X12TsMissingOrInvalidTsControlNumberDescription</span><span class="sxs-lookup"><span data-stu-id="8d04e-112">X12TsMissingOrInvalidTsControlNumberDescription</span></span>|  
|<span data-ttu-id="8d04e-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8d04e-113">Message Text</span></span>|<span data-ttu-id="8d04e-114">トランザクション セット制御番号が見つからないか無効です</span><span class="sxs-lookup"><span data-stu-id="8d04e-114">Missing or invalid transaction set control number</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8d04e-115">説明</span><span class="sxs-lookup"><span data-stu-id="8d04e-115">Explanation</span></span>  
 <span data-ttu-id="8d04e-116">このエラー/警告/情報イベントは、トランザクション セット制御番号 (ST02 フィールド) が見つからないか無効な値であったため、受信または送信パイプラインでインターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="8d04e-116">This Error/Warning/Information event indicates that the receive or send pipeline could not process the interchange because the value of the transaction set control number (in the ST02 field) was missing or had an invalid value.</span></span> <span data-ttu-id="8d04e-117">トランザクション セット制御番号は英数字である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d04e-117">The transaction set control number must be an alphanumeric value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8d04e-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8d04e-118">User Action</span></span>  
 <span data-ttu-id="8d04e-119">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8d04e-119">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="8d04e-120">各トランザクション セットにトランザクション セット制御番号があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d04e-120">Make sure that each transaction set has a transaction set control number.</span></span>  
  
2.  <span data-ttu-id="8d04e-121">各トランザクション セット制御番号が英数字であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d04e-121">Make sure that each transaction set control number is an alphanumeric value.</span></span>