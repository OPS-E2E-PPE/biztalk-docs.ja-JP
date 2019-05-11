---
title: AS2 デコーダーで、MDN に返された MIC 値の検証に処理に失敗しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fe2d76d-b0f1-4118-8483-547c2c9fffb7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b65543f3edc47b03f8b1f71344d16c5ff7b9293a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388984"
---
# <a name="the-as2-decoder-failed-processing-when-validating-the-mic-value-returned-in-the-mdn"></a><span data-ttu-id="b5cfc-102">AS2 デコーダーで、MDN に返された MIC 値の検証に処理に失敗しました</span><span class="sxs-lookup"><span data-stu-id="b5cfc-102">The AS2 Decoder failed processing when validating the MIC value returned in the MDN</span></span>
## <a name="details"></a><span data-ttu-id="b5cfc-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b5cfc-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b5cfc-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b5cfc-104">Product Name</span></span>   |                                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
| <span data-ttu-id="b5cfc-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b5cfc-105">Product Version</span></span> |                                                                      [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                       |
|    <span data-ttu-id="b5cfc-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b5cfc-106">Event ID</span></span>     |                                                                                                   -                                                                                                   |
|  <span data-ttu-id="b5cfc-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b5cfc-107">Event Source</span></span>   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="b5cfc-108">EDI</span><span class="sxs-lookup"><span data-stu-id="b5cfc-108">EDI</span></span>                                                         |
|    <span data-ttu-id="b5cfc-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b5cfc-109">Component</span></span>    |                                                                                              <span data-ttu-id="b5cfc-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="b5cfc-110">AS2 Engine</span></span>                                                                                               |
|  <span data-ttu-id="b5cfc-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b5cfc-111">Symbolic Name</span></span>  |                                                                                <span data-ttu-id="b5cfc-112">AS2DecoderMdnMicFailureDuringProcessing</span><span class="sxs-lookup"><span data-stu-id="b5cfc-112">AS2DecoderMdnMicFailureDuringProcessing</span></span>                                                                                |
|  <span data-ttu-id="b5cfc-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b5cfc-113">Message Text</span></span>   | <span data-ttu-id="b5cfc-114">AS2 デコーダーで、MDN に返された MIC 値の検証に処理できませんでした。</span><span class="sxs-lookup"><span data-stu-id="b5cfc-114">The AS2 Decoder failed processing when validating the MIC value returned in the MDN.</span></span>  <span data-ttu-id="b5cfc-115">MDN メッセージの詳細は次のとおりです。AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"OriginalMessageID:"{3}"</span><span class="sxs-lookup"><span data-stu-id="b5cfc-115">Details of the MDN message are as follows:  AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}" OriginalMessageID:"{3}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b5cfc-116">説明</span><span class="sxs-lookup"><span data-stu-id="b5cfc-116">Explanation</span></span>  
 <span data-ttu-id="b5cfc-117">このエラー/警告/情報イベントは、MIC (メッセージ整合性チェック) に検証が失敗したためで受信 MDN が受信パイプラインが処理することを示します。</span><span class="sxs-lookup"><span data-stu-id="b5cfc-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming MDN because the MIC (Message Integrity Check) failed validation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b5cfc-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b5cfc-118">User Action</span></span>  
 <span data-ttu-id="b5cfc-119">このエラーを解決するには、元のメッセージの Signed-receipt-micalg ヘッダー) の「MDN の生成に使用されるアルゴリズムは、AS2 メッセージの受信者の Signed-receipt-micalg プロパティで指定されたアルゴリズムと同じことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b5cfc-119">To resolve this error, verify that the algorithm used for generating the MDN (in the Signed-Receipt-MICalg header of the original message) is the same as the algorithm specified in the Signed-Receipt-MICalg property for the AS2 Message Receiver.</span></span> <span data-ttu-id="b5cfc-120">SHA1 または MD5 のどちらかがどちらもあります。</span><span class="sxs-lookup"><span data-stu-id="b5cfc-120">Both should be either SHA1 or MD5.</span></span> <span data-ttu-id="b5cfc-121">指定されたアルゴリズム、同じである場合は、マルチパートの署名付き MDN メッセージの 2 番目の部分で受信済みのコンテンツ-MIC 拡張フィールドに有効な MIC ダイジェストが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b5cfc-121">If the algorithm specified is the same, verify that Received-Content-MIC extension field in the second part of the multipart signed MDN message includes a valid MIC digest.</span></span> <span data-ttu-id="b5cfc-122">その場合、MDN が送信されたインターチェンジに対応しない理由を確認します。</span><span class="sxs-lookup"><span data-stu-id="b5cfc-122">If it does, determine why the MDN does not correspond to the interchange that was sent.</span></span>