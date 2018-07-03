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
ms.openlocfilehash: 2b15ec1518e4736052e31254283db66395d87fb6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985843"
---
# <a name="the-as2-decoder-failed-processing-when-validating-the-mic-value-returned-in-the-mdn"></a><span data-ttu-id="1e1e3-102">AS2 デコーダーで、MDN に返された MIC 値の検証中に処理が失敗しました</span><span class="sxs-lookup"><span data-stu-id="1e1e3-102">The AS2 Decoder failed processing when validating the MIC value returned in the MDN</span></span>
## <a name="details"></a><span data-ttu-id="1e1e3-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1e1e3-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1e1e3-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1e1e3-104">Product Name</span></span>   |                                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
| <span data-ttu-id="1e1e3-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1e1e3-105">Product Version</span></span> |                                                                      [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                       |
|    <span data-ttu-id="1e1e3-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1e1e3-106">Event ID</span></span>     |                                                                                                   -                                                                                                   |
|  <span data-ttu-id="1e1e3-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1e1e3-107">Event Source</span></span>   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1e1e3-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="1e1e3-108"> EDI</span></span>                                                         |
|    <span data-ttu-id="1e1e3-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1e1e3-109">Component</span></span>    |                                                                                              <span data-ttu-id="1e1e3-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="1e1e3-110">AS2 Engine</span></span>                                                                                               |
|  <span data-ttu-id="1e1e3-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1e1e3-111">Symbolic Name</span></span>  |                                                                                <span data-ttu-id="1e1e3-112">AS2DecoderMdnMicFailureDuringProcessing</span><span class="sxs-lookup"><span data-stu-id="1e1e3-112">AS2DecoderMdnMicFailureDuringProcessing</span></span>                                                                                |
|  <span data-ttu-id="1e1e3-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1e1e3-113">Message Text</span></span>   | <span data-ttu-id="1e1e3-114">AS2 デコーダで、MDN に返された MIC 値の検証中に処理が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="1e1e3-114">The AS2 Decoder failed processing when validating the MIC value returned in the MDN.</span></span>  <span data-ttu-id="1e1e3-115">MDN メッセージの詳細は次のとおり: AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"OriginalMessageID:"{3}"</span><span class="sxs-lookup"><span data-stu-id="1e1e3-115">Details of the MDN message are as follows:  AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}" OriginalMessageID:"{3}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="1e1e3-116">説明</span><span class="sxs-lookup"><span data-stu-id="1e1e3-116">Explanation</span></span>  
 <span data-ttu-id="1e1e3-117">このエラー/警告/情報イベントは、MIC (メッセージ整合性チェック) の検証が失敗したため、受信パイプラインで受信 MDN を処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="1e1e3-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming MDN because the MIC (Message Integrity Check) failed validation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1e1e3-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1e1e3-118">User Action</span></span>  
 <span data-ttu-id="1e1e3-119">このエラーを解決するには、MDN の生成に使用されるアルゴリズム (元のメッセージの Signed-Receipt-MICalg ヘッダー) が、AS2 メッセージの受信者の Signed-Receipt-MICalg プロパティで指定されているアルゴリズムと同じであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1e1e3-119">To resolve this error, verify that the algorithm used for generating the MDN (in the Signed-Receipt-MICalg header of the original message) is the same as the algorithm specified in the Signed-Receipt-MICalg property for the AS2 Message Receiver.</span></span> <span data-ttu-id="1e1e3-120">両方が SHA1 または MD5 のどちらかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e1e3-120">Both should be either SHA1 or MD5.</span></span> <span data-ttu-id="1e1e3-121">指定されているアルゴリズムが同じである場合は、マルチパートの署名付き MDN メッセージの 2 番目の部分にある Received-Content-MIC 拡張フィールドに、有効な MIC ダイジェストが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1e1e3-121">If the algorithm specified is the same, verify that Received-Content-MIC extension field in the second part of the multipart signed MDN message includes a valid MIC digest.</span></span> <span data-ttu-id="1e1e3-122">有効な MIC ダイジェストが含まれている場合は、送信されたインターチェンジに MDN が対応していない理由を特定します。</span><span class="sxs-lookup"><span data-stu-id="1e1e3-122">If it does, determine why the MDN does not correspond to the interchange that was sent.</span></span>