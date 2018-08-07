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
ms.openlocfilehash: c269ff3a7a5d973356754a222699c93179c90362
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984787"
---
# <a name="schema-resolution-in-pipeline-components"></a><span data-ttu-id="7fd03-102">パイプライン コンポーネントのスキーマの解決</span><span class="sxs-lookup"><span data-stu-id="7fd03-102">Schema Resolution in Pipeline Components</span></span>
<span data-ttu-id="7fd03-103">パイプラインの逆アセンブラー コンポーネントおよびアセンブラー コンポーネントは、XSD スキーマを使用して、メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="7fd03-103">Pipeline disassembler and assembler components use XSD schemas to process messages.</span></span> <span data-ttu-id="7fd03-104">スキーマには、昇格させたプロパティの一覧、識別フィールド、フラット ファイル メッセージの注釈、XML エンベロープの注釈などの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7fd03-104">The schemas contain information such as the list of promoted properties, distinguished fields, annotations for flat file messages, and annotations for XML envelopes.</span></span>  
  
 <span data-ttu-id="7fd03-105">標準の逆アセンブラー コンポーネントおよびアセンブラー コンポーネントは、スキーマの種類名およびメッセージの種類を使用して、展開されたスキーマの取得をサポートします。</span><span class="sxs-lookup"><span data-stu-id="7fd03-105">Standard disassembler and assembler components support retrieval of deployed schemas by using the schema type name and message type.</span></span> <span data-ttu-id="7fd03-106">一部のコンポーネントは、スキーマの種類名とメッセージの種類の両方を使用して、スキーマを取得します。スキーマの種類だけでスキーマを取得するコンポーネント (フラット ファイル逆アセンブラーなど) もあります。</span><span class="sxs-lookup"><span data-stu-id="7fd03-106">Some components retrieve by using both the schema type name and the message type, while others (for example, the Flat File Disassembler) retrieve only by the schema type.</span></span>  
  
 <span data-ttu-id="7fd03-107">XML メッセージを取得するパイプライン コンポーネントは、メッセージのルート要素および名前空間を調べて、メッセージの種類を判別します。</span><span class="sxs-lookup"><span data-stu-id="7fd03-107">Pipeline components that receive XML messages determine the message type by examining the message root element and namespace.</span></span> <span data-ttu-id="7fd03-108">たとえば、次の XML のメッセージの種類は"<http://MyDocument.org#MyDocument>"。</span><span class="sxs-lookup"><span data-stu-id="7fd03-108">For example, the message type for the following XML is "<http://MyDocument.org#MyDocument>".</span></span>  
  
```  
<ns0:MyDocument xmlns:ns0="http://MyDocument.org">  
  
</ns0:MyDocument>  
```  
  
 <span data-ttu-id="7fd03-109">スキーマが定義された名前空間を持たない場合、メッセージの種類は、"\<**rootNode**\>"。</span><span class="sxs-lookup"><span data-stu-id="7fd03-109">If a schema does not have a namespace defined for it, the message type is "\<**rootNode**\>".</span></span> <span data-ttu-id="7fd03-110">たとえば、前の例の XML で名前空間がない場合、メッセージの種類は、"MyDocument" になります。</span><span class="sxs-lookup"><span data-stu-id="7fd03-110">For example, if the preceding example XML had no namespace, the message type would be "MyDocument".</span></span>  
  
 <span data-ttu-id="7fd03-111">標準のパイプライン コンポーネントは、メッセージの種類を使用して、データベースから適切なスキーマを取得します。</span><span class="sxs-lookup"><span data-stu-id="7fd03-111">Standard pipeline components use the message type to retrieve the appropriate schema from the database.</span></span> <span data-ttu-id="7fd03-112">既定の XML の受信および送信パイプラインは、メッセージの XML コンテンツから実行時に動的に検出されるメッセージの種類を使用して、読み込むスキーマを常に判別します (認識されないメッセージが許可されるように、パイプライン コンポーネントが設定されている場合を除く)。</span><span class="sxs-lookup"><span data-stu-id="7fd03-112">Default XML receive and send pipelines always determine which schema to load by using the message type dynamically discovered at runtime from the message XML content (unless the pipeline component is set to allow unrecognized messages).</span></span> <span data-ttu-id="7fd03-113">XML 逆アセンブラーでは、このメカニズムを使用して、メッセージのエンベロープを削除できます。ただし、XML アセンブラーは、使用するエンベロープ スキーマを認識しないままで送信メッセージのエンベロープを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="7fd03-113">The XML Disassembler can remove the message envelope by using this mechanism; however, the XML Assembler cannot create an envelope for an outgoing message without knowing what envelope schema to use.</span></span>  
  
 <span data-ttu-id="7fd03-114">パイプライン デザイナーから、XML アセンブラーの構成プロパティのエンベロープ スキーマを指定します。</span><span class="sxs-lookup"><span data-stu-id="7fd03-114">You specify the envelope schema in the configuration properties for the XML Assembler from within the pipeline designer.</span></span>  
  
## <a name="how-schemas-are-resolved"></a><span data-ttu-id="7fd03-115">スキーマの解決方法</span><span class="sxs-lookup"><span data-stu-id="7fd03-115">How Schemas Are Resolved</span></span>  
 <span data-ttu-id="7fd03-116">XmlDisassembler で直接スキーマを指定していない場合、スキーマは次の方法で解決されます。</span><span class="sxs-lookup"><span data-stu-id="7fd03-116">Assuming you are not specifying the schema directly in the XmlDisassembler, schemas will be resolved in the following manner:</span></span>  
  
1. <span data-ttu-id="7fd03-117">最初に、展開されたスキーマで修飾されていない検索されるルート ノード名と名前空間を使用して (たとえば、http://MyNamespace#MyRoot)します。</span><span class="sxs-lookup"><span data-stu-id="7fd03-117">First, an unqualified search on the deployed schemas is made using the root node name and namespace (for example, http://MyNamespace#MyRoot).</span></span> <span data-ttu-id="7fd03-118">一致するものが 1 つだけ見つかった場合、スキーマは解決されます。</span><span class="sxs-lookup"><span data-stu-id="7fd03-118">If a unique match is found the schema is resolved.</span></span> <span data-ttu-id="7fd03-119">一致するものが複数見つかった場合で、バージョン番号のみが異なり 1 つのバージョンのみがアクティブな場合は、そのバージョンが使用され、スキーマは解決されます。</span><span class="sxs-lookup"><span data-stu-id="7fd03-119">If multiple matches are found and differ only by version number and only one is active, that version is used and the schema is resolved.</span></span> <span data-ttu-id="7fd03-120">同じスキーマが複数のアプリケーションでアクティブになっている場合は、複数のアクティブなスキーマが検出されます。この場合、次のステップ 2 に進んでさらに検索が行われます。</span><span class="sxs-lookup"><span data-stu-id="7fd03-120">If the same schema is active in multiple applications, multiple active schemas will be found and the search will continue with step 2 below.</span></span>  
  
2. <span data-ttu-id="7fd03-121">手順 1 の複数の一致を解決できない場合は、検索は、アセンブリで、パイプラインの実行によって修飾されます。</span><span class="sxs-lookup"><span data-stu-id="7fd03-121">If there are multiple matches that step 1 cannot resolve, the search is qualified by the assembly the pipeline is executing in.</span></span> <span data-ttu-id="7fd03-122">一意のスキーマが同じアセンブリ内で見つかった場合、パイプラインを実行し、スキーマは解決されます。</span><span class="sxs-lookup"><span data-stu-id="7fd03-122">If a unique schema is found within the same assembly the pipeline is executing in, then the schema is resolved.</span></span>  
  
3. <span data-ttu-id="7fd03-123">一致するスキーマが見つからない場合は、スキーマの解決にパブリッシャーが使用され、</span><span class="sxs-lookup"><span data-stu-id="7fd03-123">If there are still no matches, then the publisher is used to resolve the schema.</span></span> <span data-ttu-id="7fd03-124">ルート ノード、名前空間、および公開キー トークンを使用して検索が絞り込まれます。</span><span class="sxs-lookup"><span data-stu-id="7fd03-124">The search is narrowed by using the root node, namespace, and public key token.</span></span> <span data-ttu-id="7fd03-125">一致するスキーマが 1 つだけ見つかった場合、スキーマは解決されます。</span><span class="sxs-lookup"><span data-stu-id="7fd03-125">If a unique schema is found using this search, the schema is resolved.</span></span>  
  
4. <span data-ttu-id="7fd03-126">スキーマを解決できない場合は、</span><span class="sxs-lookup"><span data-stu-id="7fd03-126">Schema cannot be resolved.</span></span> <span data-ttu-id="7fd03-127">一意のスキーマが見つからないというエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="7fd03-127">An error is returned noting that no unique schema can be found.</span></span>  
  
   <span data-ttu-id="7fd03-128">スキーマの解決には、SQL Server 照合順序の大文字小文字の区別の影響を含むその他の考慮事項を参照してください。 [Namespace 管理](../core/namespace-management.md)します。</span><span class="sxs-lookup"><span data-stu-id="7fd03-128">For other considerations including the effect of SQL Server collation and case-sensitivity on schema resolution, see [Namespace Management](../core/namespace-management.md).</span></span>  
  
   <span data-ttu-id="7fd03-129">XML アセンブラーのエンベロープまたはフラット ファイル アセンブラーのヘッダーおよびトレーラーを作成するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7fd03-129">To create an envelope in the XML Assembler or a header and trailer in the Flat File Assembler, you may do one of the following:</span></span>  
  
- <span data-ttu-id="7fd03-130">カスタムの送信パイプラインを作成し、XML アセンブラーの構成プロパティのエンベロープ スキーマを指定します。</span><span class="sxs-lookup"><span data-stu-id="7fd03-130">Create a custom send pipeline and specify the schemas for the envelope in the configuration properties for the XML Assembler.</span></span> <span data-ttu-id="7fd03-131">この操作はパイプライン デザイナーで行います。</span><span class="sxs-lookup"><span data-stu-id="7fd03-131">This is done from within the pipeline designer.</span></span>  
  
- <span data-ttu-id="7fd03-132">BizTalk Server 管理コンソールで、送信ポートの送信パイプラインのプロパティに XMLTransmit を指定します。</span><span class="sxs-lookup"><span data-stu-id="7fd03-132">In the BizTalk Server Administration console specify XMLTransmit for the Send pipeline property on a send port.</span></span> <span data-ttu-id="7fd03-133">省略記号をクリックし、パイプラインのプロパティを構成します。次に、EnvelopeDocSpecNames プロパティのエンベロープ スキーマを指定します。</span><span class="sxs-lookup"><span data-stu-id="7fd03-133">Click the ellipsis to configure the pipeline properties and specify the schema for the envelope in the EnvelopeDocSpecNames property.</span></span>  
  
  <span data-ttu-id="7fd03-134">同じスキーマの複数のバージョンがデータベースに意図的に (または誤って) 展開されている場合 (並列配置や複数のシナリオが固有のメッセージの種類を使用している場合など)、メッセージの種類によるスキーマ解決が機能しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="7fd03-134">Schema resolution by message type may not work if several versions of the same schema are intentionally or accidentally deployed in the database (for example, in a side-by-side deployment or if multiple scenarios do not have unique message types).</span></span> <span data-ttu-id="7fd03-135">メッセージの種類によるスキーマ解決に失敗した場合、"スキーマがあいまい" であることを示すエラーがイベント ログに追加されます。</span><span class="sxs-lookup"><span data-stu-id="7fd03-135">If schema resolution by message type fails, a "schema ambiguity" error is added to the event log.</span></span> <span data-ttu-id="7fd03-136">メッセージの種類によるスキーマ解決が成功したかを確認するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7fd03-136">To ensure that schema resolution by message type succeeds, do one of the following:</span></span>  
  
- <span data-ttu-id="7fd03-137">カスタム パイプラインと同じ BizTalk プロジェクトのスキーマを定義します。</span><span class="sxs-lookup"><span data-stu-id="7fd03-137">Define the schemas in the same BizTalk project as your custom pipeline.</span></span>  
  
- <span data-ttu-id="7fd03-138">パイプラインを含むアセンブリと同じキーを持つスキーマのアセンブリに署名します。</span><span class="sxs-lookup"><span data-stu-id="7fd03-138">Sign the assembly with the schemas with the same key as the assembly containing the pipelines.</span></span>  
  
- <span data-ttu-id="7fd03-139">パイプライン コンポーネントのスキーマを明示的に指定します (メッセージの種類の名前は、BizTalk 管理データベースで固有にする必要があります)。</span><span class="sxs-lookup"><span data-stu-id="7fd03-139">Explicitly specify schemas in pipeline components (message type names should be unique across the BizTalk Management database).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7fd03-140">同じアセンブリ内のスキーマでメッセージの種類を共有する場合、同一のパイプライン コンポーネント アセンブリ内にこれらのスキーマを含めないでください。これは、あいまい解決の制限があるためです。代わりに、パイプライン コンポーネント アセンブリの外部のスキーマを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fd03-140">When schemas in the same assembly share a message type, you must not include the schemas in the same pipeline component assembly due to the limitations of ambiguity resolution; instead, reference schemas that are external to the pipeline component assembly.</span></span> <span data-ttu-id="7fd03-141">スキーマおよびパイプライン コンポーネントが同じアセンブリにある場合、スキーマの種類名がカスタム パイプラインのパイプライン コンポーネントで明示的に指定されていても、あいまい解決は機能しません。</span><span class="sxs-lookup"><span data-stu-id="7fd03-141">Ambiguity resolution does not work when schemas and pipeline components are in the same assembly, even if schema type names are explicitly specified in pipeline components in custom pipelines.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fd03-142">使用するカスタム パイプライン コンポーネント**IPipelineContext**展開されたスキーマを取得する必要があります、実行時に、コンポーネントのスキーマの種類名が指定しない場合にのみ、スキーマの種類ごとにスキーマを取得し、メッセージの種類のみでスキーマを取得場合は、コンポーネントの実行時に、スキーマの種類の情報を使用できません。</span><span class="sxs-lookup"><span data-stu-id="7fd03-142">Custom pipeline components that use **IPipelineContext** to obtain deployed schemas should obtain schemas by schema type only if the schema type name is not specified for the component at run time, and obtain schemas by message type only if the schema type information is not available when the component is run.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fd03-143">参照</span><span class="sxs-lookup"><span data-stu-id="7fd03-143">See Also</span></span>  
 [<span data-ttu-id="7fd03-144">パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7fd03-144">Pipeline Components</span></span>](../core/pipeline-components.md)