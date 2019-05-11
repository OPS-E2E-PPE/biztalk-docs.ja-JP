---
title: プロジェクト項目の追加 |Microsoft Docs
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
ms.openlocfilehash: 0b0fc88bcf2f843e7d22b47a69ccae1b7b3fcd66
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360918"
---
# <a name="add-project-items"></a><span data-ttu-id="9b477-103">プロジェクト項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="9b477-103">Add Project Items</span></span>
<span data-ttu-id="9b477-104">BizTalk プロジェクト システムのコンテキストでは、プロジェクト項目は、マップやスキーマなど、構成されている項目です。</span><span class="sxs-lookup"><span data-stu-id="9b477-104">In the context of the BizTalk project system, a project item is a configured item, such as a map or schema.</span></span> <span data-ttu-id="9b477-105">BizTalk アプリケーションには、1 つまたは複数のオーケストレーション、スキーマ、マップ、およびパイプラインが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9b477-105">A BizTalk application might contain one or more orchestrations, schemas, maps, and pipelines.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b477-106">プロジェクトに項目を追加するときに、ピリオドは .NET 名前空間を区切るのため名にピリオド (.) を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="9b477-106">When you add an item to a project, do not use a period (.) in the name because a period is a separator for the .NET namespace.</span></span> <span data-ttu-id="9b477-107">項目名にピリオドを使用する場合、項目の型名にはピリオドの代わりにアンダー スコア (_) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9b477-107">If you use a period in the item name, the Type Name of the item will contain an underscore (_) instead of a period.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b477-108">フォルダーにスキーマ、マップ、またはパイプラインを追加すると、**完全修飾名**プロパティが自動的に生成し、名前空間と型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9b477-108">When you add a schema, map, or pipeline to a folder, the **Fully Qualified Name** property is automatically generated and includes the namespace and type.</span></span>  
  
## <a name="orchestrations"></a><span data-ttu-id="9b477-109">オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="9b477-109">Orchestrations</span></span>  
 <span data-ttu-id="9b477-110">オーケストレーションは、xlang/s 言語で表されるビジネス プロセスの表現です。</span><span class="sxs-lookup"><span data-stu-id="9b477-110">An orchestration is a representation of a business process expressed in the XLANG/s language.</span></span> <span data-ttu-id="9b477-111">XLANG/秒は、Microsoft などの既存の手続き型言語を補完するために使用できます[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)]と Microsoft[!INCLUDE[btsVBNet](../includes/btsvbnet-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9b477-111">XLANG/s can be used to complement existing procedural languages such as Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] and Microsoft [!INCLUDE[btsVBNet](../includes/btsvbnet-md.md)].</span></span>  
  
 <span data-ttu-id="9b477-112">オーケストレーション デザイナーを使用して、BizTalk プロジェクトに追加するオーケストレーションを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="9b477-112">You can use Orchestration Designer to create the orchestrations that you want to include in a BizTalk project.</span></span> <span data-ttu-id="9b477-113">オーケストレーション デザイナーで作成したすべてのオーケストレーションには、.odx ファイル拡張子があります。</span><span class="sxs-lookup"><span data-stu-id="9b477-113">All orchestrations that you create in Orchestration Designer have an .odx file extension.</span></span>  
  
## <a name="schemas"></a><span data-ttu-id="9b477-114">スキーマ</span><span class="sxs-lookup"><span data-stu-id="9b477-114">Schemas</span></span>  
 <span data-ttu-id="9b477-115">スキーマは、ドキュメントまたはメッセージの構造体の定義です。</span><span class="sxs-lookup"><span data-stu-id="9b477-115">A schema is the definition of the structure for a document or message.</span></span> <span data-ttu-id="9b477-116">レコードおよびフィールド構造内の関連プロパティ情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9b477-116">It contains property information as it pertains to the records and fields within the structure.</span></span> <span data-ttu-id="9b477-117">該当する場合は、スキーマは、複数のサブスキーマを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9b477-117">If appropriate, a schema can contain multiple subschemas.</span></span>  
  
 <span data-ttu-id="9b477-118">BizTalk エディターを使用して、インポート、編集、またはスキーマを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="9b477-118">You can use BizTalk Editor to import, edit, or create schemas.</span></span> <span data-ttu-id="9b477-119">BizTalk マッパーでマップを生成するために作成するスキーマを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b477-119">You can then use the schemas that you create to generate maps in BizTalk Mapper.</span></span> <span data-ttu-id="9b477-120">すべてのスキーマを BizTalk エディターを使用して保存するには、.xsd ファイル拡張子があります。</span><span class="sxs-lookup"><span data-stu-id="9b477-120">All schemas that you save by using BizTalk Editor have an .xsd file extension.</span></span>  
  
 <span data-ttu-id="9b477-121">スキーマと BizTalk エディターの詳細については、次を参照してください。 [BizTalk エディターを使用してスキーマを作成する](../core/creating-schemas-using-biztalk-editor.md)します。</span><span class="sxs-lookup"><span data-stu-id="9b477-121">For more information about schemas and BizTalk Editor, see [Creating Schemas Using BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md).</span></span>  
  
## <a name="maps"></a><span data-ttu-id="9b477-122">マップ</span><span class="sxs-lookup"><span data-stu-id="9b477-122">Maps</span></span>  
 <span data-ttu-id="9b477-123">マップとは別のスキーマのレコードとフィールドを 1 つのスキーマのレコードとフィールドの間の対応を定義する XML ファイル。</span><span class="sxs-lookup"><span data-stu-id="9b477-123">A map is an XML file that defines the correspondence between the records and fields in one schema and the records and fields in another schema.</span></span> <span data-ttu-id="9b477-124">業界標準、非業界標準 (内部標準や従来問題など)、または既存のファイルに基づくマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="9b477-124">You create maps based on industry standards, non-industry standards (such as internal standards or legacy issues), or existing files.</span></span> <span data-ttu-id="9b477-125">受信または別の 1 つの形式から送信されるデータを変換する場合に、マップを作成します。</span><span class="sxs-lookup"><span data-stu-id="9b477-125">You create maps when you want to transform data that you receive or send from one format to another.</span></span> <span data-ttu-id="9b477-126">BizTalk マッパーを使用すると、BizTalk プロジェクトに含めるマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="9b477-126">You can use BizTalk Mapper to create maps that you include in a BizTalk project.</span></span> <span data-ttu-id="9b477-127">BizTalk マッパーで保存するすべてのマップには、.btm ファイル拡張子が付いています。</span><span class="sxs-lookup"><span data-stu-id="9b477-127">All maps that you save in BizTalk Mapper have a .btm file extension.</span></span> <span data-ttu-id="9b477-128">BizTalk マッパーの詳細については、次を参照してください。 [BizTalk マッパーを使用してマップを作成する](../core/creating-maps-using-biztalk-mapper.md)します。</span><span class="sxs-lookup"><span data-stu-id="9b477-128">For more information about BizTalk Mapper, see [Creating Maps Using BizTalk Mapper](../core/creating-maps-using-biztalk-mapper.md).</span></span>  
  
## <a name="pipelines"></a><span data-ttu-id="9b477-129">パイプライン</span><span class="sxs-lookup"><span data-stu-id="9b477-129">Pipelines</span></span>  
 <span data-ttu-id="9b477-130">パイプライン デザイナーを使用して、作成する受信パイプラインと送信されます。</span><span class="sxs-lookup"><span data-stu-id="9b477-130">You can use Pipeline Designer to create receive and send pipelines.</span></span> <span data-ttu-id="9b477-131">パイプラインは、定義および BizTalk Server によって送信または受信したメッセージを処理するための 1 つまたは複数のステージをリンクするソフトウェア インフラストラクチャです。</span><span class="sxs-lookup"><span data-stu-id="9b477-131">A pipeline is a software infrastructure that defines and links one or more stages for processing messages received or sent by BizTalk Server.</span></span> <span data-ttu-id="9b477-132">パイプラインは、特定の順序で、ステージを実装し、エンコードまたはデコード、アセンブルや逆アセンブル、および暗号化または暗号化解除などの関数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9b477-132">The pipelines implement the stages in a specific order and include functions such as encoding or decoding, assembling or disassembling, and encrypting or decrypting.</span></span>  
  
 <span data-ttu-id="9b477-133">BizTalk プロジェクトに含まれる既定のパイプライン参照は、XML ドキュメントのみを処理できます。</span><span class="sxs-lookup"><span data-stu-id="9b477-133">The default pipeline references included in a BizTalk project can process only XML documents.</span></span> <span data-ttu-id="9b477-134">フラット ファイル、EDI ドキュメント、またはその他のファイルの種類を処理する場合は、に応じて新しいパイプラインを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b477-134">If you want to process flat files, EDI documents, or other file types, you must create new pipelines as appropriate.</span></span> <span data-ttu-id="9b477-135">パイプライン デザイナーで作成されたすべてのパイプラインには、.btp 拡張子が付いています。</span><span class="sxs-lookup"><span data-stu-id="9b477-135">All pipelines created with Pipeline Designer have a .btp extension.</span></span> <span data-ttu-id="9b477-136">パイプラインおよびパイプライン デザイナーの詳細については、次を参照してください。[パイプライン デザイナーを使用してパイプラインを作成](../core/creating-pipelines-using-pipeline-designer.md)です。</span><span class="sxs-lookup"><span data-stu-id="9b477-136">For more information about pipelines and Pipeline Designer, see [Creating Pipelines Using Pipeline Designer](../core/creating-pipelines-using-pipeline-designer.md).</span></span>  
  
## <a name="valid-files-for-biztalk-projects"></a><span data-ttu-id="9b477-137">BizTalk プロジェクトの有効なファイル</span><span class="sxs-lookup"><span data-stu-id="9b477-137">Valid Files for BizTalk Projects</span></span>  
 <span data-ttu-id="9b477-138">BizTalk プロジェクトを使用する場合は、HTML ファイル、XML ファイルの場合は、受信パイプライン ファイル、およびスキーマ ファイルなど、多数の異なるファイルを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9b477-138">When you work with a BizTalk project, you can include many different files, such as HTML files, XML files, receive pipeline files, and schema files.</span></span> <span data-ttu-id="9b477-139">BizTalk Server では、Visual Studio のビルド システムでサポートされている任意のオブジェクトが、アセンブリに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9b477-139">With BizTalk Server, the assembly can contain any object supported by the Visual Studio build system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b477-140">参照</span><span class="sxs-lookup"><span data-stu-id="9b477-140">See Also</span></span>  
 [<span data-ttu-id="9b477-141">BizTalk プロジェクトの操作</span><span class="sxs-lookup"><span data-stu-id="9b477-141">Working with BizTalk Projects</span></span>](../core/working-with-biztalk-projects.md)