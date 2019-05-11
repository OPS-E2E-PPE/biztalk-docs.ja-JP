---
title: AS2 メッセージに指定されたハッシュ アルゴリズムはサポートされていません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1b292238-f964-4275-bbfa-e21c9150abf7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8ac08333b5506e342fe84a2e7a950610bcdd1b1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258620"
---
# <a name="the-hash-algorithm-specified-in-the-as2-message-is-unsupported"></a><span data-ttu-id="86bc3-102">AS2 メッセージに指定されたハッシュ アルゴリズムはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="86bc3-102">The hash algorithm specified in the AS2 message is unsupported</span></span>
## <a name="details"></a><span data-ttu-id="86bc3-103">詳細</span><span class="sxs-lookup"><span data-stu-id="86bc3-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="86bc3-104">製品名</span><span class="sxs-lookup"><span data-stu-id="86bc3-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="86bc3-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="86bc3-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="86bc3-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="86bc3-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="86bc3-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="86bc3-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="86bc3-108">EDI</span><span class="sxs-lookup"><span data-stu-id="86bc3-108">EDI</span></span> |
|    <span data-ttu-id="86bc3-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="86bc3-109">Component</span></span>    |                                       <span data-ttu-id="86bc3-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="86bc3-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="86bc3-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="86bc3-111">Symbolic Name</span></span>  |                            <span data-ttu-id="86bc3-112">UnsupportedAS2HashAlgorithmError</span><span class="sxs-lookup"><span data-stu-id="86bc3-112">UnsupportedAS2HashAlgorithmError</span></span>                            |
|  <span data-ttu-id="86bc3-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="86bc3-113">Message Text</span></span>   |            <span data-ttu-id="86bc3-114">AS2 メッセージに指定されたハッシュ アルゴリズムがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="86bc3-114">The hash algorithm specified in the AS2 message is unsupported.</span></span>             |
  
## <a name="explanation"></a><span data-ttu-id="86bc3-115">説明</span><span class="sxs-lookup"><span data-stu-id="86bc3-115">Explanation</span></span>  
 <span data-ttu-id="86bc3-116">このエラー/警告/情報イベントは、受信した AS2 メッセージの signed-receipt-micalg ヘッダーに指定された MIC ハッシュ アルゴリズムが有効な値ではないため、受信パイプラインで指定どおりに MDN を生成できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="86bc3-116">This Error/Warning/Information event indicates that the receive pipeline could not generate the MDN as specified because the MIC hash algorithm specified in the signed-receipt-micalg header of the received AS2 message is not a valid value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="86bc3-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="86bc3-117">User Action</span></span>  
 <span data-ttu-id="86bc3-118">このエラーを解決するには、メッセージの送信者にアルゴリズムを MD5 または SHA1 に変更してもらい、メッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="86bc3-118">To resolve this error, have the sender of the message change the algorithm to either MD5 or SHA1, and resend the message.</span></span>