---
title: ユーザー トレーラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- trailers [SWIFT]
- SWIFT, trailers
ms.assetid: 340d9fc8-467b-4cba-b69f-eb761767deaa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10bc0d4d0fcdb36311e0590d9ae04239db168ed7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010219"
---
# <a name="user-trailers"></a><span data-ttu-id="333c4-102">ユーザー トレーラー</span><span class="sxs-lookup"><span data-stu-id="333c4-102">User Trailers</span></span>
<span data-ttu-id="333c4-103">ユーザー トレーラーから CHK トレーラー、を除き、省略可能で、存在する場合は、次の順序で発生します。</span><span class="sxs-lookup"><span data-stu-id="333c4-103">User trailers, except for the CHK trailer, are optional and when present, occur in the following order:</span></span>  
  
|<span data-ttu-id="333c4-104">トレーラー コード</span><span class="sxs-lookup"><span data-stu-id="333c4-104">Trailer code</span></span>|<span data-ttu-id="333c4-105">名前</span><span class="sxs-lookup"><span data-stu-id="333c4-105">Name</span></span>|  
|------------------|----------|  
|<span data-ttu-id="333c4-106">MAC</span><span class="sxs-lookup"><span data-stu-id="333c4-106">MAC</span></span>|<span data-ttu-id="333c4-107">メッセージ認証コード</span><span class="sxs-lookup"><span data-stu-id="333c4-107">Message Authentication Code</span></span>|  
|<span data-ttu-id="333c4-108">PAC</span><span class="sxs-lookup"><span data-stu-id="333c4-108">PAC</span></span>|<span data-ttu-id="333c4-109">独自の認証コード</span><span class="sxs-lookup"><span data-stu-id="333c4-109">Proprietary Authentication Code</span></span>|  
|<span data-ttu-id="333c4-110">CHK</span><span class="sxs-lookup"><span data-stu-id="333c4-110">CHK</span></span>|<span data-ttu-id="333c4-111">Checksum</span><span class="sxs-lookup"><span data-stu-id="333c4-111">Checksum</span></span>|  
|<span data-ttu-id="333c4-112">TNG</span><span class="sxs-lookup"><span data-stu-id="333c4-112">TNG</span></span>|<span data-ttu-id="333c4-113">トレーニング</span><span class="sxs-lookup"><span data-stu-id="333c4-113">Training</span></span>|  
|<span data-ttu-id="333c4-114">PDE</span><span class="sxs-lookup"><span data-stu-id="333c4-114">PDE</span></span>|<span data-ttu-id="333c4-115">可能な重複する出力</span><span class="sxs-lookup"><span data-stu-id="333c4-115">Possible Duplicate Emission</span></span>|  
  
- <span data-ttu-id="333c4-116">**メッセージ認証コード (MAC) トレーラです。**</span><span class="sxs-lookup"><span data-stu-id="333c4-116">**Message Authentication Code (MAC) Trailer.**</span></span> <span data-ttu-id="333c4-117">により、受信側ユーザーを認証できます。</span><span class="sxs-lookup"><span data-stu-id="333c4-117">Allows authentication by the receiving user.</span></span> <span data-ttu-id="333c4-118">MAC のトレーラーには、認証の結果が続きます。</span><span class="sxs-lookup"><span data-stu-id="333c4-118">The MAC trailer is followed by an authentication result.</span></span> <span data-ttu-id="333c4-119">このトレーラーは、ほとんどのユーザーにメッセージ カテゴリ、FIN アプリケーション内で必須です。</span><span class="sxs-lookup"><span data-stu-id="333c4-119">This trailer is mandatory for most user-to-user message categories within the FIN application.</span></span>  
  
   <span data-ttu-id="333c4-120">FIN コピーのサービスを使用する場合 (存在する) 場合は、PAC トレーラーは MAC トレーラーに従います。</span><span class="sxs-lookup"><span data-stu-id="333c4-120">When the FIN Copy Service is used, a PAC trailer (if present) follows the MAC trailer.</span></span> <span data-ttu-id="333c4-121">次のコードでは、MAC トレーラーの例を示します。</span><span class="sxs-lookup"><span data-stu-id="333c4-121">The following code is an example of a MAC trailer:</span></span>  
  
  ```  
  {MAC:<authentication-result>}  
  where <authentication-result> = 8!h  
  ```  
  
- <span data-ttu-id="333c4-122">**独自の認証コード (PAC) のトレーラです。**</span><span class="sxs-lookup"><span data-stu-id="333c4-122">**Proprietary Authentication Code (PAC) Trailer.**</span></span> <span data-ttu-id="333c4-123">PAC トレーラーは、二重認証オプションを使用する場合にのみ、FIN コピー サービス内で使用されます。</span><span class="sxs-lookup"><span data-stu-id="333c4-123">The PAC trailer is used within the FIN Copy service only when using the double authentication option.</span></span> <span data-ttu-id="333c4-124">ブロック 5 の FIN ユーザーのユーザー メッセージには、存在する場合、直後に、MAC トレーラー PAC トレーラーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="333c4-124">Block 5 of FIN user-to-user messages include the PAC trailer immediately after the MAC trailer, if present.</span></span> <span data-ttu-id="333c4-125">この結果が存在する場合に 115、フィールドの値は、メッセージのブロック 4 の抽出、フィールドに計算される、\<認証結果\>二重認証を使用したコピー サービスの MAC トレーラーの。</span><span class="sxs-lookup"><span data-stu-id="333c4-125">This result is calculated on the extracted fields of Block 4 of the message, the value of field 115, if present, and the \<authentication-result\> of the MAC trailer for Copy Services with double authentication.</span></span>  
  
   <span data-ttu-id="333c4-126">その結果、ブロックのインジケーター (CrLf-) が PAC の計算に含まれているし、フィールドは次のように定義されます。</span><span class="sxs-lookup"><span data-stu-id="333c4-126">As a result, the end-of-block indicator (CrLf-) is included in the PAC calculation and the fields are defined as follows:</span></span>  
  
  - <span data-ttu-id="333c4-127">最初の 4 つの文字は、CrLf は。</span><span class="sxs-lookup"><span data-stu-id="333c4-127">The first four characters are CrLf:</span></span>  
  
  - <span data-ttu-id="333c4-128">フィールドと、区切り記号が存在する場合は、32 a は、:、20: これにします。</span><span class="sxs-lookup"><span data-stu-id="333c4-128">The field and the delimiter are present, that is, 32A:, 20:, and so on.</span></span>  
  
  - <span data-ttu-id="333c4-129">すべてのサブフィールドとその区切り記号は存在します。</span><span class="sxs-lookup"><span data-stu-id="333c4-129">All subfields and their delimiters are present.</span></span>  
  
    <span data-ttu-id="333c4-130">次のコードでは、PAC トレーラーの形式の例を示します。</span><span class="sxs-lookup"><span data-stu-id="333c4-130">The following code is an example of the PAC trailer format:</span></span>  
  
  ```  
  {PAC:[<authentication-result>]}  
  where <authentication-result> is mandatory on input messages only and  
  <authentication-result> = 8!h  
  ```  
  
- <span data-ttu-id="333c4-131">**(チェックサム) から CHK トレーラー (必須のすべての FIN メッセージ)**</span><span class="sxs-lookup"><span data-stu-id="333c4-131">**CHK (Checksum) Trailer (mandatory for all FIN messages)**</span></span>  
  
   <span data-ttu-id="333c4-132">CHK トレーラーは FIN メッセージをすべての必須であり、受信者のアドレスに基づいて計算されます (9 番目の文字で 12 文字に置き換え*X*さらに、テキスト ブロック)。</span><span class="sxs-lookup"><span data-stu-id="333c4-132">The CHK trailer is mandatory for all FIN messages and is computed based upon the receiver's address (12 characters with the ninth character replaced by *X* plus the text block).</span></span> <span data-ttu-id="333c4-133">このトレーラーは、システムおよびシステムの動作不良または検出の伝送エラーによりメッセージが破損していないことを確認するために CBT を許可します。</span><span class="sxs-lookup"><span data-stu-id="333c4-133">This trailer allows the system and the CBT to check that messages are not corrupted due to a system malfunction or an undetected transmission error.</span></span>  
  
   <span data-ttu-id="333c4-134">次のコードでは、から CHK トレーラーの形式の例を示します。</span><span class="sxs-lookup"><span data-stu-id="333c4-134">The following code is an example of the CHK trailer format:</span></span>  
  
  ```  
  {CHK:<checksum-result>}  
  where <checksum-result> = 12!h  
  ```  
  
## <a name="see-also"></a><span data-ttu-id="333c4-135">参照</span><span class="sxs-lookup"><span data-stu-id="333c4-135">See Also</span></span>  
 [<span data-ttu-id="333c4-136">スキーマの操作</span><span class="sxs-lookup"><span data-stu-id="333c4-136">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)