---
title: EDI の種類 (データ要素) の検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd53685f-a49c-41c8-813e-29700fc0b62b
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e64063dbd9e8a7337759f90114b70a2e8f7b9d21
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973659"
---
# <a name="edi-type-data-element-validation"></a><span data-ttu-id="4aaef-102">EDI の種類 (データ要素) の検証</span><span class="sxs-lookup"><span data-stu-id="4aaef-102">EDI Type (Data Element) Validation</span></span>
<span data-ttu-id="4aaef-103">EDI 受信パイプラインと EDI 送信パイプラインは、トランザクション セット データ要素に対して EDI 検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="4aaef-103">The EDI receive pipeline and EDI send pipeline perform EDI validation on transaction-set data elements.</span></span> <span data-ttu-id="4aaef-104">この検証が上のすべてのメッセージから、またはそのパーティとのアグリーメントのプロパティを通じて、特定のパーティに用に構成された、**検証**ページ (下、**トランザクション セットの設定**x12 のいずれかのセクションまたは EDIFACT アグリーメント) で変更します。</span><span class="sxs-lookup"><span data-stu-id="4aaef-104">This validation is configured for all messages from or to a specific party, through that party's agreement properties on the **Validation** page (under the **Transaction Set Settings** section for either X12 or EDIFACT agreements).</span></span> <span data-ttu-id="4aaef-105">場合、 **EDI 型の検証**でプロパティが選択されていない、**検証**] ページの [データのこのトピックで説明されている検証は実行されません。</span><span class="sxs-lookup"><span data-stu-id="4aaef-105">If the **EDI Type Validation** property is not selected in the **Validation** page, the data validations described in this topic will not be performed.</span></span>  
  
 <span data-ttu-id="4aaef-106">選択する受信と送信メッセージの EDI の種類の検証が有効になっている、 **EDI の種類の検証**プロパティ、**検証**双方向アグリーメントタブのページ**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="4aaef-106">EDI type validation is enabled for incoming as well as outgoing messages by selecting the **EDI type Validation** property in the **Validation** page of the bi-directional agreement tabs in the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="4aaef-107">受信メッセージと送信メッセージの両方で、このプロパティは既定で選択されているため、EDI の検証は既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="4aaef-107">For both incoming and outgoing messages, this property is selected by default so that EDI validation is enabled by default.</span></span>  
  
## <a name="validation-checks"></a><span data-ttu-id="4aaef-108">検証の確認</span><span class="sxs-lookup"><span data-stu-id="4aaef-108">Validation Checks</span></span>  
 <span data-ttu-id="4aaef-109">EDI 受信パイプラインまたは EDI 送信パイプラインが EDI の検証を実行するとき、以下の点が検証されます。</span><span class="sxs-lookup"><span data-stu-id="4aaef-109">When the EDI receive pipeline or EDI send pipeline performs EDI validation, it validates the following:</span></span>  
  
- <span data-ttu-id="4aaef-110">スキーマの EDI プロパティで定義されたデータ型</span><span class="sxs-lookup"><span data-stu-id="4aaef-110">Data types as defined by the EDI properties of the schema</span></span>  
  
- <span data-ttu-id="4aaef-111">長さ制限</span><span class="sxs-lookup"><span data-stu-id="4aaef-111">Length restrictions</span></span>  
  
- <span data-ttu-id="4aaef-112">空のデータ要素と後続の区切り文字</span><span class="sxs-lookup"><span data-stu-id="4aaef-112">Empty data elements and trailing separators</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="4aaef-113">この検証では、コード セット (列挙) や、最小または最大の出現は検証されません。</span><span class="sxs-lookup"><span data-stu-id="4aaef-113">This validation does not check code sets (enumerations) or min or max occurs.</span></span>  
  
  <span data-ttu-id="4aaef-114">**文字セット**</span><span class="sxs-lookup"><span data-stu-id="4aaef-114">**Character Sets**</span></span>  
  
  <span data-ttu-id="4aaef-115">EDI データ要素の検証を行うために、EDI 受信パイプラインと送信パイプラインには、次のように文字セットを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4aaef-115">To perform EDI data element validations, the EDI receive and send pipelines require the character set to be established as follows:</span></span>  
  
- <span data-ttu-id="4aaef-116">データ要素で、edifact 文字セットが確立されている**UNB1**の**文字セットと区切り記号**の一方向アグリーメント タブのページ、**アグリーメントのプロパティ**ダイアログ ボックスまたは**EDIFACT フォールバックの設定** ダイアログ ボックス (アグリーメントが設定されていない) 場合。</span><span class="sxs-lookup"><span data-stu-id="4aaef-116">For EDIFACT, the character set is established in data element **UNB1** of the **Charset and Separators** page of the one-way agreement tab of the **Agreement Properties** dialog box or the **EDIFACT Fallback Settings** dialog box (if no agreement has been established).</span></span>  
  
- <span data-ttu-id="4aaef-117">データ要素で、kedifact 文字が確立されている**UNB1**の**文字セットと区切り記号**の一方向アグリーメント タブのページ、**アグリーメントのプロパティ**ダイアログボックスでは、EDIFACT の場合とします。</span><span class="sxs-lookup"><span data-stu-id="4aaef-117">For KEDIFACT, the character is established in data element **UNB1** of the **Charset and Separators** page of the one-way agreement tab of the **Agreement Properties** dialog box, as for EDIFACT.</span></span> <span data-ttu-id="4aaef-118">値、 **UNB1.1**に要素を設定する必要があります`KECA`します。</span><span class="sxs-lookup"><span data-stu-id="4aaef-118">The value for the **UNB1.1** element must be set to `KECA`.</span></span>  
  
- <span data-ttu-id="4aaef-119">X12 では、メッセージの文字セットは、パイプライン プロパティで設定されます。</span><span class="sxs-lookup"><span data-stu-id="4aaef-119">For X12, the character set is established for the message in the pipeline properties.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="4aaef-120">BizTalk ランタイムがメッセージの EDI 検証を実行する際には、パイプライン プロパティで選択された X12 文字セットが使用されます。</span><span class="sxs-lookup"><span data-stu-id="4aaef-120">When the BizTalk runtime performs EDI validation of a message, it will use the X12 character set selected in the pipeline properties.</span></span> <span data-ttu-id="4aaef-121">ただし、プロパティの検証がのページで入力、**アグリーメントのプロパティ**設定で選択した文字を使用して、ダイアログ ボックスが実行される、**文字セットと区切り記号**そのダイアログ ボックスのページ。</span><span class="sxs-lookup"><span data-stu-id="4aaef-121">However, validation of the properties entered in the pages of the **Agreement Properties** dialog box is performed using the character set selected in the **Charset and Separators** page of that dialog box.</span></span> <span data-ttu-id="4aaef-122">実行時に、パイプラインは、値を無視の X12 文字セット プロパティ**文字セットと区切り記号**のページ、**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="4aaef-122">During runtime, the pipeline ignores the value of the X12 character set property **Charset and Separators** page of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="4aaef-123">これら 2 つの設定は、同じ場合 (X12 文字セット プロパティなど、**アグリーメントのプロパティ** ダイアログ ボックスに設定されて**拡張**パイプライン プロパティで文字プロパティに設定の X12 の while**基本的な**)、メッセージ検証エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4aaef-123">If these two settings are not the same (i.e., the X12 character set property in the **Agreement Properties** dialog box is set to **Extended** while the X12 character property in the pipeline properties is set to **Basic**), message validation errors could result.</span></span>  
  
  <span data-ttu-id="4aaef-124">**データ型の検証**</span><span class="sxs-lookup"><span data-stu-id="4aaef-124">**Data Type Validation**</span></span>  
  
  <span data-ttu-id="4aaef-125">X12 では、受信パイプラインまたは送信パイプラインにおける逆アセンブラーまたはアセンブラー コンポーネントによる検証用に、Numeric、Decimal、Identifier、String、Date、Time、Binary、Composite の各 EDI データ型にスキーマ内で注釈が付いています。</span><span class="sxs-lookup"><span data-stu-id="4aaef-125">For X12, the following EDI data types are annotated in schema for validation by the Disassembler/Assembler components in the Receive or Send Pipelines: Numeric, Decimal, Identifier, String, Date, Time, Binary, and Composite.</span></span>  
  
  <span data-ttu-id="4aaef-126">EDIFACT では、受信パイプラインまたは送信パイプラインにおける逆アセンブラーまたはアセンブラー コンポーネントによる検証用に、Alphabetic、Numeric、Identifier、String、Composite の各 EDI データ型にスキーマ内で注釈が付いています。</span><span class="sxs-lookup"><span data-stu-id="4aaef-126">For EDIFACT, the following EDI data types are annotated in schema for validation by the Disassembler/Assembler components in the Receive or Send Pipelines: Alphabetic, Numeric, Identifier, String, and Composite.</span></span>  
  
  <span data-ttu-id="4aaef-127">**長さの制限**</span><span class="sxs-lookup"><span data-stu-id="4aaef-127">**Length Restrictions**</span></span>  
  
  <span data-ttu-id="4aaef-128">X12 と EDIFACT の両方で、要素またはサブ要素の長さ (最小と最大) 要件を検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4aaef-128">For both X12 and EDIFACT, elements or sub-elements must be validated for length (minimum and maximum) requirement.</span></span> <span data-ttu-id="4aaef-129">長さは、使用されている文字位置の数として定義されます。</span><span class="sxs-lookup"><span data-stu-id="4aaef-129">Length is defined as the number of character positions used.</span></span> <span data-ttu-id="4aaef-130">長さには、符号および小数点表記は含まれません。</span><span class="sxs-lookup"><span data-stu-id="4aaef-130">Length does not include signs and decimal notations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4aaef-131">X12_AN の文字列データ型では、最小長の要件を満たすために、どのセグメントでも先頭のスペースが保持され、後続のスペースが許可されます。</span><span class="sxs-lookup"><span data-stu-id="4aaef-131">For the X12_AN string data type, leading spaces are preserved and trailing spaces are allowed in any segment to satisfy the minimum length requirement.</span></span>  
  
 <span data-ttu-id="4aaef-132">KECA では、長さはバイト数として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="4aaef-132">For KECA, length is interpreted as the number of bytes.</span></span> <span data-ttu-id="4aaef-133">たとえば、長さが 3 つとして定義される場合要素またはサブ要素含めることができます 3 つの 1 バイト文字または 1 つの 2 バイト文字と 1 つの 1 バイト文字の組み合わせのいずれか。</span><span class="sxs-lookup"><span data-stu-id="4aaef-133">For example, if the length is defined as three, the element or sub-element can include either three one-byte characters or the combination of one two-byte character and one one-byte character.</span></span>  
  
 <span data-ttu-id="4aaef-134">**空のデータ要素と末尾の区切り文字の検証**</span><span class="sxs-lookup"><span data-stu-id="4aaef-134">**Empty Data Elements and Trailing Separator Validation**</span></span>  
  
 <span data-ttu-id="4aaef-135">X12 では、必須とマークされたデータ要素は、セグメントが存在する場合、インスタンス内で空であってはなりません。</span><span class="sxs-lookup"><span data-stu-id="4aaef-135">For X12, data elements marked as mandatory cannot be empty in an instance if the segment is present.</span></span> <span data-ttu-id="4aaef-136">データ要素が複合型である場合は、少なくとも 1 つのコンポーネント データ要素に値が格納されていることが必要です。</span><span class="sxs-lookup"><span data-stu-id="4aaef-136">If the data element is composite at least one component data element must be valued.</span></span>  
  
 <span data-ttu-id="4aaef-137">EDIFACT では、値のないデータ要素や条件付きのデータ要素 (およびサブコンポーネント) を除外できますが、区切り文字は保持されます。</span><span class="sxs-lookup"><span data-stu-id="4aaef-137">For EDIFACT, non-valued and conditional data elements (and sub-components) may be excluded; however, the separator is retained.</span></span>  
  
 <span data-ttu-id="4aaef-138">X12 または EDIFACT のいずれでも、後続の区切り文字は必須ではありませんが、使用することを推奨します。</span><span class="sxs-lookup"><span data-stu-id="4aaef-138">Trailing separators are not required for either X12 or EDIFACT, but are recommended.</span></span>  
  
## <a name="when-edi-type-validation-is-disabled"></a><span data-ttu-id="4aaef-139">EDI の種類の検証が無効になっている場合</span><span class="sxs-lookup"><span data-stu-id="4aaef-139">When EDI Type Validation Is Disabled</span></span>  
 <span data-ttu-id="4aaef-140">EDI の種類の検証を無効にすると、EDI 受信パイプラインまたは EDI 送信パイプラインは、処理中のメッセージを中断することなく、EDI の種類の検証によってエラーがチェックされたデータ要素を処理します。</span><span class="sxs-lookup"><span data-stu-id="4aaef-140">If you deactivate the EDI type validation, the EDI receive pipeline or EDI send pipeline will process data elements that have errors checked by the EDI type validation without suspending the message being processed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4aaef-141">EDI の種類の検証が無効であっても、EDI の構造の検証は実行されます。</span><span class="sxs-lookup"><span data-stu-id="4aaef-141">EDI structural validation is performed even if the EDI type validation is disabled.</span></span> <span data-ttu-id="4aaef-142">EDI の種類の検証が無効であっても、基本的な構造の検証でエラーとなったインターチェンジは中断されます。</span><span class="sxs-lookup"><span data-stu-id="4aaef-142">An interchange that fails the basic structural validations will be suspended, even if the EDI Type validation is disabled.</span></span>  
  
 <span data-ttu-id="4aaef-143">メッセージが中断されることなく処理されるエラーには以下のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="4aaef-143">Some of the errors that will be processed without causing the message to be suspended are:</span></span>  
  
- <span data-ttu-id="4aaef-144">予期しないまたは未定義のトランザクション セット</span><span class="sxs-lookup"><span data-stu-id="4aaef-144">An unexpected/undefined transaction set</span></span>  
  
- <span data-ttu-id="4aaef-145">セグメント/ループおよびデータ要素レベルでの予期せぬデータまたは未定義のデータ</span><span class="sxs-lookup"><span data-stu-id="4aaef-145">Unexpected/undefined data at the segment/loop and data element level</span></span>  
  
- <span data-ttu-id="4aaef-146">セグメント/ループおよびデータ要素レベルでの任意選択 (最小と最大の出現)</span><span class="sxs-lookup"><span data-stu-id="4aaef-146">Optionality (min and max occurs) at the segment/loop and data element level</span></span>  
  
- <span data-ttu-id="4aaef-147">データ要素レベルでの長さ (最小/最大) 違反 (最大レベルを超える長さのデータまたは最小レベルを下回る長さのデータ)</span><span class="sxs-lookup"><span data-stu-id="4aaef-147">Length (min/max) violation at the data element level (data with length exceeding the maximum level or below the minimum level)</span></span>  
  
- <span data-ttu-id="4aaef-148">データ要素レベルでのデータ型の不一致 (ID データ型は独自の制御があるため除く)</span><span class="sxs-lookup"><span data-stu-id="4aaef-148">Data type mismatch at the data element level (except for the ID data type, which has its own control)</span></span>  
  
- <span data-ttu-id="4aaef-149">データ要素レベルでの無効な列挙リスト</span><span class="sxs-lookup"><span data-stu-id="4aaef-149">Invalid enumeration list at the data element level.</span></span>  
  
  <span data-ttu-id="4aaef-150">EDI の種類の検証が受信側では無効になっており、送信側では有効になっている場合、XML ファイルにエラーが含まれていると、EDI の送信パイプラインは、受信パイプラインで生成された XML を再処理して有効な EDI ファイルを作成することができません。</span><span class="sxs-lookup"><span data-stu-id="4aaef-150">If EDI type validation is disabled on the receive side, but enabled on the send side, the EDI send pipeline will not be able to reprocess the XML produced by the receive pipeline into a valid EDI file if the XML file contains errors.</span></span> <span data-ttu-id="4aaef-151">その結果、送信パイプラインでエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="4aaef-151">As a result, the send pipeline will generate an error.</span></span>  
  
  <span data-ttu-id="4aaef-152">EDI の種類の検証が無効になっていると、EDI 受信パイプラインまたは送信パイプラインは以下のようにエラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="4aaef-152">If EDI Type validation is disabled, the EDI receive pipeline or send pipeline will handle errors as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4aaef-153">予期せぬデータ</span><span class="sxs-lookup"><span data-stu-id="4aaef-153">Unexpected Data</span></span>|<span data-ttu-id="4aaef-154">操作</span><span class="sxs-lookup"><span data-stu-id="4aaef-154">Action</span></span>|  
|<span data-ttu-id="4aaef-155">予期せぬトランザクション セットまたは未定義のトランザクション セット</span><span class="sxs-lookup"><span data-stu-id="4aaef-155">Unexpected/undefined transaction set</span></span>|<span data-ttu-id="4aaef-156">EDI 受信パイプラインまたは送信パイプラインは、スキーマが展開されていない場合でもトランザクション セットを受け付けます。</span><span class="sxs-lookup"><span data-stu-id="4aaef-156">The EDI receive or send pipeline will accept a transaction set even if a schema for it has not been deployed</span></span>|  
|<span data-ttu-id="4aaef-157">予期せぬセグメントまたはレコード</span><span class="sxs-lookup"><span data-stu-id="4aaef-157">Unexpected segment/record</span></span>|<span data-ttu-id="4aaef-158">受信パイプラインは、適切なプレフィックスを持つタグを生成: \<unexpectedsegment _ %segmentid%\>します。</span><span class="sxs-lookup"><span data-stu-id="4aaef-158">The receive pipeline will generate a tag with the appropriate prefix: \<UnexpectedSegment_%SegmentID%\>.</span></span><br /><br /> <span data-ttu-id="4aaef-159">送信パイプラインは、XML タグ名の最初の 1 ～ 3 文字をセグメント名として使用します。</span><span class="sxs-lookup"><span data-stu-id="4aaef-159">The send pipeline will use the first one to three characters of the XML Tag name as the segment name.</span></span>|  
|<span data-ttu-id="4aaef-160">予期せぬ単純なデータ要素</span><span class="sxs-lookup"><span data-stu-id="4aaef-160">Unexpected simple data element</span></span>|<span data-ttu-id="4aaef-161">受信パイプラインは、プレフィックス、セグメント識別子、セグメント中のデータ要素の位置を表すインデックス <UnexpectedDataElement_%FieldName% の付いた XML タグを生成します。</span><span class="sxs-lookup"><span data-stu-id="4aaef-161">The receive pipeline will generate an XML tag with a prefix, segment identifier, and index representing the position of the data element in the segment: <UnexpectedDataElement_%FieldName%.</span></span>|  
|<span data-ttu-id="4aaef-162">予期せぬ複合データ要素</span><span class="sxs-lookup"><span data-stu-id="4aaef-162">Unexpected composite data element</span></span>|<span data-ttu-id="4aaef-163">受信パイプラインは、プレフィックス、セグメント識別子、セグメント中のデータ要素の位置を表すインデックス <UnexpectedCompositeDataElement_%FieldName% の付いた XML タグを生成します。</span><span class="sxs-lookup"><span data-stu-id="4aaef-163">The receive pipeline will generate an XML tags with prefix, segment identifier, and index representing the position of the data element in the segment: <UnexpectedCompositeDataElement_%FieldName%.</span></span>|  
|<span data-ttu-id="4aaef-164">必須データの不足</span><span class="sxs-lookup"><span data-stu-id="4aaef-164">Missing required data</span></span>|<span data-ttu-id="4aaef-165">パイプラインはデータを省略可能として扱います。</span><span class="sxs-lookup"><span data-stu-id="4aaef-165">The pipeline will treat the data as optional.</span></span>|  
|<span data-ttu-id="4aaef-166">データ要素の長さ違反</span><span class="sxs-lookup"><span data-stu-id="4aaef-166">Data element length violation</span></span>|<span data-ttu-id="4aaef-167">パイプラインは無効なデータ要素の長さを有効として扱います (最小がゼロ、最大が無制限)。</span><span class="sxs-lookup"><span data-stu-id="4aaef-167">The pipeline will treat the invalid data element length as valid (min = 0 and max = unbounded).</span></span>|  
|<span data-ttu-id="4aaef-168">インスタンス内の無効な列挙値 (ID データ型に該当)</span><span class="sxs-lookup"><span data-stu-id="4aaef-168">Invalid enumeration value in the instance (applicable to the ID data type)</span></span>|<span data-ttu-id="4aaef-169">パイプラインはエラーを無視して処理を続行します。</span><span class="sxs-lookup"><span data-stu-id="4aaef-169">The pipeline will ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="4aaef-170">インスタンス内の最大出現違反</span><span class="sxs-lookup"><span data-stu-id="4aaef-170">‘Max’ repletion violation in the instance</span></span>|<span data-ttu-id="4aaef-171">パイプラインはその反復データを有効として扱います (最小出現がゼロ、最大出現が無制限)。</span><span class="sxs-lookup"><span data-stu-id="4aaef-171">The pipeline will treat such repetitive data as valid (min occurs = 0 and max occurs = unbounded).</span></span>|  
  
 <span data-ttu-id="4aaef-172">**[エラー報告]**</span><span class="sxs-lookup"><span data-stu-id="4aaef-172">**Error Reporting**</span></span>  
  
 <span data-ttu-id="4aaef-173">EDI の種類の検証を無効にすると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のイベント ビューアーではエラーは報告されませんが、警告は報告されます。</span><span class="sxs-lookup"><span data-stu-id="4aaef-173">When EDI type validation is turned off, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] does not report errors in the Event Viewer, but reports a warning.</span></span> <span data-ttu-id="4aaef-174">また、受信確認で Accept がソース パーティに報告されます。その際、X12 997 では AK501 および AK901 が "E" に設定され、EDIFACT CONTRL では UCI.4、UCM.3、UCF.4 が "7" に設定されます。</span><span class="sxs-lookup"><span data-stu-id="4aaef-174">In addition, the acknowledgment reports an ‘Accept’ back to the source party, setting AK501 and AK901 as “E” in an X12 997 or UCI.4, UCM.3, and UCF.4 as “7” in an EDIFACT CONTRL.</span></span> <span data-ttu-id="4aaef-175">その結果、将来の送信で訂正される可能性が除去されます。</span><span class="sxs-lookup"><span data-stu-id="4aaef-175">As a result, any chance of rectification in future transmissions will be eliminated.</span></span> <span data-ttu-id="4aaef-176">しかし、メッセージの受信者は、メッセージを拒否または中断するのではなく、手動で介入することによりドキュメントを復旧できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4aaef-176">However, receivers of the message will have an opportunity to salvage the document via manual intervention rather than the message being rejected or suspended.</span></span> <span data-ttu-id="4aaef-177">また、EDI 受信パイプラインでこれらのエラーが発生すると、`Edi.ErrorsInTransactionSet` コンテキスト プロパティが昇格されます。</span><span class="sxs-lookup"><span data-stu-id="4aaef-177">Also, the `Edi.ErrorsInTransactionSet` context property will be promoted if any of these errors are encountered by the EDI receive pipeline.</span></span> <span data-ttu-id="4aaef-178">このプロパティは、EDI 検証エラーまたは拡張検証エラーが発生した場合は True として昇格されます。</span><span class="sxs-lookup"><span data-stu-id="4aaef-178">This property will be promoted as "True" if EDI or Extended validation errors are encountered.</span></span> <span data-ttu-id="4aaef-179">エラーが発生しなかった場合は False として昇格されます。</span><span class="sxs-lookup"><span data-stu-id="4aaef-179">If not errors are encountered, the property will be promoted as "False".</span></span>  
  
 <span data-ttu-id="4aaef-180">受信パイプラインまたは送信パイプラインは、予期せぬデータを検出すると、親レベルでエラーを報告し、以下のように子レベルのエラーを無視します。</span><span class="sxs-lookup"><span data-stu-id="4aaef-180">If the receive or send pipeline encounters unexpected data, it will report the error at the parent level and ignore child level errors, as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4aaef-181">予期せぬデータ</span><span class="sxs-lookup"><span data-stu-id="4aaef-181">Unexpected Data</span></span>|<span data-ttu-id="4aaef-182">操作</span><span class="sxs-lookup"><span data-stu-id="4aaef-182">Action</span></span>|  
|<span data-ttu-id="4aaef-183">予期せぬトランザクション セット</span><span class="sxs-lookup"><span data-stu-id="4aaef-183">Unexpected transaction set</span></span>|<span data-ttu-id="4aaef-184">受信確認でこのエラーが報告され、セグメント/ループおよびデータ要素レベルでの後続のエラーは無視されます。</span><span class="sxs-lookup"><span data-stu-id="4aaef-184">The acknowledgment reports this error and ignores subsequent errors at the segment/loop and data element level</span></span>|  
|<span data-ttu-id="4aaef-185">予期せぬセグメント/ループ</span><span class="sxs-lookup"><span data-stu-id="4aaef-185">Unexpected segment/loop</span></span>|<span data-ttu-id="4aaef-186">受信確認でこのエラーが報告され、データ要素レベルでのエラーは無視されます。</span><span class="sxs-lookup"><span data-stu-id="4aaef-186">The acknowledgment reports this error and ignores errors at the data element level.</span></span>|  
|<span data-ttu-id="4aaef-187">予期せぬデータ要素</span><span class="sxs-lookup"><span data-stu-id="4aaef-187">Unexpected data element</span></span>|<span data-ttu-id="4aaef-188">受信確認でこのエラーが報告され、ID、長さ、出現などのプロパティに関連する複合エラーと、複合データ要素フィールドに関するエラー (該当する場合) は無視されます。</span><span class="sxs-lookup"><span data-stu-id="4aaef-188">The acknowledgment reports this error and ignores compound errors relating to properties like ID, length, occours, etc) and errors relating to composite data element fields (if applicable).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4aaef-189">参照</span><span class="sxs-lookup"><span data-stu-id="4aaef-189">See Also</span></span>  
 <span data-ttu-id="4aaef-190">[EDI メッセージの検証](../core/edi-message-validation.md) </span><span class="sxs-lookup"><span data-stu-id="4aaef-190">[EDI Message Validation](../core/edi-message-validation.md) </span></span>  
 [<span data-ttu-id="4aaef-191">拡張された (BTS-XSD) 検証</span><span class="sxs-lookup"><span data-stu-id="4aaef-191">Extended (BTS-XSD) Validation</span></span>](../core/extended-bts-xsd-validation.md)