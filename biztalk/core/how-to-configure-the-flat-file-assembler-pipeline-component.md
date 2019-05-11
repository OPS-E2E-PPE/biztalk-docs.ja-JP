---
title: フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, Flat File Assembler
- Flat File Assembler [pipeline component], configuring
- messages, flat files
ms.assetid: 5af61bba-4eb2-4bb9-a655-394a76d08d3b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0db8ce0e52ec4dfc5368f172747dc51ef7704626
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340875"
---
# <a name="how-to-configure-the-flat-file-assembler-pipeline-component"></a><span data-ttu-id="a2e03-102">フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="a2e03-102">How to Configure the Flat File Assembler Pipeline Component</span></span>
<span data-ttu-id="a2e03-103">フラット ファイル アセンブラー パイプライン コンポーネントは、XML ドキュメントをサーバーから送信する前に区切り文字/位置指定フラット ファイル形式にシリアル化に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2e03-103">The Flat File Assembler pipeline component is used to serialize an XML document into delimited or positional flat file format before sending it out of the server.</span></span>  
  
### <a name="to-configure-the-properties-for-the-flat-file-assembler-pipeline-component"></a><span data-ttu-id="a2e03-104">フラット ファイル アセンブラー パイプライン コンポーネントのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="a2e03-104">To configure the properties for the Flat File Assembler pipeline component</span></span>  
  
1.  <span data-ttu-id="a2e03-105">フラット ファイル アセンブラー パイプライン コンポーネントは、送信パイプラインのアセンブル ステージにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a2e03-105">Drag the Flat File Assembler pipeline component into the Assemble stage of the send pipeline.</span></span>  
  
2.  <span data-ttu-id="a2e03-106">[プロパティ] ウィンドウでの**パイプライン コンポーネントのプロパティ**セクションで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a2e03-106">In the Properties window, in the **Pipeline Component Properties** section, do the following.</span></span>  
  
    |<span data-ttu-id="a2e03-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a2e03-107">Use this</span></span>|<span data-ttu-id="a2e03-108">目的</span><span class="sxs-lookup"><span data-stu-id="a2e03-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a2e03-109">**ドキュメント スキーマ**</span><span class="sxs-lookup"><span data-stu-id="a2e03-109">**Document schema**</span></span>|<span data-ttu-id="a2e03-110">XML からフラット ファイル形式へのメッセージをシリアル化するために使用するフラット ファイル ドキュメント スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="a2e03-110">Select a flat file document schema to use for serializing the message from XML to the flat file format.</span></span> <span data-ttu-id="a2e03-111">スキーマが指定されていない場合は、実行時のスキーマの検出が行われます。</span><span class="sxs-lookup"><span data-stu-id="a2e03-111">If no schema is specified, run-time schema discovery is done.</span></span> <span data-ttu-id="a2e03-112">BizTalk エディターでフラット ファイル ドキュメント スキーマを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="a2e03-112">You can create the flat file document schema in BizTalk Editor.</span></span><br /><br /> <span data-ttu-id="a2e03-113">既定値:なし</span><span class="sxs-lookup"><span data-stu-id="a2e03-113">Default value: None</span></span>|  
    |<span data-ttu-id="a2e03-114">**ヘッダー スキーマ**</span><span class="sxs-lookup"><span data-stu-id="a2e03-114">**Header schema**</span></span>|<span data-ttu-id="a2e03-115">フラット ファイル メッセージのヘッダー部のスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="a2e03-115">Select a schema for the header part of the flat file message.</span></span> <span data-ttu-id="a2e03-116">ヘッダー スキーマは、という名前のメッセージ コンテキスト プロパティで指定することも**HeaderSpecName** xmlnorm 名前空間の下。</span><span class="sxs-lookup"><span data-stu-id="a2e03-116">A header schema can also be specified in the message context property named **HeaderSpecName** under the xmlnorm namespace.</span></span> <span data-ttu-id="a2e03-117">この場合、パイプライン デザイナーで指定されたヘッダー スキーマが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="a2e03-117">In this case, it will override the header schema specified in Pipeline Designer.</span></span><br /><br /> <span data-ttu-id="a2e03-118">BizTalk エディターでフラット ファイル メッセージのヘッダー部のスキーマを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a2e03-118">You can create the schema for the header part of the flat file message with BizTalk Editor.</span></span><br /><br /> <span data-ttu-id="a2e03-119">既定値:なし</span><span class="sxs-lookup"><span data-stu-id="a2e03-119">Default value: None</span></span>|  
    |<span data-ttu-id="a2e03-120">**バイト オーダー マークを保存します。**</span><span class="sxs-lookup"><span data-stu-id="a2e03-120">**Preserve byte order mark**</span></span>|<span data-ttu-id="a2e03-121">かどうか、バイトを追加するオーダー マーク (BOM) アセンブラー コンポーネントによって生成されたドキュメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2e03-121">Specifies whether to add a byte order mark (BOM) to the document produced by the assembler component.</span></span><br /><br /> <span data-ttu-id="a2e03-122">既定値:**False**</span><span class="sxs-lookup"><span data-stu-id="a2e03-122">Default Value: **False**</span></span>|  
    |<span data-ttu-id="a2e03-123">**ターゲット文字セット**</span><span class="sxs-lookup"><span data-stu-id="a2e03-123">**Target charset**</span></span>|<span data-ttu-id="a2e03-124">送信メッセージのエンコードに使用されるターゲット文字セットを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2e03-124">Specifies the target character set used for encoding of outgoing messages.</span></span><br /><br /> <span data-ttu-id="a2e03-125">既定値:なし</span><span class="sxs-lookup"><span data-stu-id="a2e03-125">Default value: None</span></span>|  
    |<span data-ttu-id="a2e03-126">**トレーラー スキーマ**</span><span class="sxs-lookup"><span data-stu-id="a2e03-126">**Trailer schema**</span></span>|<span data-ttu-id="a2e03-127">フラット ファイル メッセージのトレーラー部のスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="a2e03-127">Select a schema for the trailer part of the flat file message.</span></span> <span data-ttu-id="a2e03-128">BizTalk エディターでフラット ファイル メッセージのトレーラー部のスキーマを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="a2e03-128">You can create the schema for the trailer part of the flat file message in BizTalk Editor.</span></span><br /><br /> <span data-ttu-id="a2e03-129">既定値:なし</span><span class="sxs-lookup"><span data-stu-id="a2e03-129">Default value: None</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a2e03-130">参照</span><span class="sxs-lookup"><span data-stu-id="a2e03-130">See Also</span></span>  
 <span data-ttu-id="a2e03-131">[フラット ファイル アセンブラー パイプライン コンポーネント](../core/flat-file-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="a2e03-131">[Flat File Assembler Pipeline Component](../core/flat-file-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="a2e03-132">[ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="a2e03-132">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 <span data-ttu-id="a2e03-133">[XML とフラット ファイル プロパティ スキーマおよびプロパティ](../core/xml-and-flat-file-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="a2e03-133">[XML and Flat File Property Schema and Properties](../core/xml-and-flat-file-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="a2e03-134">Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="a2e03-134">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)