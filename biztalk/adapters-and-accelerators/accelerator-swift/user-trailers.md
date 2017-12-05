---
title: "ユーザーのトレーラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- trailers [SWIFT]
- SWIFT, trailers
ms.assetid: 340d9fc8-467b-4cba-b69f-eb761767deaa
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff907e262088acd188028282fe2e03441071358a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="user-trailers"></a><span data-ttu-id="a549f-102">ユーザーのトレーラー</span><span class="sxs-lookup"><span data-stu-id="a549f-102">User Trailers</span></span>
<span data-ttu-id="a549f-103">ユーザーのトレーラー、CHK トレーラーを除くはオプションであり、存在する場合は、次の順序で発生します。</span><span class="sxs-lookup"><span data-stu-id="a549f-103">User trailers, except for the CHK trailer, are optional and when present, occur in the following order:</span></span>  
  
|<span data-ttu-id="a549f-104">トレーラー コード</span><span class="sxs-lookup"><span data-stu-id="a549f-104">Trailer code</span></span>|<span data-ttu-id="a549f-105">名前</span><span class="sxs-lookup"><span data-stu-id="a549f-105">Name</span></span>|  
|------------------|----------|  
|<span data-ttu-id="a549f-106">MAC</span><span class="sxs-lookup"><span data-stu-id="a549f-106">MAC</span></span>|<span data-ttu-id="a549f-107">メッセージ認証コード</span><span class="sxs-lookup"><span data-stu-id="a549f-107">Message Authentication Code</span></span>|  
|<span data-ttu-id="a549f-108">PAC</span><span class="sxs-lookup"><span data-stu-id="a549f-108">PAC</span></span>|<span data-ttu-id="a549f-109">独自の認証コード</span><span class="sxs-lookup"><span data-stu-id="a549f-109">Proprietary Authentication Code</span></span>|  
|<span data-ttu-id="a549f-110">CHK</span><span class="sxs-lookup"><span data-stu-id="a549f-110">CHK</span></span>|<span data-ttu-id="a549f-111">Checksum</span><span class="sxs-lookup"><span data-stu-id="a549f-111">Checksum</span></span>|  
|<span data-ttu-id="a549f-112">TNG</span><span class="sxs-lookup"><span data-stu-id="a549f-112">TNG</span></span>|<span data-ttu-id="a549f-113">トレーニング</span><span class="sxs-lookup"><span data-stu-id="a549f-113">Training</span></span>|  
|<span data-ttu-id="a549f-114">PDE</span><span class="sxs-lookup"><span data-stu-id="a549f-114">PDE</span></span>|<span data-ttu-id="a549f-115">考えられる重複する出力</span><span class="sxs-lookup"><span data-stu-id="a549f-115">Possible Duplicate Emission</span></span>|  
  
-   <span data-ttu-id="a549f-116">**メッセージ認証コード (MAC) のトレーラです。**</span><span class="sxs-lookup"><span data-stu-id="a549f-116">**Message Authentication Code (MAC) Trailer.**</span></span> <span data-ttu-id="a549f-117">により、受信側ユーザーを認証できます。</span><span class="sxs-lookup"><span data-stu-id="a549f-117">Allows authentication by the receiving user.</span></span> <span data-ttu-id="a549f-118">MAC トレーラーには、認証の結果が続きます。</span><span class="sxs-lookup"><span data-stu-id="a549f-118">The MAC trailer is followed by an authentication result.</span></span> <span data-ttu-id="a549f-119">このトレーラーは、ほとんどのユーザーにメッセージ カテゴリ、FIN アプリケーション内で必須です。</span><span class="sxs-lookup"><span data-stu-id="a549f-119">This trailer is mandatory for most user-to-user message categories within the FIN application.</span></span>  
  
     <span data-ttu-id="a549f-120">FIN コピー サービスを使用すると、PAC トレーラー (存在する場合) には、MAC トレーラーが次に示します。</span><span class="sxs-lookup"><span data-stu-id="a549f-120">When the FIN Copy Service is used, a PAC trailer (if present) follows the MAC trailer.</span></span> <span data-ttu-id="a549f-121">次のコードは、MAC トレーラーの例です。</span><span class="sxs-lookup"><span data-stu-id="a549f-121">The following code is an example of a MAC trailer:</span></span>  
  
    ```  
    {MAC:<authentication-result>}  
    where <authentication-result> = 8!h  
    ```  
  
-   <span data-ttu-id="a549f-122">**独自の認証コード (PAC を) トレーラです。**</span><span class="sxs-lookup"><span data-stu-id="a549f-122">**Proprietary Authentication Code (PAC) Trailer.**</span></span> <span data-ttu-id="a549f-123">二重認証オプションを使用する場合にのみ、PAC トレーラーは FIN コピー サービス内で使用されます。</span><span class="sxs-lookup"><span data-stu-id="a549f-123">The PAC trailer is used within the FIN Copy service only when using the double authentication option.</span></span> <span data-ttu-id="a549f-124">ブロック 5 の FIN ユーザー-ユーザーへのメッセージには、存在する場合、MAC トレーラーの直後に、PAC トレーラーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a549f-124">Block 5 of FIN user-to-user messages include the PAC trailer immediately after the MAC trailer, if present.</span></span> <span data-ttu-id="a549f-125">この結果が計算される 115、フィールドの値、メッセージのブロック 4 のフィールドの抽出に存在する場合、および\<認証結果\>コピー サービスの認証では二重の MAC トレーラーのです。</span><span class="sxs-lookup"><span data-stu-id="a549f-125">This result is calculated on the extracted fields of Block 4 of the message, the value of field 115, if present, and the \<authentication-result\> of the MAC trailer for Copy Services with double authentication.</span></span>  
  
     <span data-ttu-id="a549f-126">その結果、PAC の計算でブロックのインジケーター (CrLf-) が含まれているし、フィールドは次のように定義されます。</span><span class="sxs-lookup"><span data-stu-id="a549f-126">As a result, the end-of-block indicator (CrLf-) is included in the PAC calculation and the fields are defined as follows:</span></span>  
  
    -   <span data-ttu-id="a549f-127">最初の 4 つの文字は、CrLf:</span><span class="sxs-lookup"><span data-stu-id="a549f-127">The first four characters are CrLf:</span></span>  
  
    -   <span data-ttu-id="a549f-128">フィールドと、区切り記号がある、32 a は、:、20: のようにします。</span><span class="sxs-lookup"><span data-stu-id="a549f-128">The field and the delimiter are present, that is, 32A:, 20:, and so on.</span></span>  
  
    -   <span data-ttu-id="a549f-129">すべてのサブフィールドとその区切り記号は存在します。</span><span class="sxs-lookup"><span data-stu-id="a549f-129">All subfields and their delimiters are present.</span></span>  
  
     <span data-ttu-id="a549f-130">次のコードでは、PAC トレーラー形式の例を示します。</span><span class="sxs-lookup"><span data-stu-id="a549f-130">The following code is an example of the PAC trailer format:</span></span>  
  
    ```  
    {PAC:[<authentication-result>]}  
    where <authentication-result> is mandatory on input messages only and  
    <authentication-result> = 8!h  
    ```  
  
-   <span data-ttu-id="a549f-131">**CHK (チェックサム) トレーラー (必須のすべての FIN メッセージ)**</span><span class="sxs-lookup"><span data-stu-id="a549f-131">**CHK (Checksum) Trailer (mandatory for all FIN messages)**</span></span>  
  
     <span data-ttu-id="a549f-132">CHK トレーラーは FIN メッセージをすべての必須であり、受信者のアドレスに基づいて計算されます (9 番目の文字で 12 文字で置換*X*さらに、テキスト ブロック) します。</span><span class="sxs-lookup"><span data-stu-id="a549f-132">The CHK trailer is mandatory for all FIN messages and is computed based upon the receiver's address (12 characters with the ninth character replaced by *X* plus the text block).</span></span> <span data-ttu-id="a549f-133">このトレーラーは、システムおよびシステムが誤動作または検出されていない転送エラーのためのメッセージが破損していないことを確認する CBT を許可します。</span><span class="sxs-lookup"><span data-stu-id="a549f-133">This trailer allows the system and the CBT to check that messages are not corrupted due to a system malfunction or an undetected transmission error.</span></span>  
  
     <span data-ttu-id="a549f-134">次のコードでは、CHK トレーラー形式の例を示します。</span><span class="sxs-lookup"><span data-stu-id="a549f-134">The following code is an example of the CHK trailer format:</span></span>  
  
    ```  
    {CHK:<checksum-result>}  
    where <checksum-result> = 12!h  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a549f-135">参照</span><span class="sxs-lookup"><span data-stu-id="a549f-135">See Also</span></span>  
 [<span data-ttu-id="a549f-136">スキーマの操作</span><span class="sxs-lookup"><span data-stu-id="a549f-136">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)