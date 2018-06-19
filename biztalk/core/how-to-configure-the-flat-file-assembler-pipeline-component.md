---
title: フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 7fe9c7a0720db68d8e629410dd3f0a443a99d7a4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248634"
---
# <a name="how-to-configure-the-flat-file-assembler-pipeline-component"></a><span data-ttu-id="ec921-102">フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="ec921-102">How to Configure the Flat File Assembler Pipeline Component</span></span>
<span data-ttu-id="ec921-103">フラット ファイル アセンブラー パイプライン コンポーネントは、XML ドキュメントがサーバーから送信される前に、このドキュメントを区切り記号付きフラット ファイル形式または位置指定フラット ファイル形式にシリアル化する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ec921-103">The Flat File Assembler pipeline component is used to serialize an XML document into delimited or positional flat file format before sending it out of the server.</span></span>  
  
### <a name="to-configure-the-properties-for-the-flat-file-assembler-pipeline-component"></a><span data-ttu-id="ec921-104">フラット ファイル アセンブラー パイプライン コンポーネントのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="ec921-104">To configure the properties for the Flat File Assembler pipeline component</span></span>  
  
1.  <span data-ttu-id="ec921-105">フラット ファイル アセンブラー パイプライン コンポーネントを、送信パイプラインのアセンブル ステージにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ec921-105">Drag the Flat File Assembler pipeline component into the Assemble stage of the send pipeline.</span></span>  
  
2.  <span data-ttu-id="ec921-106">[プロパティ] ウィンドウでの**パイプライン コンポーネントのプロパティ**セクションで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ec921-106">In the Properties window, in the **Pipeline Component Properties** section, do the following.</span></span>  
  
    |<span data-ttu-id="ec921-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ec921-107">Use this</span></span>|<span data-ttu-id="ec921-108">目的</span><span class="sxs-lookup"><span data-stu-id="ec921-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ec921-109">**ドキュメント スキーマ**</span><span class="sxs-lookup"><span data-stu-id="ec921-109">**Document schema**</span></span>|<span data-ttu-id="ec921-110">XML 形式からフラット ファイル形式へのメッセージのシリアル化に使用するフラット ファイルのドキュメント スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="ec921-110">Select a flat file document schema to use for serializing the message from XML to the flat file format.</span></span> <span data-ttu-id="ec921-111">スキーマを指定しない場合、実行時にスキーマ探索が行われます。</span><span class="sxs-lookup"><span data-stu-id="ec921-111">If no schema is specified, run-time schema discovery is done.</span></span> <span data-ttu-id="ec921-112">フラット ファイル ドキュメント スキーマは、BizTalk エディターで作成できます。</span><span class="sxs-lookup"><span data-stu-id="ec921-112">You can create the flat file document schema in BizTalk Editor.</span></span><br /><br /> <span data-ttu-id="ec921-113">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="ec921-113">Default value: None</span></span>|  
    |<span data-ttu-id="ec921-114">**ヘッダー スキーマ**</span><span class="sxs-lookup"><span data-stu-id="ec921-114">**Header schema**</span></span>|<span data-ttu-id="ec921-115">フラット ファイル メッセージのヘッダー部のスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="ec921-115">Select a schema for the header part of the flat file message.</span></span> <span data-ttu-id="ec921-116">ヘッダー スキーマは、という名前のメッセージ コンテキスト プロパティで指定することも**HeaderSpecName** xmlnorm 名前空間の下。</span><span class="sxs-lookup"><span data-stu-id="ec921-116">A header schema can also be specified in the message context property named **HeaderSpecName** under the xmlnorm namespace.</span></span> <span data-ttu-id="ec921-117">この場合、パイプライン デザイナーで指定されたヘッダー スキーマは無視されます。</span><span class="sxs-lookup"><span data-stu-id="ec921-117">In this case, it will override the header schema specified in Pipeline Designer.</span></span><br /><br /> <span data-ttu-id="ec921-118">フラット ファイル メッセージのヘッダー部のスキーマは、BizTalk エディターで作成できます。</span><span class="sxs-lookup"><span data-stu-id="ec921-118">You can create the schema for the header part of the flat file message with BizTalk Editor.</span></span><br /><br /> <span data-ttu-id="ec921-119">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="ec921-119">Default value: None</span></span>|  
    |<span data-ttu-id="ec921-120">**バイト オーダー マークを保存します。**</span><span class="sxs-lookup"><span data-stu-id="ec921-120">**Preserve byte order mark**</span></span>|<span data-ttu-id="ec921-121">かどうかをバイトを追加するオーダー マーク (BOM)、アセンブラー コンポーネントによって生成されたドキュメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="ec921-121">Specifies whether to add a byte order mark (BOM) to the document produced by the assembler component.</span></span><br /><br /> <span data-ttu-id="ec921-122">既定値: **False**</span><span class="sxs-lookup"><span data-stu-id="ec921-122">Default Value: **False**</span></span>|  
    |<span data-ttu-id="ec921-123">**ターゲット文字セット**</span><span class="sxs-lookup"><span data-stu-id="ec921-123">**Target charset**</span></span>|<span data-ttu-id="ec921-124">送信メッセージのエンコードに使用されるターゲット文字セットを指定します。</span><span class="sxs-lookup"><span data-stu-id="ec921-124">Specifies the target character set used for encoding of outgoing messages.</span></span><br /><br /> <span data-ttu-id="ec921-125">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="ec921-125">Default value: None</span></span>|  
    |<span data-ttu-id="ec921-126">**トレーラー スキーマ**</span><span class="sxs-lookup"><span data-stu-id="ec921-126">**Trailer schema**</span></span>|<span data-ttu-id="ec921-127">フラット ファイル メッセージのトレーラー部のスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="ec921-127">Select a schema for the trailer part of the flat file message.</span></span> <span data-ttu-id="ec921-128">BizTalk エディターでフラット ファイル メッセージのトレーラー部のスキーマを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ec921-128">You can create the schema for the trailer part of the flat file message in BizTalk Editor.</span></span><br /><br /> <span data-ttu-id="ec921-129">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="ec921-129">Default value: None</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec921-130">参照</span><span class="sxs-lookup"><span data-stu-id="ec921-130">See Also</span></span>  
 <span data-ttu-id="ec921-131">[フラット ファイル アセンブラー パイプライン コンポーネント](../core/flat-file-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="ec921-131">[Flat File Assembler Pipeline Component](../core/flat-file-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="ec921-132">[ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="ec921-132">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 <span data-ttu-id="ec921-133">[XML とフラット ファイル プロパティ スキーマおよびプロパティ](../core/xml-and-flat-file-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="ec921-133">[XML and Flat File Property Schema and Properties](../core/xml-and-flat-file-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="ec921-134">パイプライン AssemblerDisassembler (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="ec921-134">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)