---
title: SWIFT ヘッダーおよびトレーラ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- trailer schemas
- schemas, headers
- schemas, trailers
- header schemas
ms.assetid: 82cd33d4-6bbb-4124-9506-fd35b5dca8a4
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2299ec3a45968cd0aaae2094ec892d03c70972f
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529764"
---
# <a name="swift-header-and-trailer-schemas"></a><span data-ttu-id="26b8d-102">SWIFT ヘッダーおよびトレーラー スキーマ</span><span class="sxs-lookup"><span data-stu-id="26b8d-102">SWIFT Header and Trailer Schemas</span></span>
<span data-ttu-id="26b8d-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] SWIFT ヘッダーおよびトレーラのスキーマを提供します。</span><span class="sxs-lookup"><span data-stu-id="26b8d-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides the SWIFT header and trailer schemas.</span></span> <span data-ttu-id="26b8d-104">A4SWIFT は、これらのさまざまな FIN メッセージのインターチェンジのスキーマに既に組み込みます。</span><span class="sxs-lookup"><span data-stu-id="26b8d-104">A4SWIFT has already incorporated these into the interchange schemas for the various FIN messages.</span></span> <span data-ttu-id="26b8d-105">カスタム SWIFT FIN 書式スタイル メッセージの種類 (たとえば、N98 メッセージ) を作成する場合は、独自の形式に、ヘッダーとトレーラーのスキーマを組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="26b8d-105">If you want to create a custom SWIFT FIN format style message type (for example, an N98 message), you can incorporate the header and trailer schemas into your own format.</span></span>  
  
 <span data-ttu-id="26b8d-106">SWIFT ヘッダー スキーマ (SWIFT Header.xsd) には、次の形式が含まれています。</span><span class="sxs-lookup"><span data-stu-id="26b8d-106">The SWIFT header schema (SWIFT Header.xsd) contains the formats for the following:</span></span>  
  
- <span data-ttu-id="26b8d-107">基本的なヘッダー</span><span class="sxs-lookup"><span data-stu-id="26b8d-107">Basic Header</span></span>  
  
- <span data-ttu-id="26b8d-108">アプリケーション用のヘッダー (入力または出力の選択)</span><span class="sxs-lookup"><span data-stu-id="26b8d-108">Application Header (choice of Input or Output)</span></span>  
  
- <span data-ttu-id="26b8d-109">ユーザー ヘッダー</span><span class="sxs-lookup"><span data-stu-id="26b8d-109">User Header</span></span>  
  
- <span data-ttu-id="26b8d-110">テキスト ブロックの先頭の区切り文字</span><span class="sxs-lookup"><span data-stu-id="26b8d-110">Beginning delimiter of the text block</span></span>  
  
  <span data-ttu-id="26b8d-111">基本的なヘッダーには、メッセージのソースに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="26b8d-111">The Basic Header contains information about the source of the message.</span></span> <span data-ttu-id="26b8d-112">アプリケーションのヘッダーには、メッセージの種類およびメッセージの転送先に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="26b8d-112">The Application Header contains information about the message type and the destination of the message.</span></span> <span data-ttu-id="26b8d-113">受信パイプラインで SWIFT 逆アセンブラーがメッセージの種類の解像度は、適切なアプリケーションのヘッダー内のフィールドの内容に基づいています。</span><span class="sxs-lookup"><span data-stu-id="26b8d-113">The resolution of the message type by the SWIFT disassembler in a receive pipeline is based upon the contents of the field in the appropriate Application Header.</span></span> <span data-ttu-id="26b8d-114">ユーザー ヘッダーは、省略可能な特別な処理命令が含まれています。</span><span class="sxs-lookup"><span data-stu-id="26b8d-114">The User Header is optional, and contains special processing instructions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26b8d-115">いくつかのメッセージの種類には、フィールド 119 ユーザー ヘッダーの内容に基づいて変数の形式があります。</span><span class="sxs-lookup"><span data-stu-id="26b8d-115">A few message types have variable formats based upon the contents of field 119 in the User Header.</span></span> <span data-ttu-id="26b8d-116">これらは、A4SWIFT で「二重メッセージ型」です。</span><span class="sxs-lookup"><span data-stu-id="26b8d-116">These are "dual message types" in A4SWIFT.</span></span> <span data-ttu-id="26b8d-117">A4SWIFT 逆アセンブラーでは、119 フィールドの内容と組み合わせてアプリケーション ヘッダー メッセージの種類を使用して、メッセージ インスタンスの適切なスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="26b8d-117">The A4SWIFT disassembler uses the message type in the Application Header in conjunction with the contents of field 119 to select the appropriate schema for a message instance.</span></span>  
  
 <span data-ttu-id="26b8d-118">*SWIFT ユーザー向けハンドブック*、これらのヘッダーはすべて、FIN サービスの SWIFT ドキュメントの一部であるについて説明します。</span><span class="sxs-lookup"><span data-stu-id="26b8d-118">The *SWIFT User Handbook*, which is part of the SWIFT documentation for the FIN service, describes all of these headers.</span></span>  
  
 <span data-ttu-id="26b8d-119">テキスト ブロックの先頭が"{4:"後にキャリッジ リターンとライン フィードします。</span><span class="sxs-lookup"><span data-stu-id="26b8d-119">The beginning of the text block is "{4:" followed by a carriage return and line feed.</span></span> <span data-ttu-id="26b8d-120">テキスト ブロックの先頭が必要です。</span><span class="sxs-lookup"><span data-stu-id="26b8d-120">The beginning of the text block is required.</span></span>  
  
 <span data-ttu-id="26b8d-121">SWIFT のみを格納しているインターチェンジの処理 (解析と検証) に対応するためにブロック 4、インターチェンジのスキーマ内のすべてのヘッダーとトレーラーのブロックは省略可能としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="26b8d-121">In order to accommodate processing (parsing and validation) of interchanges containing only SWIFT block 4, all header and trailer blocks in the interchange schemas are marked as optional.</span></span> <span data-ttu-id="26b8d-122">これは、基本的なヘッダー ブロック 1 と 2 アプリケーション ヘッダー ブロックは必須、SWIFT FIN 仕様から逸脱します。</span><span class="sxs-lookup"><span data-stu-id="26b8d-122">This deviates from the SWIFT FIN specification, where the Basic Header block 1 and the Application Header block 2 are mandatory.</span></span> <span data-ttu-id="26b8d-123">これにより、ヘッダーを必要としないメッセージを処理するインターチェンジのスキーマを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="26b8d-123">This enables you to use the interchange schema to handle messages that do not require headers.</span></span> <span data-ttu-id="26b8d-124">たとえば、FileAct を通じて受信するメッセージを受け取る場合、バッチ ヘッダーは共通のメッセージ型と同様に、メッセージのソースを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="26b8d-124">For example, if you are accepting messages received through FileAct, the batch header may contain the source of the messages as well as a common message type.</span></span>  
  
 <span data-ttu-id="26b8d-125">ランタイム スキーマ DLL には、ヘッダー スキーマも含まれています。</span><span class="sxs-lookup"><span data-stu-id="26b8d-125">The RunTime schema DLL also includes the header schema.</span></span> <span data-ttu-id="26b8d-126">A4SWIFT インストール環境では、ランタイム スキーマ DLL および A4SWIFT プロパティ スキーマを展開します。</span><span class="sxs-lookup"><span data-stu-id="26b8d-126">A4SWIFT installation deploys the RunTime schema DLL and the A4SWIFT property schema.</span></span> <span data-ttu-id="26b8d-127">処理のため、独自のヘッダーを使用する必要がある場合と定義に、カスタム ヘッダー スキーマを展開し、メッセージ解決のための適切なプロパティを昇格させます。</span><span class="sxs-lookup"><span data-stu-id="26b8d-127">If you need to use your own header for processing, you can define and deploy a custom header schema, and promote the appropriate properties for message resolution.</span></span> <span data-ttu-id="26b8d-128">これを行う場合は、新しいヘッダーを SWIFT 逆アセンブラー (逆アセンブラー) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26b8d-128">If you do so, you will also need to specify the new header to the SWIFT disassembler (DASM).</span></span> <span data-ttu-id="26b8d-129">カスタム ヘッダー スキーマは、その A4SWIFT のインストールが実行時のスキーマ DLL で展開 SWIFT ヘッダー スキーマと同じドキュメントの種類をいないが必要です。</span><span class="sxs-lookup"><span data-stu-id="26b8d-129">The custom header schema should not have the same Document Type as the SWIFT header schema that A4SWIFT installation has deployed in the RunTime schemas DLL.</span></span> <span data-ttu-id="26b8d-130">スキーマの名前空間またはルート ノード名、またはその両方を変更してください。</span><span class="sxs-lookup"><span data-stu-id="26b8d-130">Be sure to change the schema namespace, or root node name, or both.</span></span>  
  
 <span data-ttu-id="26b8d-131">SWIFT トレーラー スキーマ (**SWIFT Trailer.xsd**)、次の形式が含まれています。</span><span class="sxs-lookup"><span data-stu-id="26b8d-131">The SWIFT Trailer schema (**SWIFT Trailer.xsd**) contains the format for the following:</span></span>  
  
- <span data-ttu-id="26b8d-132">テキスト ブロックの末尾の区切り記号</span><span class="sxs-lookup"><span data-stu-id="26b8d-132">Ending delimiter of the text block</span></span>  
  
- <span data-ttu-id="26b8d-133">ユーザー トレーラー (ユーザーおよびシステム情報)</span><span class="sxs-lookup"><span data-stu-id="26b8d-133">User trailers (user and system information)</span></span>  
  
- <span data-ttu-id="26b8d-134">システム トレーラー</span><span class="sxs-lookup"><span data-stu-id="26b8d-134">System trailers</span></span>  
  
  <span data-ttu-id="26b8d-135">テキスト ブロックの終了区切り記号は、「-}」です。</span><span class="sxs-lookup"><span data-stu-id="26b8d-135">The ending delimiter of the text block is "-}".</span></span> <span data-ttu-id="26b8d-136">トレーラーのブロックが始まる"{5:"です。</span><span class="sxs-lookup"><span data-stu-id="26b8d-136">The trailer block begins with "{5:".</span></span> <span data-ttu-id="26b8d-137">トレーラーのブロックの内容には、ユーザー情報 (チェックサム、メッセージの認証、独自の認証およびなど) とシステム情報 (遅延メッセージ、メッセージの参照、使用可能な重複するメッセージ、およびなど) の両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="26b8d-137">The contents of the trailer block include both user information (checksum, message authentication, proprietary authentication, and so on) and system information (delayed message, message reference, possible duplicate message, and so on).</span></span> <span data-ttu-id="26b8d-138">SWIFT によって追加されたトレーラーで区切られた、3 番目のブロックを提供も"{s:"です。</span><span class="sxs-lookup"><span data-stu-id="26b8d-138">Trailers added by SWIFT also provide a third block, delimited by "{S:".</span></span> <span data-ttu-id="26b8d-139">*SWIFT ユーザー向けハンドブック*、"FIN サービス Description"の下で詳しく説明します 5 のブロックの内容。</span><span class="sxs-lookup"><span data-stu-id="26b8d-139">The *SWIFT User Handbook*, under "FIN Service Description", describes in detail the contents of block 5.</span></span> <span data-ttu-id="26b8d-140">A4SWIFT が %s のブロックの内容を検証できません。</span><span class="sxs-lookup"><span data-stu-id="26b8d-140">A4SWIFT does not validate the contents of block S.</span></span>  
  
  <span data-ttu-id="26b8d-141">実際、FIN インターフェイスまたは SWIFT ネットワークは、トレーラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="26b8d-141">The actual FIN interface or the SWIFT network appends the trailers.</span></span> <span data-ttu-id="26b8d-142">メッセージにトレーラーが含まれるは、A4SWIFT メッセージを受信するとき、A4SWIFT は、メッセージのトレーラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="26b8d-142">If a message contains a trailer when A4SWIFT receives the message, A4SWIFT carries the trailer with the message.</span></span> <span data-ttu-id="26b8d-143">A4SWIFT では、A4SWIFT はメッセージを受信メッセージにトレーラーがない場合、エラーは発生しません。</span><span class="sxs-lookup"><span data-stu-id="26b8d-143">A4SWIFT does not raise an error if a message does not contain a trailer when A4SWIFT receives the message.</span></span> <span data-ttu-id="26b8d-144">として、ヘッダー付き自体には、ブロックをはじめ、トレーラーのエントリはすべて A4SWIFT では省略可能です。</span><span class="sxs-lookup"><span data-stu-id="26b8d-144">As with headers, all of the trailer entries, including the blocks themselves, are optional in A4SWIFT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26b8d-145">参照</span><span class="sxs-lookup"><span data-stu-id="26b8d-145">See Also</span></span>  
 [<span data-ttu-id="26b8d-146">スキーマの操作</span><span class="sxs-lookup"><span data-stu-id="26b8d-146">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)