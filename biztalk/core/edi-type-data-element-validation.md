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
ms.openlocfilehash: 22dd511711a8ec2245c1196e5865f574cf47fc08
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389142"
---
# <a name="edi-type-data-element-validation"></a><span data-ttu-id="5d016-102">EDI の種類 (データ要素) 検証</span><span class="sxs-lookup"><span data-stu-id="5d016-102">EDI Type (Data Element) Validation</span></span>
<span data-ttu-id="5d016-103">EDI 受信パイプラインと EDI 送信パイプラインは、トランザクション セット データ要素に対して EDI 検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="5d016-103">The EDI receive pipeline and EDI send pipeline perform EDI validation on transaction-set data elements.</span></span> <span data-ttu-id="5d016-104">この検証が上のすべてのメッセージから、またはそのパーティとのアグリーメントのプロパティを通じて、特定のパーティに用に構成された、**検証**ページ (下、**トランザクション セットの設定**x12 のいずれかのセクションまたは EDIFACT アグリーメント) で変更します。</span><span class="sxs-lookup"><span data-stu-id="5d016-104">This validation is configured for all messages from or to a specific party, through that party's agreement properties on the **Validation** page (under the **Transaction Set Settings** section for either X12 or EDIFACT agreements).</span></span> <span data-ttu-id="5d016-105">場合、 **EDI 型の検証**でプロパティが選択されていない、**検証**] ページの [データのこのトピックで説明されている検証は実行されません。</span><span class="sxs-lookup"><span data-stu-id="5d016-105">If the **EDI Type Validation** property is not selected in the **Validation** page, the data validations described in this topic will not be performed.</span></span>  
  
 <span data-ttu-id="5d016-106">選択する受信と送信メッセージの EDI の種類の検証が有効になっている、 **EDI の種類の検証**プロパティ、**検証**双方向アグリーメントタブのページ**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="5d016-106">EDI type validation is enabled for incoming as well as outgoing messages by selecting the **EDI type Validation** property in the **Validation** page of the bi-directional agreement tabs in the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="5d016-107">受信と送信の両方のメッセージの EDI の検証が既定で有効にするため、このプロパティは既定で選択されます。</span><span class="sxs-lookup"><span data-stu-id="5d016-107">For both incoming and outgoing messages, this property is selected by default so that EDI validation is enabled by default.</span></span>  
  
## <a name="validation-checks"></a><span data-ttu-id="5d016-108">検証チェック</span><span class="sxs-lookup"><span data-stu-id="5d016-108">Validation Checks</span></span>  
 <span data-ttu-id="5d016-109">EDI 受信パイプラインまたは EDI 送信パイプラインは、EDI 検証を実行します。、検証します。</span><span class="sxs-lookup"><span data-stu-id="5d016-109">When the EDI receive pipeline or EDI send pipeline performs EDI validation, it validates the following:</span></span>  
  
- <span data-ttu-id="5d016-110">スキーマの EDI プロパティで定義されたデータ型</span><span class="sxs-lookup"><span data-stu-id="5d016-110">Data types as defined by the EDI properties of the schema</span></span>  
  
- <span data-ttu-id="5d016-111">長さの制限</span><span class="sxs-lookup"><span data-stu-id="5d016-111">Length restrictions</span></span>  
  
- <span data-ttu-id="5d016-112">空のデータ要素と末尾の区切り記号</span><span class="sxs-lookup"><span data-stu-id="5d016-112">Empty data elements and trailing separators</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="5d016-113">この検証では、コードのセット (列挙) または最小値または最大の出現はチェックされません。</span><span class="sxs-lookup"><span data-stu-id="5d016-113">This validation does not check code sets (enumerations) or min or max occurs.</span></span>  
  
  <span data-ttu-id="5d016-114">**文字セット**</span><span class="sxs-lookup"><span data-stu-id="5d016-114">**Character Sets**</span></span>  
  
  <span data-ttu-id="5d016-115">EDI データ要素の検証を実行するのには、EDI は受信し、送信パイプラインが文字セットが次のように確立されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d016-115">To perform EDI data element validations, the EDI receive and send pipelines require the character set to be established as follows:</span></span>  
  
- <span data-ttu-id="5d016-116">データ要素で、edifact 文字セットが確立されている**UNB1**の**文字セットと区切り記号**の一方向アグリーメント タブのページ、**アグリーメントのプロパティ**ダイアログ ボックスまたは**EDIFACT フォールバックの設定** ダイアログ ボックス (アグリーメントが設定されていない) 場合。</span><span class="sxs-lookup"><span data-stu-id="5d016-116">For EDIFACT, the character set is established in data element **UNB1** of the **Charset and Separators** page of the one-way agreement tab of the **Agreement Properties** dialog box or the **EDIFACT Fallback Settings** dialog box (if no agreement has been established).</span></span>  
  
- <span data-ttu-id="5d016-117">データ要素で、kedifact 文字が確立されている**UNB1**の**文字セットと区切り記号**の一方向アグリーメント タブのページ、**アグリーメントのプロパティ**ダイアログボックスでは、EDIFACT の場合とします。</span><span class="sxs-lookup"><span data-stu-id="5d016-117">For KEDIFACT, the character is established in data element **UNB1** of the **Charset and Separators** page of the one-way agreement tab of the **Agreement Properties** dialog box, as for EDIFACT.</span></span> <span data-ttu-id="5d016-118">値、 **UNB1.1**に要素を設定する必要があります`KECA`します。</span><span class="sxs-lookup"><span data-stu-id="5d016-118">The value for the **UNB1.1** element must be set to `KECA`.</span></span>  
  
- <span data-ttu-id="5d016-119">X12 の場合、文字セットが、メッセージのパイプライン プロパティで確立されます。</span><span class="sxs-lookup"><span data-stu-id="5d016-119">For X12, the character set is established for the message in the pipeline properties.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="5d016-120">X12 を使用は、BizTalk ランタイムでは、メッセージの EDI 検証を実行するときに文字セット、パイプライン プロパティで選択します。</span><span class="sxs-lookup"><span data-stu-id="5d016-120">When the BizTalk runtime performs EDI validation of a message, it will use the X12 character set selected in the pipeline properties.</span></span> <span data-ttu-id="5d016-121">ただし、プロパティの検証がのページで入力、**アグリーメントのプロパティ**設定で選択した文字を使用して、ダイアログ ボックスが実行される、**文字セットと区切り記号**そのダイアログ ボックスのページ。</span><span class="sxs-lookup"><span data-stu-id="5d016-121">However, validation of the properties entered in the pages of the **Agreement Properties** dialog box is performed using the character set selected in the **Charset and Separators** page of that dialog box.</span></span> <span data-ttu-id="5d016-122">実行時に、パイプラインは、値を無視の X12 文字セット プロパティ**文字セットと区切り記号**のページ、**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="5d016-122">During runtime, the pipeline ignores the value of the X12 character set property **Charset and Separators** page of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="5d016-123">これら 2 つの設定は、同じ場合 (X12 文字セット プロパティなど、**アグリーメントのプロパティ** ダイアログ ボックスに設定されて**拡張**パイプライン プロパティで文字プロパティに設定の X12 の while**基本的な**)、メッセージ検証エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5d016-123">If these two settings are not the same (i.e., the X12 character set property in the **Agreement Properties** dialog box is set to **Extended** while the X12 character property in the pipeline properties is set to **Basic**), message validation errors could result.</span></span>  
  
  <span data-ttu-id="5d016-124">**データ型の検証**</span><span class="sxs-lookup"><span data-stu-id="5d016-124">**Data Type Validation**</span></span>  
  
  <span data-ttu-id="5d016-125">X12 の場合、次の EDI データ型はスキーマ検証のための受信または送信パイプラインにおける逆アセンブラーまたはアセンブラー コンポーネントで注釈付き。数値、10 進数、識別子、文字列、日付、時刻、バイナリ、および合成。</span><span class="sxs-lookup"><span data-stu-id="5d016-125">For X12, the following EDI data types are annotated in schema for validation by the Disassembler/Assembler components in the Receive or Send Pipelines: Numeric, Decimal, Identifier, String, Date, Time, Binary, and Composite.</span></span>  
  
  <span data-ttu-id="5d016-126">Edifact では、受信または送信パイプラインにおける逆アセンブラーまたはアセンブラー コンポーネントで、次の EDI データ型が検証スキーマで注釈付き。アルファベット、数値、識別子、文字列、および合成。</span><span class="sxs-lookup"><span data-stu-id="5d016-126">For EDIFACT, the following EDI data types are annotated in schema for validation by the Disassembler/Assembler components in the Receive or Send Pipelines: Alphabetic, Numeric, Identifier, String, and Composite.</span></span>  
  
  <span data-ttu-id="5d016-127">**長さの制限**</span><span class="sxs-lookup"><span data-stu-id="5d016-127">**Length Restrictions**</span></span>  
  
  <span data-ttu-id="5d016-128">X12 と EDIFACT の両方の要素またはサブ要素を長さ (最小および最大) 要件を検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d016-128">For both X12 and EDIFACT, elements or sub-elements must be validated for length (minimum and maximum) requirement.</span></span> <span data-ttu-id="5d016-129">長さは、使用する文字位置の数として定義されます。</span><span class="sxs-lookup"><span data-stu-id="5d016-129">Length is defined as the number of character positions used.</span></span> <span data-ttu-id="5d016-130">長さは、符号および小数点表記は含まれません。</span><span class="sxs-lookup"><span data-stu-id="5d016-130">Length does not include signs and decimal notations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d016-131">X12_AN の文字列データ型の先頭のスペースが保持され、最小長の要件を満たすために任意のセグメントの末尾のスペースが許可されています。</span><span class="sxs-lookup"><span data-stu-id="5d016-131">For the X12_AN string data type, leading spaces are preserved and trailing spaces are allowed in any segment to satisfy the minimum length requirement.</span></span>  
  
 <span data-ttu-id="5d016-132">Keca では、長さはバイト数として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="5d016-132">For KECA, length is interpreted as the number of bytes.</span></span> <span data-ttu-id="5d016-133">たとえば、長さが 3 つとして定義される場合要素またはサブ要素含めることができます 3 つの 1 バイト文字または 1 つの 2 バイト文字と 1 つの 1 バイト文字の組み合わせのいずれか。</span><span class="sxs-lookup"><span data-stu-id="5d016-133">For example, if the length is defined as three, the element or sub-element can include either three one-byte characters or the combination of one two-byte character and one one-byte character.</span></span>  
  
 <span data-ttu-id="5d016-134">**空のデータ要素と末尾の区切り文字の検証**</span><span class="sxs-lookup"><span data-stu-id="5d016-134">**Empty Data Elements and Trailing Separator Validation**</span></span>  
  
 <span data-ttu-id="5d016-135">X12 の場合、データ要素が必須としてマークされていることはできません空にするインスタンスのセグメントが存在する場合です。</span><span class="sxs-lookup"><span data-stu-id="5d016-135">For X12, data elements marked as mandatory cannot be empty in an instance if the segment is present.</span></span> <span data-ttu-id="5d016-136">データ要素が複合要素の少なくとも 1 つのコンポーネント データ要素の値を持つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="5d016-136">If the data element is composite at least one component data element must be valued.</span></span>  
  
 <span data-ttu-id="5d016-137">EDIFACT の場合、値のないと条件付きデータ要素 (およびサブコンポーネント) を除外する可能性があります。ただし、区切り記号が保持されます。</span><span class="sxs-lookup"><span data-stu-id="5d016-137">For EDIFACT, non-valued and conditional data elements (and sub-components) may be excluded; however, the separator is retained.</span></span>  
  
 <span data-ttu-id="5d016-138">末尾の区切り記号は、X12 または EDIFACT では、必須ではありませんはお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5d016-138">Trailing separators are not required for either X12 or EDIFACT, but are recommended.</span></span>  
  
## <a name="when-edi-type-validation-is-disabled"></a><span data-ttu-id="5d016-139">EDI 型の検証が無効になっています</span><span class="sxs-lookup"><span data-stu-id="5d016-139">When EDI Type Validation Is Disabled</span></span>  
 <span data-ttu-id="5d016-140">EDI 型の検証を無効化する場合は、EDI 受信パイプラインまたは EDI 送信パイプラインは EDI 型の検証処理中のメッセージを中断することがなくチェック エラーが発生したデータ要素を処理します。</span><span class="sxs-lookup"><span data-stu-id="5d016-140">If you deactivate the EDI type validation, the EDI receive pipeline or EDI send pipeline will process data elements that have errors checked by the EDI type validation without suspending the message being processed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d016-141">EDI 型の検証が無効になっている場合でも、EDI 構造検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="5d016-141">EDI structural validation is performed even if the EDI type validation is disabled.</span></span> <span data-ttu-id="5d016-142">EDI 型の検証が無効になっている場合でも、基本的な構造検証に失敗したインターチェンジは保留されます。</span><span class="sxs-lookup"><span data-stu-id="5d016-142">An interchange that fails the basic structural validations will be suspended, even if the EDI Type validation is disabled.</span></span>  
  
 <span data-ttu-id="5d016-143">中断するメッセージを発生させることがなく処理されるエラーを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5d016-143">Some of the errors that will be processed without causing the message to be suspended are:</span></span>  
  
- <span data-ttu-id="5d016-144">予期しないまたは未定義のトランザクション セット</span><span class="sxs-lookup"><span data-stu-id="5d016-144">An unexpected/undefined transaction set</span></span>  
  
- <span data-ttu-id="5d016-145">セグメント/ループおよびデータ要素レベルでの予期しないまたは未定義のデータ</span><span class="sxs-lookup"><span data-stu-id="5d016-145">Unexpected/undefined data at the segment/loop and data element level</span></span>  
  
- <span data-ttu-id="5d016-146">Optionality (min と max は発生) セグメント/ループおよびデータ要素レベルで</span><span class="sxs-lookup"><span data-stu-id="5d016-146">Optionality (min and max occurs) at the segment/loop and data element level</span></span>  
  
- <span data-ttu-id="5d016-147">データ要素レベル (データまたは最小レベルを下回る長さが最大レベルを超える) の長さ (最小/最大) 違反</span><span class="sxs-lookup"><span data-stu-id="5d016-147">Length (min/max) violation at the data element level (data with length exceeding the maximum level or below the minimum level)</span></span>  
  
- <span data-ttu-id="5d016-148">(独自のコントロールが、ID データ型) を除くデータ要素レベルでのデータ型の不一致</span><span class="sxs-lookup"><span data-stu-id="5d016-148">Data type mismatch at the data element level (except for the ID data type, which has its own control)</span></span>  
  
- <span data-ttu-id="5d016-149">データ要素レベルで無効な列挙リスト。</span><span class="sxs-lookup"><span data-stu-id="5d016-149">Invalid enumeration list at the data element level.</span></span>  
  
  <span data-ttu-id="5d016-150">EDI 型の検証は、受信側で無効になっていますが、送信側で有効になっている場合、EDI 送信パイプラインは、XML ファイルにエラーが含まれている場合、有効な EDI ファイルに、受信パイプラインで生成される XML を再処理することはできません。</span><span class="sxs-lookup"><span data-stu-id="5d016-150">If EDI type validation is disabled on the receive side, but enabled on the send side, the EDI send pipeline will not be able to reprocess the XML produced by the receive pipeline into a valid EDI file if the XML file contains errors.</span></span> <span data-ttu-id="5d016-151">その結果、送信パイプライン エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5d016-151">As a result, the send pipeline will generate an error.</span></span>  
  
  <span data-ttu-id="5d016-152">EDI 型の検証が無効になっている場合、EDI 受信パイプラインまたは送信パイプラインでは、エラーを次のように処理されます。</span><span class="sxs-lookup"><span data-stu-id="5d016-152">If EDI Type validation is disabled, the EDI receive pipeline or send pipeline will handle errors as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5d016-153">予期しないデータ</span><span class="sxs-lookup"><span data-stu-id="5d016-153">Unexpected Data</span></span>|<span data-ttu-id="5d016-154">操作</span><span class="sxs-lookup"><span data-stu-id="5d016-154">Action</span></span>|  
|<span data-ttu-id="5d016-155">予期しないまたは未定義のトランザクション セット</span><span class="sxs-lookup"><span data-stu-id="5d016-155">Unexpected/undefined transaction set</span></span>|<span data-ttu-id="5d016-156">EDI 受信パイプラインまたは送信パイプラインは、トランザクション セットをそのスキーマが展開されていない場合でも、受け付ける</span><span class="sxs-lookup"><span data-stu-id="5d016-156">The EDI receive or send pipeline will accept a transaction set even if a schema for it has not been deployed</span></span>|  
|<span data-ttu-id="5d016-157">予期しないセグメントまたはレコード</span><span class="sxs-lookup"><span data-stu-id="5d016-157">Unexpected segment/record</span></span>|<span data-ttu-id="5d016-158">受信パイプライン、適切なプレフィックスを持つタグが生成されます。\<Unexpectedsegment _ %segmentid%\>します。</span><span class="sxs-lookup"><span data-stu-id="5d016-158">The receive pipeline will generate a tag with the appropriate prefix: \<UnexpectedSegment_%SegmentID%\>.</span></span><br /><br /> <span data-ttu-id="5d016-159">送信パイプラインは、セグメント名として最初の XML タグ名の 1 ~ 3 文字が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5d016-159">The send pipeline will use the first one to three characters of the XML Tag name as the segment name.</span></span>|  
|<span data-ttu-id="5d016-160">予期せぬ単純データ要素</span><span class="sxs-lookup"><span data-stu-id="5d016-160">Unexpected simple data element</span></span>|<span data-ttu-id="5d016-161">受信パイプラインは、プレフィックス、セグメント識別子、セグメント データ要素の位置を表すインデックスと XML タグが生成されます: < unexpecteddataelement _ %fieldname% します。</span><span class="sxs-lookup"><span data-stu-id="5d016-161">The receive pipeline will generate an XML tag with a prefix, segment identifier, and index representing the position of the data element in the segment: <UnexpectedDataElement_%FieldName%.</span></span>|  
|<span data-ttu-id="5d016-162">予期せぬ複合データ要素</span><span class="sxs-lookup"><span data-stu-id="5d016-162">Unexpected composite data element</span></span>|<span data-ttu-id="5d016-163">受信パイプラインでは、XML を生成します。 プレフィックス、セグメント識別子、セグメント データ要素の位置を表すインデックスとタグ: < unexpectedcompositedataelement _ %fieldname% します。</span><span class="sxs-lookup"><span data-stu-id="5d016-163">The receive pipeline will generate an XML tags with prefix, segment identifier, and index representing the position of the data element in the segment: <UnexpectedCompositeDataElement_%FieldName%.</span></span>|  
|<span data-ttu-id="5d016-164">必要なデータがありません。</span><span class="sxs-lookup"><span data-stu-id="5d016-164">Missing required data</span></span>|<span data-ttu-id="5d016-165">パイプラインでは、オプションとして、データを扱います。</span><span class="sxs-lookup"><span data-stu-id="5d016-165">The pipeline will treat the data as optional.</span></span>|  
|<span data-ttu-id="5d016-166">データ要素の長さ違反</span><span class="sxs-lookup"><span data-stu-id="5d016-166">Data element length violation</span></span>|<span data-ttu-id="5d016-167">パイプラインは、有効と無効なデータ要素の長さを扱います (最小 = 0、最大が無制限)。</span><span class="sxs-lookup"><span data-stu-id="5d016-167">The pipeline will treat the invalid data element length as valid (min = 0 and max = unbounded).</span></span>|  
|<span data-ttu-id="5d016-168">(ID データ型に適用) のインスタンスに無効な列挙値</span><span class="sxs-lookup"><span data-stu-id="5d016-168">Invalid enumeration value in the instance (applicable to the ID data type)</span></span>|<span data-ttu-id="5d016-169">パイプラインはエラーを無視し、処理を続行します。</span><span class="sxs-lookup"><span data-stu-id="5d016-169">The pipeline will ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="5d016-170">インスタンス内の 'Max' 出現違反</span><span class="sxs-lookup"><span data-stu-id="5d016-170">‘Max’ repletion violation in the instance</span></span>|<span data-ttu-id="5d016-171">パイプラインでは、このような反復的なデータは有効なとして扱います (最小発生数 = 0、最大出現が = unbounded)。</span><span class="sxs-lookup"><span data-stu-id="5d016-171">The pipeline will treat such repetitive data as valid (min occurs = 0 and max occurs = unbounded).</span></span>|  
  
 <span data-ttu-id="5d016-172">**[エラー報告]**</span><span class="sxs-lookup"><span data-stu-id="5d016-172">**Error Reporting**</span></span>  
  
 <span data-ttu-id="5d016-173">EDI 型の検証が入っていないときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が、警告は報告のイベント ビューアーでエラーを報告しません。</span><span class="sxs-lookup"><span data-stu-id="5d016-173">When EDI type validation is turned off, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] does not report errors in the Event Viewer, but reports a warning.</span></span> <span data-ttu-id="5d016-174">さらに、受信確認 '許可' に報告ソース パーティ、AK501 および AK901 を X12 では、"E"として設定し、997 または UCI.4、UCM.3、UCF.4 が「7」、EDIFACT CONTRL でします。</span><span class="sxs-lookup"><span data-stu-id="5d016-174">In addition, the acknowledgment reports an ‘Accept’ back to the source party, setting AK501 and AK901 as “E” in an X12 997 or UCI.4, UCM.3, and UCF.4 as “7” in an EDIFACT CONTRL.</span></span> <span data-ttu-id="5d016-175">その結果、将来の送信で訂正される可能性のある、削除されます。</span><span class="sxs-lookup"><span data-stu-id="5d016-175">As a result, any chance of rectification in future transmissions will be eliminated.</span></span> <span data-ttu-id="5d016-176">ただし、メッセージの受信側では、メッセージを拒否または中断ではなく、手動で介入文書を回収する機会があります。</span><span class="sxs-lookup"><span data-stu-id="5d016-176">However, receivers of the message will have an opportunity to salvage the document via manual intervention rather than the message being rejected or suspended.</span></span> <span data-ttu-id="5d016-177">また、 `Edi.ErrorsInTransactionSet` EDI によってこれらのエラーが発生した場合、コンテキスト プロパティを昇格、受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="5d016-177">Also, the `Edi.ErrorsInTransactionSet` context property will be promoted if any of these errors are encountered by the EDI receive pipeline.</span></span> <span data-ttu-id="5d016-178">EDI または拡張検証エラーが発生した場合、このプロパティを"True"として昇格されます。</span><span class="sxs-lookup"><span data-stu-id="5d016-178">This property will be promoted as "True" if EDI or Extended validation errors are encountered.</span></span> <span data-ttu-id="5d016-179">いない場合は、エラーが発生した、"False"として、プロパティが昇格されます。</span><span class="sxs-lookup"><span data-stu-id="5d016-179">If not errors are encountered, the property will be promoted as "False".</span></span>  
  
 <span data-ttu-id="5d016-180">受信または送信パイプラインには、予期しないデータが検出されるが親レベルでエラーを報告し、次のように子レベルのエラーを無視します。</span><span class="sxs-lookup"><span data-stu-id="5d016-180">If the receive or send pipeline encounters unexpected data, it will report the error at the parent level and ignore child level errors, as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5d016-181">予期しないデータ</span><span class="sxs-lookup"><span data-stu-id="5d016-181">Unexpected Data</span></span>|<span data-ttu-id="5d016-182">操作</span><span class="sxs-lookup"><span data-stu-id="5d016-182">Action</span></span>|  
|<span data-ttu-id="5d016-183">予期せぬトランザクション セット</span><span class="sxs-lookup"><span data-stu-id="5d016-183">Unexpected transaction set</span></span>|<span data-ttu-id="5d016-184">受信確認は、このエラーが報告され、セグメント/ループおよびデータ要素レベルでの後続のエラーを無視します。</span><span class="sxs-lookup"><span data-stu-id="5d016-184">The acknowledgment reports this error and ignores subsequent errors at the segment/loop and data element level</span></span>|  
|<span data-ttu-id="5d016-185">予期しないセグメント/ループ</span><span class="sxs-lookup"><span data-stu-id="5d016-185">Unexpected segment/loop</span></span>|<span data-ttu-id="5d016-186">受信確認では、このエラーが報告され、データ要素レベルでのエラーは無視されます。</span><span class="sxs-lookup"><span data-stu-id="5d016-186">The acknowledgment reports this error and ignores errors at the data element level.</span></span>|  
|<span data-ttu-id="5d016-187">予期せぬデータ要素</span><span class="sxs-lookup"><span data-stu-id="5d016-187">Unexpected data element</span></span>|<span data-ttu-id="5d016-188">受信確認では、このエラーが報告され、ID、長さ、出現などのようなプロパティに関連する複合エラーは無視されます) と (必要な場合)、複合データ要素のフィールドに関連するエラー。</span><span class="sxs-lookup"><span data-stu-id="5d016-188">The acknowledgment reports this error and ignores compound errors relating to properties like ID, length, occours, etc) and errors relating to composite data element fields (if applicable).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5d016-189">参照</span><span class="sxs-lookup"><span data-stu-id="5d016-189">See Also</span></span>  
 <span data-ttu-id="5d016-190">[EDI メッセージの検証](../core/edi-message-validation.md) </span><span class="sxs-lookup"><span data-stu-id="5d016-190">[EDI Message Validation](../core/edi-message-validation.md) </span></span>  
 [<span data-ttu-id="5d016-191">拡張された (BTS-XSD) 検証</span><span class="sxs-lookup"><span data-stu-id="5d016-191">Extended (BTS-XSD) Validation</span></span>](../core/extended-bts-xsd-validation.md)