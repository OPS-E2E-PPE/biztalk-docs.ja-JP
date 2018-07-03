---
title: 検証の既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- known issues, validating
- validating, known issues
ms.assetid: 136596f2-ee0f-4ea9-918c-3608f2ee1be3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73cc1caa3207901780a57e7b1213215217b73326
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010579"
---
# <a name="validation-known-issues"></a><span data-ttu-id="47a07-102">検証に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="47a07-102">Validation Known Issues</span></span>
<span data-ttu-id="47a07-103">このセクションには、検証エラーを回避するために役立つ有用な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="47a07-103">This section contains useful information that may help you avoid validation errors.</span></span>  
  
## <a name="disabling-xml-validation"></a><span data-ttu-id="47a07-104">XML 検証を無効にします。</span><span class="sxs-lookup"><span data-stu-id="47a07-104">Disabling XML validation</span></span>  
 <span data-ttu-id="47a07-105">「本文検証セグメント」フラグ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーは、XML 本文の検証を制御し、予期しない区切り文字と末尾の区切り記号の検証には含まれません。</span><span class="sxs-lookup"><span data-stu-id="47a07-105">The "Validate Body Segments" flag in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer controls the XML body validation and does not include validation of unexpected delimiters and trailing delimiters.</span></span> <span data-ttu-id="47a07-106">メッセージが適切な区切り記号を持たない場合、メッセージを正常に解析できません。</span><span class="sxs-lookup"><span data-stu-id="47a07-106">If a message does not have the proper delimiters, the message cannot be successfully parsed.</span></span> <span data-ttu-id="47a07-107">メッセージを正常に解析できない場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]中間の有効な XML を生成することはできません。</span><span class="sxs-lookup"><span data-stu-id="47a07-107">If a message cannot be successfully parsed, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] cannot generate valid intermediate XML.</span></span> <span data-ttu-id="47a07-108">「本文のセグメントを検証する」フラグを無効にするのでは、次に結果します。</span><span class="sxs-lookup"><span data-stu-id="47a07-108">Disabling the "Validate Body Segments" flag results in the following:</span></span>  
  
1.  <span data-ttu-id="47a07-109">空の必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="47a07-109">Empty required fields.</span></span>  
  
2.  <span data-ttu-id="47a07-110">データ型は検証されません。</span><span class="sxs-lookup"><span data-stu-id="47a07-110">Data types not validated.</span></span>  
  
3.  <span data-ttu-id="47a07-111">セグメントの構造の検証は行われません (セグメントの順序は検証されません)。</span><span class="sxs-lookup"><span data-stu-id="47a07-111">Segment structure is not validated (order of segments is not validated).</span></span>  
  
## <a name="v2xml-acks-with-multiple-errors-will-fail-validation"></a><span data-ttu-id="47a07-112">V2。複数のエラーで XML Ack 検証に失敗します</span><span class="sxs-lookup"><span data-stu-id="47a07-112">V2.XML ACKs with multiple errors will fail validation</span></span>  
 <span data-ttu-id="47a07-113">受信の V2 の場合。XML メッセージには、Microsoft BizTalk Accelerator for HL7 の 1 つ以上のエラーが含まれています ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) パーサーは、V2 生成可能性があります。Error フィールドに 1 つ以上のエラーで XML の確認 (ACK)。</span><span class="sxs-lookup"><span data-stu-id="47a07-113">If an incoming V2.XML message contains more than one error, the Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) parser may generate a V2.XML acknowledgment (ACK) with more than one error in the error field.</span></span> <span data-ttu-id="47a07-114">このような V2。XML の確認には、HL7 標準では、パーサーが、V2 での 1 つだけのエラーを報告できるを指定するために、検証は失敗します。XML の ACK エラー フィールドです。</span><span class="sxs-lookup"><span data-stu-id="47a07-114">Such a V2.XML ACK will fail validation, because the HL7 standard specifies that the parser can report only one error in a V2.XML ACK error field.</span></span>  
  
## <a name="two-parsing-errors-are-logged-when-messages-in-the-batch-inbatch-out-scenario-contain-validation-errors"></a><span data-ttu-id="47a07-115">2 つの解析エラーがログに記録時に、バッチ内のメッセージで/バッチ アウト シナリオは、検証エラーを含めることが</span><span class="sxs-lookup"><span data-stu-id="47a07-115">Two parsing errors are logged when messages in the Batch In/Batch Out scenario contain validation errors</span></span>  
 <span data-ttu-id="47a07-116">バッチ内の最初のメッセージで/バッチ アウト シナリオ (複数のメッセージがバッチ ヘッダーのないバッチ) には、検証エラーが含まれています。[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]イベント ログに 2 つのエラー ログに記録します。</span><span class="sxs-lookup"><span data-stu-id="47a07-116">When the first message in the Batch In/Batch Out scenario (multiple messages batched without batch headers) contains validation errors, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] logs two errors in the Event Log.</span></span> <span data-ttu-id="47a07-117">最初のエラーが、バッチの最初のメッセージに関連し、2 番目のエラーに関連するメッセージの残りの部分。</span><span class="sxs-lookup"><span data-stu-id="47a07-117">The first error pertains to the first message in the batch, and the second error pertains to the remainder of the messages.</span></span>  
  
## <a name="restrictions-in-validating-field-length"></a><span data-ttu-id="47a07-118">フィールドの長さの検証の制限</span><span class="sxs-lookup"><span data-stu-id="47a07-118">Restrictions in validating field length</span></span>  
 <span data-ttu-id="47a07-119">HL7 の複雑なデータ型は、のコンポーネントとサブコンポーネントで構成に関連付けられているフィールドです。</span><span class="sxs-lookup"><span data-stu-id="47a07-119">Fields associated with HL7 complex data types are comprised of components and subcomponents.</span></span> <span data-ttu-id="47a07-120">HL7 の規則は、長さと、フィールド レベルで、コンポーネントまたはサブコンポーネント レベルではなくオプションかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="47a07-120">HL7 rules specify the length and optionality at the field level and not at the component/subcomponent level.</span></span> <span data-ttu-id="47a07-121">たとえば V2.4、HL7 は HD データ型と 180 文字の最大長である MSH3 を制御します。</span><span class="sxs-lookup"><span data-stu-id="47a07-121">For example in V2.4, HL7 governs MSH3 to be of HD data type and 180 characters maximum length.</span></span> <span data-ttu-id="47a07-122">HD は、HD1 セットは、現状、ST、として HD2 セット id。 hd3 はどれも設定して複合データ型は、します。</span><span class="sxs-lookup"><span data-stu-id="47a07-122">HD is a composite data type with HD1 set as IS, HD2 set as ST, and HD3 set as ID.</span></span> <span data-ttu-id="47a07-123">フィールドの長さの制限は、(2 つのコンポーネントの区切り記号を含む) の 3 つのコンポーネント内のデータが 180 小さいことを意味します。</span><span class="sxs-lookup"><span data-stu-id="47a07-123">The field length restriction implies that the data in the three components (including the two component separators) should be less than or equal to 180.</span></span> <span data-ttu-id="47a07-124">ただし、3 つのデータ型の選択肢が指定されていません。つまり、すべてまたは一部のコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="47a07-124">However, the optionality of the three data types is not specified; which means that all or some components may exist.</span></span> <span data-ttu-id="47a07-125">さらに、ST および IS のデータ型では、ユーザーが定義されているため[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]通常定義されているサイトがあるために 3 つのコンポーネント間の長さの分散を意識することはできません。</span><span class="sxs-lookup"><span data-stu-id="47a07-125">Additionally, data types ST and IS are user defined and therefore [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] cannot be aware of the length distribution across the three components, since these are normally site defined.</span></span>  
  
 <span data-ttu-id="47a07-126">これらおよびその他の複雑な問題により[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]フィールドの長さを検証しません。</span><span class="sxs-lookup"><span data-stu-id="47a07-126">Due to these and other complications, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not validate the field length.</span></span> <span data-ttu-id="47a07-127">ただしの長さ制限に個々 のコンポーネントとサブコンポーネント (データ型の単純な) での BizTalk エディターを使用してを適用して[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="47a07-127">However, you can apply length restrictions at each individual component/subcomponent (of data type simple) using BizTalk Editor in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="47a07-128"> これらの処理中に検証されます。</span><span class="sxs-lookup"><span data-stu-id="47a07-128"> will validate these during processing.</span></span>  
  
## <a name="validation-of-batch-and-file-headerstrailers-are-affected-by-enabling-fragmentation"></a><span data-ttu-id="47a07-129">断片化を有効にするとバッチとファイルのヘッダー/トレーラーの検証が影響を受ける</span><span class="sxs-lookup"><span data-stu-id="47a07-129">Validation of batch and file headers/trailers are affected by enabling fragmentation</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="47a07-130"> FHS3 フィールドには、断片化が有効になっているパーティが含まれている場合は、バッチとファイルのヘッダー/トレーラーを検証しません。</span><span class="sxs-lookup"><span data-stu-id="47a07-130"> does not validate batch and file headers/trailers when the FHS3 field contains a party that has fragmentation enabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47a07-131">参照</span><span class="sxs-lookup"><span data-stu-id="47a07-131">See Also</span></span>  
 [<span data-ttu-id="47a07-132">既知の問題</span><span class="sxs-lookup"><span data-stu-id="47a07-132">Known Issues</span></span>](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)