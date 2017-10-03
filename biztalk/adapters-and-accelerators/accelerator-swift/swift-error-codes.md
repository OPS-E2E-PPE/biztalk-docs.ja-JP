---
title: "BizTalk Server での迅速なエラー コード |Microsoft ドキュメント"
description: "BizTalk Server に SWIFT アクセラレータのクラスと検証の種類を表示します。"
ms.custom: 
ms.date: 08/16/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03699986-965b-4a28-ab2e-09f110fb4db6
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6d8e027eb9cce1cf66342484070310141e10b5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="swift-error-codes"></a><span data-ttu-id="4b6f8-103">SWIFT エラー コード</span><span class="sxs-lookup"><span data-stu-id="4b6f8-103">SWIFT Error Codes</span></span>
<span data-ttu-id="4b6f8-104">SWIFT では、財務 (FIN) メッセージのセットに対して多くのネットワークによる検証を定義します。</span><span class="sxs-lookup"><span data-stu-id="4b6f8-104">SWIFT defines many network-imposed validations against the set of financial (FIN) messages.</span></span> <span data-ttu-id="4b6f8-105">各検証は、メッセージの内容に対してチェックの種類に関連して、3 文字のエラー コードに関連付けられてです。</span><span class="sxs-lookup"><span data-stu-id="4b6f8-105">Each validation relates to a type of check against the contents of the message, and is associated with a three-character error code.</span></span> <span data-ttu-id="4b6f8-106">エラー コードの最初の文字は、クラス、検出された問題のことを意味し、文字です。</span><span class="sxs-lookup"><span data-stu-id="4b6f8-106">The first character of the error code implies the class of the problem detected, and is a letter.</span></span> <span data-ttu-id="4b6f8-107">残りの 2 つの文字は、(クラスと組み合わせて) 場合、エラーの詳細を示すためし、常に 2 桁のコードとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b6f8-107">The remaining two characters denote the detail of the error (when combined with the class) and always appear as a two-digit code.</span></span>  

## <a name="class-of-errors"></a><span data-ttu-id="4b6f8-108">エラーのクラス</span><span class="sxs-lookup"><span data-stu-id="4b6f8-108">Class of errors</span></span>  
 <span data-ttu-id="4b6f8-109">次の表は、ドライブの文字、検証の種類、ルールの変更が、エラーの各クラスに関連付けられているエラーのクラスがサポートされているかどうかとします。</span><span class="sxs-lookup"><span data-stu-id="4b6f8-109">The following table lists the letter designations, validation type, rule change associated with each class of error, and whether or not the class of error is supported.</span></span>  
  
|<span data-ttu-id="4b6f8-110">クラス</span><span class="sxs-lookup"><span data-stu-id="4b6f8-110">Class</span></span>|<span data-ttu-id="4b6f8-111">検証の種類および規則の変更</span><span class="sxs-lookup"><span data-stu-id="4b6f8-111">Validation type and rule change</span></span>|<span data-ttu-id="4b6f8-112">サポートされているか。</span><span class="sxs-lookup"><span data-stu-id="4b6f8-112">Supported?</span></span>|  
|-----------|-------------------------------------|----------------|  
|<span data-ttu-id="4b6f8-113">**C、D、E**</span><span class="sxs-lookup"><span data-stu-id="4b6f8-113">**C, D, E**</span></span>|<span data-ttu-id="4b6f8-114">セマンティック検証規則は、0-299</span><span class="sxs-lookup"><span data-stu-id="4b6f8-114">Semantic validation rules 0-299</span></span>|<span data-ttu-id="4b6f8-115">Supported</span><span class="sxs-lookup"><span data-stu-id="4b6f8-115">Supported</span></span>|  
|<span data-ttu-id="4b6f8-116">**Knn**</span><span class="sxs-lookup"><span data-stu-id="4b6f8-116">**Knn**</span></span>|<span data-ttu-id="4b6f8-117">フィールドに無効なコード ワード*nn*</span><span class="sxs-lookup"><span data-stu-id="4b6f8-117">Invalid code word in field *nn*</span></span>|<span data-ttu-id="4b6f8-118">Supported</span><span class="sxs-lookup"><span data-stu-id="4b6f8-118">Supported</span></span>|  
|<span data-ttu-id="4b6f8-119">**M50**</span><span class="sxs-lookup"><span data-stu-id="4b6f8-119">**M50**</span></span>|<span data-ttu-id="4b6f8-120">メッセージの長さを超えています</span><span class="sxs-lookup"><span data-stu-id="4b6f8-120">Message length exceeded</span></span>|<span data-ttu-id="4b6f8-121">サポートされていない</span><span class="sxs-lookup"><span data-stu-id="4b6f8-121">Unsupported</span></span>|  
|<span data-ttu-id="4b6f8-122">**M60**</span><span class="sxs-lookup"><span data-stu-id="4b6f8-122">**M60**</span></span>|<span data-ttu-id="4b6f8-123">見つかった非 SWIFT 文字</span><span class="sxs-lookup"><span data-stu-id="4b6f8-123">Non-SWIFT character encountered</span></span>|<span data-ttu-id="4b6f8-124">Supported</span><span class="sxs-lookup"><span data-stu-id="4b6f8-124">Supported</span></span>|  
|<span data-ttu-id="4b6f8-125">**T**</span><span class="sxs-lookup"><span data-stu-id="4b6f8-125">**T**</span></span>|<span data-ttu-id="4b6f8-126">テキスト検証のエラー コード</span><span class="sxs-lookup"><span data-stu-id="4b6f8-126">Text validation error codes</span></span>|<span data-ttu-id="4b6f8-127">Supported</span><span class="sxs-lookup"><span data-stu-id="4b6f8-127">Supported</span></span>|  
|<span data-ttu-id="4b6f8-128">**G**</span><span class="sxs-lookup"><span data-stu-id="4b6f8-128">**G**</span></span>|<span data-ttu-id="4b6f8-129">メッセージのユーザー グループ (の入ったマグ) Textval 規則の特定のエラー コード</span><span class="sxs-lookup"><span data-stu-id="4b6f8-129">Specific error codes for message user group (MUG) Textval rules</span></span>|<span data-ttu-id="4b6f8-130">サポートされていない</span><span class="sxs-lookup"><span data-stu-id="4b6f8-130">Unsupported</span></span>|  
|<span data-ttu-id="4b6f8-131">**B**</span><span class="sxs-lookup"><span data-stu-id="4b6f8-131">**B**</span></span>|<span data-ttu-id="4b6f8-132">付加価値サービスの特殊なエラー コード</span><span class="sxs-lookup"><span data-stu-id="4b6f8-132">Special error codes for value-added services</span></span>|<span data-ttu-id="4b6f8-133">サポートされていない</span><span class="sxs-lookup"><span data-stu-id="4b6f8-133">Unsupported</span></span>|  
  
 <span data-ttu-id="4b6f8-134">SWIFT のすべてのエラーを参照してください、 *SWIFT ユーザー マニュアル*です。</span><span class="sxs-lookup"><span data-stu-id="4b6f8-134">All SWIFT errors should be referenced in the *SWIFT User Handbook*.</span></span> <span data-ttu-id="4b6f8-135">詳細については、迅速なエラー コードの完全な一覧についてを参照してください、*メッセージ形式の検証規則*のボリューム、 *SWIFT ユーザー マニュアル*です。</span><span class="sxs-lookup"><span data-stu-id="4b6f8-135">For more information and for a complete list of SWIFT error codes, refer to the *Message Format Validation Rules* volume of the *SWIFT User Handbook*.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="4b6f8-136">このパブリケーションの 2003 年 9 月のエディションで、規則を実装します。</span><span class="sxs-lookup"><span data-stu-id="4b6f8-136"> implements the rules in the September 2003 edition of this publication.</span></span> <span data-ttu-id="4b6f8-137">SWIFT Web サイトにアクセスすることができます[http://go.microsoft.com/fwlink/?LinkId=27885](http://go.microsoft.com/fwlink/?LinkId=27885)です。</span><span class="sxs-lookup"><span data-stu-id="4b6f8-137">You can access the SWIFT Web site at [http://go.microsoft.com/fwlink/?LinkId=27885](http://go.microsoft.com/fwlink/?LinkId=27885).</span></span>  

## <a name="validation-errors"></a><span data-ttu-id="4b6f8-138">検証エラー</span><span class="sxs-lookup"><span data-stu-id="4b6f8-138">Validation errors</span></span>  
 <span data-ttu-id="4b6f8-139">A4SWIFT で定義されている一部のコードがあります。</span><span class="sxs-lookup"><span data-stu-id="4b6f8-139">There are some codes which are defined by A4SWIFT.</span></span> <span data-ttu-id="4b6f8-140">これらのエラー コードが作成され、このようなルールの SWIFT によって定義された対応するエラー コードがないように A4SWIFT、によって実装される検証/ネットワーク ルールで使用されます。</span><span class="sxs-lookup"><span data-stu-id="4b6f8-140">These error codes are used in the validation/network rules created and implemented by A4SWIFT, so there is no corresponding error code defined by SWIFT for such rules.</span></span> <span data-ttu-id="4b6f8-141">次の表は、エラー コードと、エラーがスローされた、対応するケースを示しています。</span><span class="sxs-lookup"><span data-stu-id="4b6f8-141">Below table shows the error code and corresponding case in which the error is thrown.</span></span> <span data-ttu-id="4b6f8-142">エラーをスローする特定のフィールドです。</span><span class="sxs-lookup"><span data-stu-id="4b6f8-142">is the particular field which throws the error.</span></span>  
  
|<span data-ttu-id="4b6f8-143">エラー コード</span><span class="sxs-lookup"><span data-stu-id="4b6f8-143">Error Code</span></span>|<span data-ttu-id="4b6f8-144">Description</span><span class="sxs-lookup"><span data-stu-id="4b6f8-144">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="4b6f8-145">A4SWIFT001</span><span class="sxs-lookup"><span data-stu-id="4b6f8-145">A4SWIFT001</span></span>|<span data-ttu-id="4b6f8-146">複数行のフィールドの最初の文字にすることはできません ':' または '-' 行目以降の文字です。</span><span class="sxs-lookup"><span data-stu-id="4b6f8-146">The first character of multiline field cannot be ':' or '-' character for second and  subsequent lines.</span></span>|  
|<span data-ttu-id="4b6f8-147">A4SWIFT002</span><span class="sxs-lookup"><span data-stu-id="4b6f8-147">A4SWIFT002</span></span>|<span data-ttu-id="4b6f8-148">フィールドには、無効な値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b6f8-148">Field contains invalid value.</span></span>|  
  
> [!NOTE]
>  [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]<span data-ttu-id="4b6f8-149">内部アプリケーションがこれらのメッセージを使用するため、一部のレガシ メッセージのサポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4b6f8-149"> includes support for some legacy messages, because internal applications might use these messages.</span></span> <span data-ttu-id="4b6f8-150">したがって、A4SWIFT は、関連付けられている SWIFT ルールおよびエラー コードを保持します。</span><span class="sxs-lookup"><span data-stu-id="4b6f8-150">Therefore, A4SWIFT maintains the associated SWIFT rules and error codes.</span></span>

## <a name="more-good-info"></a><span data-ttu-id="4b6f8-151">詳細な情報</span><span class="sxs-lookup"><span data-stu-id="4b6f8-151">More good info</span></span>
[<span data-ttu-id="4b6f8-152">トラブルシューティング: 問題と解決策</span><span class="sxs-lookup"><span data-stu-id="4b6f8-152">Troubleshooting: Issues and Resolutions</span></span>](troubleshooting-issues-and-resolutions1.md)  
[<span data-ttu-id="4b6f8-153">既知の問題</span><span class="sxs-lookup"><span data-stu-id="4b6f8-153">Known Issues</span></span>](known-issues5.md)  
[<span data-ttu-id="4b6f8-154">一般的な用語と定義</span><span class="sxs-lookup"><span data-stu-id="4b6f8-154">Common terms and definitions</span></span>](glossary6.md)