---
title: パイプライン コンポーネントのスキーマの解決 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, schema resolution
- pipeline components, schema resolution
- schemas, pipeline components
ms.assetid: 35a79a6f-788b-4ca1-8483-36dcba5ae580
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9eebb3e1cb4c33d49bacb1353ada164932dae003
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396921"
---
# <a name="schema-resolution-in-pipeline-components"></a><span data-ttu-id="b1f0f-102">パイプライン コンポーネントのスキーマの解決</span><span class="sxs-lookup"><span data-stu-id="b1f0f-102">Schema Resolution in Pipeline Components</span></span>
<span data-ttu-id="b1f0f-103">パイプラインの逆アセンブラーおよびアセンブラー コンポーネントでは、XSD スキーマを使用して、メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-103">Pipeline disassembler and assembler components use XSD schemas to process messages.</span></span> <span data-ttu-id="b1f0f-104">スキーマには、昇格させたプロパティ、識別フィールド、フラット ファイル メッセージでは、注釈、および XML エンベロープの注釈の一覧などの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-104">The schemas contain information such as the list of promoted properties, distinguished fields, annotations for flat file messages, and annotations for XML envelopes.</span></span>  
  
 <span data-ttu-id="b1f0f-105">標準の逆アセンブラーおよびアセンブラー コンポーネントは、スキーマの型名とメッセージ型を使用して展開されたスキーマの取得をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-105">Standard disassembler and assembler components support retrieval of deployed schemas by using the schema type name and message type.</span></span> <span data-ttu-id="b1f0f-106">一部のコンポーネントは、スキーマの種類でのみ他のユーザー (たとえば、フラット ファイル逆アセンブラー) を取得中に、スキーマの型名と、メッセージの種類の両方を使用して取得します。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-106">Some components retrieve by using both the schema type name and the message type, while others (for example, the Flat File Disassembler) retrieve only by the schema type.</span></span>  
  
 <span data-ttu-id="b1f0f-107">XML メッセージを取得するパイプライン コンポーネントは、メッセージのルート要素および名前空間を調べて、メッセージの種類を判別します。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-107">Pipeline components that receive XML messages determine the message type by examining the message root element and namespace.</span></span> <span data-ttu-id="b1f0f-108">たとえば、次の XML のメッセージの種類は "<http://MyDocument.org#MyDocument>" 。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-108">For example, the message type for the following XML is "<http://MyDocument.org#MyDocument>".</span></span>  
  
```  
<ns0:MyDocument xmlns:ns0="http://MyDocument.org">  
  
</ns0:MyDocument>  
```  
  
 <span data-ttu-id="b1f0f-109">スキーマが定義された名前空間を持たない場合、メッセージの種類は、"\<**rootNode**\>"。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-109">If a schema does not have a namespace defined for it, the message type is "\<**rootNode**\>".</span></span> <span data-ttu-id="b1f0f-110">たとえば、上記の XML が名前空間を持たない場合、メッセージの種類は、"MyDocument"をなります。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-110">For example, if the preceding example XML had no namespace, the message type would be "MyDocument".</span></span>  
  
 <span data-ttu-id="b1f0f-111">標準のパイプライン コンポーネントでは、メッセージの種類を使用して、データベースから適切なスキーマを取得します。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-111">Standard pipeline components use the message type to retrieve the appropriate schema from the database.</span></span> <span data-ttu-id="b1f0f-112">既定の XML の受信し、送信パイプラインが常に動的にメッセージの種類を使用して、読み込むスキーマを検出時に、メッセージから XML コンテンツ (ただし、パイプライン コンポーネントは認識されないメッセージを許可する設定) を決定します。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-112">Default XML receive and send pipelines always determine which schema to load by using the message type dynamically discovered at runtime from the message XML content (unless the pipeline component is set to allow unrecognized messages).</span></span> <span data-ttu-id="b1f0f-113">XML 逆アセンブラーは、このメカニズムでは; を使用してメッセージ エンベロープを削除できます。ただし、XML アセンブラーを使用するエンベロープ スキーマを知らなくても、送信メッセージのエンベロープを作成できません。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-113">The XML Disassembler can remove the message envelope by using this mechanism; however, the XML Assembler cannot create an envelope for an outgoing message without knowing what envelope schema to use.</span></span>  
  
 <span data-ttu-id="b1f0f-114">パイプライン デザイナーから、XML アセンブラーの構成のプロパティでエンベロープ スキーマを指定します。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-114">You specify the envelope schema in the configuration properties for the XML Assembler from within the pipeline designer.</span></span>  
  
## <a name="how-schemas-are-resolved"></a><span data-ttu-id="b1f0f-115">スキーマの解決方法</span><span class="sxs-lookup"><span data-stu-id="b1f0f-115">How Schemas Are Resolved</span></span>  
 <span data-ttu-id="b1f0f-116">XmlDisassembler で直接スキーマが指定されていないと仮定すると、スキーマは、次のように解決されます。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-116">Assuming you are not specifying the schema directly in the XmlDisassembler, schemas will be resolved in the following manner:</span></span>  
  
1. <span data-ttu-id="b1f0f-117">最初に、展開されたスキーマで修飾されていない検索されるルート ノード名と名前空間を使用して (たとえば、 http://MyNamespace#MyRoot)します。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-117">First, an unqualified search on the deployed schemas is made using the root node name and namespace (for example, http://MyNamespace#MyRoot).</span></span> <span data-ttu-id="b1f0f-118">一意の一致には、スキーマが見つかった場合は解決されます。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-118">If a unique match is found the schema is resolved.</span></span> <span data-ttu-id="b1f0f-119">複数の一致が見られますが、バージョン番号のみが異なる 1 つだけがアクティブな場合は、そのバージョンを使用し、スキーマは解決されます。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-119">If multiple matches are found and differ only by version number and only one is active, that version is used and the schema is resolved.</span></span> <span data-ttu-id="b1f0f-120">同じスキーマが複数のアプリケーションでアクティブな場合は、複数のアクティブなスキーマが検出され、検索は次のステップ 2 に進みます。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-120">If the same schema is active in multiple applications, multiple active schemas will be found and the search will continue with step 2 below.</span></span>  
  
2. <span data-ttu-id="b1f0f-121">手順 1 の複数の一致を解決できない場合は、検索は、アセンブリで、パイプラインの実行によって修飾されます。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-121">If there are multiple matches that step 1 cannot resolve, the search is qualified by the assembly the pipeline is executing in.</span></span> <span data-ttu-id="b1f0f-122">一意のスキーマが同じアセンブリ内で見つかった場合、パイプラインを実行し、スキーマは解決されます。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-122">If a unique schema is found within the same assembly the pipeline is executing in, then the schema is resolved.</span></span>  
  
3. <span data-ttu-id="b1f0f-123">ない場合でも、一致するスキーマを解決するのには、パブリッシャーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-123">If there are still no matches, then the publisher is used to resolve the schema.</span></span> <span data-ttu-id="b1f0f-124">検索は、ルート ノード、名前空間、および公開キー トークンを使用して絞り込まれます。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-124">The search is narrowed by using the root node, namespace, and public key token.</span></span> <span data-ttu-id="b1f0f-125">この検索を使用して一意のスキーマが見つかった場合、スキーマは解決されます。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-125">If a unique schema is found using this search, the schema is resolved.</span></span>  
  
4. <span data-ttu-id="b1f0f-126">スキーマを解決できません。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-126">Schema cannot be resolved.</span></span> <span data-ttu-id="b1f0f-127">注目する一意のスキーマが見つからない場合、エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-127">An error is returned noting that no unique schema can be found.</span></span>  
  
   <span data-ttu-id="b1f0f-128">スキーマの解決には、SQL Server 照合順序の大文字小文字の区別の影響を含むその他の考慮事項を参照してください。 [Namespace 管理](../core/namespace-management.md)します。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-128">For other considerations including the effect of SQL Server collation and case-sensitivity on schema resolution, see [Namespace Management](../core/namespace-management.md).</span></span>  
  
   <span data-ttu-id="b1f0f-129">XML アセンブラーまたはヘッダーとトレーラーをフラット ファイル アセンブラーのエンベロープを作成するには、次のいずれかを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-129">To create an envelope in the XML Assembler or a header and trailer in the Flat File Assembler, you may do one of the following:</span></span>  
  
- <span data-ttu-id="b1f0f-130">カスタム送信パイプラインを作成し、構成プロパティで、XML アセンブラーのエンベロープのスキーマを指定します。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-130">Create a custom send pipeline and specify the schemas for the envelope in the configuration properties for the XML Assembler.</span></span> <span data-ttu-id="b1f0f-131">これについては、パイプライン デザイナーからを行います。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-131">This is done from within the pipeline designer.</span></span>  
  
- <span data-ttu-id="b1f0f-132">BizTalk Server 管理コンソールでは、送信ポートで送信パイプライン プロパティに XMLTransmit を指定します。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-132">In the BizTalk Server Administration console specify XMLTransmit for the Send pipeline property on a send port.</span></span> <span data-ttu-id="b1f0f-133">パイプラインのプロパティを構成し、EnvelopeDocSpecNames プロパティのエンベロープのスキーマを指定する省略記号をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-133">Click the ellipsis to configure the pipeline properties and specify the schema for the envelope in the EnvelopeDocSpecNames property.</span></span>  
  
  <span data-ttu-id="b1f0f-134">展開する場合、同じスキーマの複数のバージョンは意図的にまたは誤って (サイド バイ サイドで配置の例では、または複数のシナリオには一意のメッセージの種類がないかどうか) 用のデータベースで、メッセージの種類によるスキーマ解決は機能しません。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-134">Schema resolution by message type may not work if several versions of the same schema are intentionally or accidentally deployed in the database (for example, in a side-by-side deployment or if multiple scenarios do not have unique message types).</span></span> <span data-ttu-id="b1f0f-135">メッセージの種類によるスキーマ解決が失敗した場合は、「スキーマのあいまいさ」エラーがイベント ログに追加されます。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-135">If schema resolution by message type fails, a "schema ambiguity" error is added to the event log.</span></span> <span data-ttu-id="b1f0f-136">メッセージの種類によるスキーマ解決が成功したことを確認するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-136">To ensure that schema resolution by message type succeeds, do one of the following:</span></span>  
  
- <span data-ttu-id="b1f0f-137">カスタム パイプラインと同じ BizTalk プロジェクト内のスキーマを定義します。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-137">Define the schemas in the same BizTalk project as your custom pipeline.</span></span>  
  
- <span data-ttu-id="b1f0f-138">パイプラインを含むアセンブリと同じキーで、スキーマを使用したアセンブリに署名します。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-138">Sign the assembly with the schemas with the same key as the assembly containing the pipelines.</span></span>  
  
- <span data-ttu-id="b1f0f-139">(メッセージ型の名前は一意である BizTalk 管理データベース) のパイプライン コンポーネントで、スキーマを明示的に指定します。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-139">Explicitly specify schemas in pipeline components (message type names should be unique across the BizTalk Management database).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b1f0f-140">あいまいさの解決の制限により、同じパイプライン コンポーネント アセンブリ内のスキーマを含める必要がありますいない、同じアセンブリ内のスキーマは、メッセージの種類を共有する場合代わりに、パイプライン コンポーネント アセンブリの外部スキーマを参照します。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-140">When schemas in the same assembly share a message type, you must not include the schemas in the same pipeline component assembly due to the limitations of ambiguity resolution; instead, reference schemas that are external to the pipeline component assembly.</span></span> <span data-ttu-id="b1f0f-141">あいまいさの解決は機能しませんスキーマとパイプライン コンポーネントが、同じアセンブリでは、カスタム パイプラインのパイプライン コンポーネントのスキーマの種類名が明示的に指定されている場合でも。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-141">Ambiguity resolution does not work when schemas and pipeline components are in the same assembly, even if schema type names are explicitly specified in pipeline components in custom pipelines.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1f0f-142">使用するカスタム パイプライン コンポーネント**IPipelineContext**展開されたスキーマを取得する必要があります、実行時に、コンポーネントのスキーマの種類名が指定しない場合にのみ、スキーマの種類ごとにスキーマを取得し、メッセージの種類のみでスキーマを取得場合は、コンポーネントの実行時に、スキーマの種類の情報を使用できません。</span><span class="sxs-lookup"><span data-stu-id="b1f0f-142">Custom pipeline components that use **IPipelineContext** to obtain deployed schemas should obtain schemas by schema type only if the schema type name is not specified for the component at run time, and obtain schemas by message type only if the schema type information is not available when the component is run.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1f0f-143">参照</span><span class="sxs-lookup"><span data-stu-id="b1f0f-143">See Also</span></span>  
 [<span data-ttu-id="b1f0f-144">パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b1f0f-144">Pipeline Components</span></span>](../core/pipeline-components.md)