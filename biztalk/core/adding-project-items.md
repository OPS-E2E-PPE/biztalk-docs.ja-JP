---
title: プロジェクト項目の追加 |Microsoft ドキュメント
description: オーケストレーション、スキーマ、マップ、およびパイプラインを Visual Studio で BizTalk Server プロジェクトに追加します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1b922d5-8ece-4e1a-a390-e6ae1222665a
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef998865a1851e546a3648b60e0141b3cd137c1b
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710225"
---
# <a name="add-project-items"></a><span data-ttu-id="e3e1d-103">プロジェクト項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-103">Add Project Items</span></span>
<span data-ttu-id="e3e1d-104">BizTalk プロジェクト システムのコンテキストでは、プロジェクト項目は構成済みの項目のことであり、マップやスキーマなどがあります。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-104">In the context of the BizTalk project system, a project item is a configured item, such as a map or schema.</span></span> <span data-ttu-id="e3e1d-105">BizTalk アプリケーションには、1 つ以上のオーケストレーション、スキーマ、マップ、およびパイプラインを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-105">A BizTalk application might contain one or more orchestrations, schemas, maps, and pipelines.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3e1d-106">項目をプロジェクトに追加する場合は、名前にピリオド (.) を使用しないでください。ピリオドは .NET 名前空間の区切り記号であるためです。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-106">When you add an item to a project, do not use a period (.) in the name because a period is a separator for the .NET namespace.</span></span> <span data-ttu-id="e3e1d-107">項目名にピリオドを使用すると、項目の型名にピリオドの代わりにアンダースコア (_) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-107">If you use a period in the item name, the Type Name of the item will contain an underscore (_) instead of a period.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3e1d-108">スキーマ、マップ、またはパイプラインをフォルダーに追加すると、 **完全修飾名** プロパティが自動的に生成し、名前空間と型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-108">When you add a schema, map, or pipeline to a folder, the **Fully Qualified Name** property is automatically generated and includes the namespace and type.</span></span>  
  
## <a name="orchestrations"></a><span data-ttu-id="e3e1d-109">オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="e3e1d-109">Orchestrations</span></span>  
 <span data-ttu-id="e3e1d-110">オーケストレーションとは、XLANG/s 言語で表現されたビジネス プロセスを表すものです。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-110">An orchestration is a representation of a business process expressed in the XLANG/s language.</span></span> <span data-ttu-id="e3e1d-111">XLANG/s は、既存の手続き型言語 (Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] や Microsoft [!INCLUDE[btsVBNet](../includes/btsvbnet-md.md)] など) を補完するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-111">XLANG/s can be used to complement existing procedural languages such as Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] and Microsoft [!INCLUDE[btsVBNet](../includes/btsvbnet-md.md)].</span></span>  
  
 <span data-ttu-id="e3e1d-112">オーケストレーション デザイナーを使用すると、BizTalk に含めるオーケストレーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-112">You can use Orchestration Designer to create the orchestrations that you want to include in a BizTalk project.</span></span> <span data-ttu-id="e3e1d-113">オーケストレーション デザイナーで作成したすべてのオーケストレーションには、.odx ファイル拡張子が付きます。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-113">All orchestrations that you create in Orchestration Designer have an .odx file extension.</span></span>  
  
## <a name="schemas"></a><span data-ttu-id="e3e1d-114">スキーマ</span><span class="sxs-lookup"><span data-stu-id="e3e1d-114">Schemas</span></span>  
 <span data-ttu-id="e3e1d-115">スキーマとは、ドキュメントまたはメッセージの構造の定義です。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-115">A schema is the definition of the structure for a document or message.</span></span> <span data-ttu-id="e3e1d-116">構造内のレコードおよびフィールドに関連するプロパティ情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-116">It contains property information as it pertains to the records and fields within the structure.</span></span> <span data-ttu-id="e3e1d-117">必要に応じて、スキーマには複数のサブスキーマを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-117">If appropriate, a schema can contain multiple subschemas.</span></span>  
  
 <span data-ttu-id="e3e1d-118">BizTalk エディターを使用して、スキーマをインポート、編集、または作成できます。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-118">You can use BizTalk Editor to import, edit, or create schemas.</span></span> <span data-ttu-id="e3e1d-119">作成したスキーマを使用して、BizTalk マッパーでマップを生成できます。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-119">You can then use the schemas that you create to generate maps in BizTalk Mapper.</span></span> <span data-ttu-id="e3e1d-120">BizTalk エディターで保存したすべてのスキーマには、.xsd ファイル拡張子が付きます。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-120">All schemas that you save by using BizTalk Editor have an .xsd file extension.</span></span>  
  
 <span data-ttu-id="e3e1d-121">スキーマと BizTalk エディターの詳細については、次を参照してください。 [BizTalk エディターを使用してスキーマを作成する](../core/creating-schemas-using-biztalk-editor.md)です。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-121">For more information about schemas and BizTalk Editor, see [Creating Schemas Using BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md).</span></span>  
  
## <a name="maps"></a><span data-ttu-id="e3e1d-122">マップ</span><span class="sxs-lookup"><span data-stu-id="e3e1d-122">Maps</span></span>  
 <span data-ttu-id="e3e1d-123">マップとは、あるスキーマと別のスキーマのレコードおよびフィールドの対応関係を定義した XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-123">A map is an XML file that defines the correspondence between the records and fields in one schema and the records and fields in another schema.</span></span> <span data-ttu-id="e3e1d-124">業界標準、非業界標準 (内部標準や従来の問題など)、または既存のファイルに基づいてマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-124">You create maps based on industry standards, non-industry standards (such as internal standards or legacy issues), or existing files.</span></span> <span data-ttu-id="e3e1d-125">受信または送信するデータを 1 つの形式から別の形式に変換する場合に、マップを作成します。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-125">You create maps when you want to transform data that you receive or send from one format to another.</span></span> <span data-ttu-id="e3e1d-126">BizTalk マッパーを使用して、BizTalk プロジェクトに含めるマップを生成できます。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-126">You can use BizTalk Mapper to create maps that you include in a BizTalk project.</span></span> <span data-ttu-id="e3e1d-127">BizTalk マッパーで保存したすべてのマップには、.btm ファイル拡張子が付きます。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-127">All maps that you save in BizTalk Mapper have a .btm file extension.</span></span> <span data-ttu-id="e3e1d-128">BizTalk マッパーの詳細については、次を参照してください。 [BizTalk マッパーを使用してマップを作成する](../core/creating-maps-using-biztalk-mapper.md)です。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-128">For more information about BizTalk Mapper, see [Creating Maps Using BizTalk Mapper](../core/creating-maps-using-biztalk-mapper.md).</span></span>  
  
## <a name="pipelines"></a><span data-ttu-id="e3e1d-129">パイプライン</span><span class="sxs-lookup"><span data-stu-id="e3e1d-129">Pipelines</span></span>  
 <span data-ttu-id="e3e1d-130">パイプライン デザイナーを使用して、受信および送信パイプラインを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-130">You can use Pipeline Designer to create receive and send pipelines.</span></span> <span data-ttu-id="e3e1d-131">パイプラインを定義および BizTalk Server によって送信または受信したメッセージを処理するための 1 つまたは複数のステージをリンクするソフトウェア インフラストラクチャです。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-131">A pipeline is a software infrastructure that defines and links one or more stages for processing messages received or sent by BizTalk Server.</span></span> <span data-ttu-id="e3e1d-132">パイプラインには、複数のステージが特定の順序で実装され、エンコードやデコード、アセンブルや逆アセンブル、暗号化や復号化などの機能が取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-132">The pipelines implement the stages in a specific order and include functions such as encoding or decoding, assembling or disassembling, and encrypting or decrypting.</span></span>  
  
 <span data-ttu-id="e3e1d-133">BizTalk プロジェクトに含まれる既定のパイプライン参照は、XML ドキュメントのみを処理できます。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-133">The default pipeline references included in a BizTalk project can process only XML documents.</span></span> <span data-ttu-id="e3e1d-134">フラット ファイル、EDI ドキュメント、またはその他の種類のファイルを処理する場合、必要に応じて新しいパイプラインを作成してください。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-134">If you want to process flat files, EDI documents, or other file types, you must create new pipelines as appropriate.</span></span> <span data-ttu-id="e3e1d-135">パイプライン デザイナーで作成されたすべてのパイプラインには、.btp 拡張子が付きます。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-135">All pipelines created with Pipeline Designer have a .btp extension.</span></span> <span data-ttu-id="e3e1d-136">パイプラインおよびパイプライン デザイナーの詳細については、次を参照してください。[パイプライン デザイナーを使用してパイプラインを作成する](../core/creating-pipelines-using-pipeline-designer.md)です。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-136">For more information about pipelines and Pipeline Designer, see [Creating Pipelines Using Pipeline Designer](../core/creating-pipelines-using-pipeline-designer.md).</span></span>  
  
## <a name="valid-files-for-biztalk-projects"></a><span data-ttu-id="e3e1d-137">BizTalk プロジェクトの有効なファイル</span><span class="sxs-lookup"><span data-stu-id="e3e1d-137">Valid Files for BizTalk Projects</span></span>  
 <span data-ttu-id="e3e1d-138">BizTalk プロジェクトで作業する場合、HTML ファイル、XML ファイル、受信パイプライン ファイル、スキーマ ファイルなど、多数の異なるファイルを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-138">When you work with a BizTalk project, you can include many different files, such as HTML files, XML files, receive pipeline files, and schema files.</span></span> <span data-ttu-id="e3e1d-139">BizTalk Server アセンブリは、Visual Studio のビルド システムでサポートされている任意のオブジェクトを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e3e1d-139">With BizTalk Server, the assembly can contain any object supported by the Visual Studio build system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3e1d-140">参照</span><span class="sxs-lookup"><span data-stu-id="e3e1d-140">See Also</span></span>  
 [<span data-ttu-id="e3e1d-141">BizTalk プロジェクトでの作業</span><span class="sxs-lookup"><span data-stu-id="e3e1d-141">Working with BizTalk Projects</span></span>](../core/working-with-biztalk-projects.md)