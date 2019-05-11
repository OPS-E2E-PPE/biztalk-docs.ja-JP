---
title: BizTalk Server で SWIFT エラー コード |Microsoft Docs
description: BizTalk Server で、SWIFT アクセラレータ クラスと検証の種類を表示します。
ms.custom: ''
ms.date: 08/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03699986-965b-4a28-ab2e-09f110fb4db6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eeefb9fc918893b8caaab6852d77a417cab340e3
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529788"
---
# <a name="swift-error-codes"></a><span data-ttu-id="04ddd-103">SWIFT エラー コード</span><span class="sxs-lookup"><span data-stu-id="04ddd-103">SWIFT Error Codes</span></span>
<span data-ttu-id="04ddd-104">SWIFT では、財務 (FIN) メッセージのセットに対して多くのネットワークによる検証を定義します。</span><span class="sxs-lookup"><span data-stu-id="04ddd-104">SWIFT defines many network-imposed validations against the set of financial (FIN) messages.</span></span> <span data-ttu-id="04ddd-105">各検証は、メッセージの内容に対してチェックの種類に関連していて、3 文字のエラー コードに関連付けられました。</span><span class="sxs-lookup"><span data-stu-id="04ddd-105">Each validation relates to a type of check against the contents of the message, and is associated with a three-character error code.</span></span> <span data-ttu-id="04ddd-106">エラー コードの最初の文字は、検出された問題のクラスのことを意味する、文字です。</span><span class="sxs-lookup"><span data-stu-id="04ddd-106">The first character of the error code implies the class of the problem detected, and is a letter.</span></span> <span data-ttu-id="04ddd-107">残りの 2 つの文字 (クラスと組み合わせた) ときにエラーの詳細を示すためし、常に 2 桁のコードとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="04ddd-107">The remaining two characters denote the detail of the error (when combined with the class) and always appear as a two-digit code.</span></span>  

## <a name="class-of-errors"></a><span data-ttu-id="04ddd-108">エラーのクラス</span><span class="sxs-lookup"><span data-stu-id="04ddd-108">Class of errors</span></span>  
 <span data-ttu-id="04ddd-109">次の表は、ドライブの文字、検証の種類、エラーの各クラスに関連付けられているルールの変更とエラーのクラスがサポートされているかどうか。</span><span class="sxs-lookup"><span data-stu-id="04ddd-109">The following table lists the letter designations, validation type, rule change associated with each class of error, and whether or not the class of error is supported.</span></span>  
  
|<span data-ttu-id="04ddd-110">クラス</span><span class="sxs-lookup"><span data-stu-id="04ddd-110">Class</span></span>|<span data-ttu-id="04ddd-111">検証の種類とルールの変更</span><span class="sxs-lookup"><span data-stu-id="04ddd-111">Validation type and rule change</span></span>|<span data-ttu-id="04ddd-112">サポートされていますか。</span><span class="sxs-lookup"><span data-stu-id="04ddd-112">Supported?</span></span>|  
|-----------|-------------------------------------|----------------|  
|<span data-ttu-id="04ddd-113">**C、D、E**</span><span class="sxs-lookup"><span data-stu-id="04ddd-113">**C, D, E**</span></span>|<span data-ttu-id="04ddd-114">セマンティック検証規則は、0-299</span><span class="sxs-lookup"><span data-stu-id="04ddd-114">Semantic validation rules 0-299</span></span>|<span data-ttu-id="04ddd-115">Supported</span><span class="sxs-lookup"><span data-stu-id="04ddd-115">Supported</span></span>|  
|<span data-ttu-id="04ddd-116">**Knn**</span><span class="sxs-lookup"><span data-stu-id="04ddd-116">**Knn**</span></span>|<span data-ttu-id="04ddd-117">フィールドに無効なコード word *nn*</span><span class="sxs-lookup"><span data-stu-id="04ddd-117">Invalid code word in field *nn*</span></span>|<span data-ttu-id="04ddd-118">Supported</span><span class="sxs-lookup"><span data-stu-id="04ddd-118">Supported</span></span>|  
|<span data-ttu-id="04ddd-119">**M50**</span><span class="sxs-lookup"><span data-stu-id="04ddd-119">**M50**</span></span>|<span data-ttu-id="04ddd-120">メッセージの長さを超えています</span><span class="sxs-lookup"><span data-stu-id="04ddd-120">Message length exceeded</span></span>|<span data-ttu-id="04ddd-121">サポートされていない</span><span class="sxs-lookup"><span data-stu-id="04ddd-121">Unsupported</span></span>|  
|<span data-ttu-id="04ddd-122">**M60**</span><span class="sxs-lookup"><span data-stu-id="04ddd-122">**M60**</span></span>|<span data-ttu-id="04ddd-123">見つかった非 SWIFT 文字</span><span class="sxs-lookup"><span data-stu-id="04ddd-123">Non-SWIFT character encountered</span></span>|<span data-ttu-id="04ddd-124">Supported</span><span class="sxs-lookup"><span data-stu-id="04ddd-124">Supported</span></span>|  
|<span data-ttu-id="04ddd-125">**T**</span><span class="sxs-lookup"><span data-stu-id="04ddd-125">**T**</span></span>|<span data-ttu-id="04ddd-126">テキスト検証のエラー コード</span><span class="sxs-lookup"><span data-stu-id="04ddd-126">Text validation error codes</span></span>|<span data-ttu-id="04ddd-127">Supported</span><span class="sxs-lookup"><span data-stu-id="04ddd-127">Supported</span></span>|  
|<span data-ttu-id="04ddd-128">**G**</span><span class="sxs-lookup"><span data-stu-id="04ddd-128">**G**</span></span>|<span data-ttu-id="04ddd-129">メッセージのユーザー グループ (マグカップ) Textval 規則の特定のエラー コード</span><span class="sxs-lookup"><span data-stu-id="04ddd-129">Specific error codes for message user group (MUG) Textval rules</span></span>|<span data-ttu-id="04ddd-130">サポートされていない</span><span class="sxs-lookup"><span data-stu-id="04ddd-130">Unsupported</span></span>|  
|<span data-ttu-id="04ddd-131">**B**</span><span class="sxs-lookup"><span data-stu-id="04ddd-131">**B**</span></span>|<span data-ttu-id="04ddd-132">付加価値サービスの特殊なエラー コード</span><span class="sxs-lookup"><span data-stu-id="04ddd-132">Special error codes for value-added services</span></span>|<span data-ttu-id="04ddd-133">サポートされていない</span><span class="sxs-lookup"><span data-stu-id="04ddd-133">Unsupported</span></span>|  
  
 <span data-ttu-id="04ddd-134">SWIFT のすべてのエラーを参照する必要があります、 *SWIFT ユーザー向けハンドブック*します。</span><span class="sxs-lookup"><span data-stu-id="04ddd-134">All SWIFT errors should be referenced in the *SWIFT User Handbook*.</span></span> <span data-ttu-id="04ddd-135">詳細については、および SWIFT エラー コードの完全な一覧についてを参照してください。、*メッセージ形式の検証規則*のボリューム、 *SWIFT ユーザー向けハンドブック*します。</span><span class="sxs-lookup"><span data-stu-id="04ddd-135">For more information and for a complete list of SWIFT error codes, refer to the *Message Format Validation Rules* volume of the *SWIFT User Handbook*.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] <span data-ttu-id="04ddd-136">このパブリケーションの 2003 年 9 月のエディションで、規則を実装します。</span><span class="sxs-lookup"><span data-stu-id="04ddd-136">implements the rules in the September 2003 edition of this publication.</span></span> <span data-ttu-id="04ddd-137">SWIFT Web サイトにアクセスすることができます[ http://go.microsoft.com/fwlink/?LinkId=27885](http://go.microsoft.com/fwlink/?LinkId=27885)します。</span><span class="sxs-lookup"><span data-stu-id="04ddd-137">You can access the SWIFT Web site at [http://go.microsoft.com/fwlink/?LinkId=27885](http://go.microsoft.com/fwlink/?LinkId=27885).</span></span>  

## <a name="validation-errors"></a><span data-ttu-id="04ddd-138">検証エラー</span><span class="sxs-lookup"><span data-stu-id="04ddd-138">Validation errors</span></span>  
 <span data-ttu-id="04ddd-139">A4SWIFT で定義されているいくつかのコードがあります。</span><span class="sxs-lookup"><span data-stu-id="04ddd-139">There are some codes which are defined by A4SWIFT.</span></span> <span data-ttu-id="04ddd-140">これらのエラー コードは、検証/ネットワーク ルールを作成し、このような規則の SWIFT で定義されている、対応するエラー コードがない、A4SWIFT、によって実装されるで使用されます。</span><span class="sxs-lookup"><span data-stu-id="04ddd-140">These error codes are used in the validation/network rules created and implemented by A4SWIFT, so there is no corresponding error code defined by SWIFT for such rules.</span></span> <span data-ttu-id="04ddd-141">次の表は、エラー コードとエラーがスローされた対応するケースを示しています。</span><span class="sxs-lookup"><span data-stu-id="04ddd-141">Below table shows the error code and corresponding case in which the error is thrown.</span></span> <span data-ttu-id="04ddd-142">エラーをスローする特定のフィールドです。</span><span class="sxs-lookup"><span data-stu-id="04ddd-142">is the particular field which throws the error.</span></span>  
  
|<span data-ttu-id="04ddd-143">エラー コード</span><span class="sxs-lookup"><span data-stu-id="04ddd-143">Error Code</span></span>|<span data-ttu-id="04ddd-144">説明</span><span class="sxs-lookup"><span data-stu-id="04ddd-144">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="04ddd-145">A4SWIFT001</span><span class="sxs-lookup"><span data-stu-id="04ddd-145">A4SWIFT001</span></span>|<span data-ttu-id="04ddd-146">複数行のフィールドの最初の文字にすることはできません ':' または '-' 行目以降の文字。</span><span class="sxs-lookup"><span data-stu-id="04ddd-146">The first character of multiline field cannot be ':' or '-' character for second and  subsequent lines.</span></span>|  
|<span data-ttu-id="04ddd-147">A4SWIFT002</span><span class="sxs-lookup"><span data-stu-id="04ddd-147">A4SWIFT002</span></span>|<span data-ttu-id="04ddd-148">フィールドには、無効な値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="04ddd-148">Field contains invalid value.</span></span>|  
  
> [!NOTE]
>  [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] <span data-ttu-id="04ddd-149">内部アプリケーションがメッセージを使用しているために、一部の従来のメッセージのサポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="04ddd-149">includes support for some legacy messages, because internal applications might use these messages.</span></span> <span data-ttu-id="04ddd-150">したがって、A4SWIFT は、関連付けられている SWIFT ルールおよびエラー コードを保持します。</span><span class="sxs-lookup"><span data-stu-id="04ddd-150">Therefore, A4SWIFT maintains the associated SWIFT rules and error codes.</span></span>

## <a name="more-good-info"></a><span data-ttu-id="04ddd-151">詳細な情報</span><span class="sxs-lookup"><span data-stu-id="04ddd-151">More good info</span></span>
[<span data-ttu-id="04ddd-152">トラブルシューティング: 問題と解決方法</span><span class="sxs-lookup"><span data-stu-id="04ddd-152">Troubleshooting: Issues and Resolutions</span></span>](troubleshooting-issues-and-resolutions1.md)  
[<span data-ttu-id="04ddd-153">既知の問題</span><span class="sxs-lookup"><span data-stu-id="04ddd-153">Known Issues</span></span>](known-issues5.md)  
[<span data-ttu-id="04ddd-154">一般的な用語と定義</span><span class="sxs-lookup"><span data-stu-id="04ddd-154">Common terms and definitions</span></span>](glossary6.md)