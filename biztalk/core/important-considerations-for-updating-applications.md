---
title: "アプリケーションを更新するための重要な考慮事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- updating, applications
- applications, planning
- applications, updating
- planning, applications
- planning, updating
- updating, planning
ms.assetid: e7690bdf-943d-4bb6-b8cd-a6841b722d40
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c24528dcce390376b7ac2e47199aa5ae06d412a4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="important-considerations-for-updating-applications"></a><span data-ttu-id="abc42-102">アプリケーションの更新に関する重要な考慮事項</span><span class="sxs-lookup"><span data-stu-id="abc42-102">Important Considerations for Updating Applications</span></span>
<span data-ttu-id="abc42-103">アプリケーション (特に実稼働環境で実行されているアプリケーション) を更新する前に考慮する必要のある重要事項を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="abc42-103">The following are important issues to consider before updating an application, especially one that is running in a production environment.</span></span>  
  
## <a name="general-considerations"></a><span data-ttu-id="abc42-104">全般的な考慮事項</span><span class="sxs-lookup"><span data-stu-id="abc42-104">General considerations</span></span>  
  
-   <span data-ttu-id="abc42-105">パーティおよびルールはグループのスコープで認識されるため、パーティおよびルールを追加すると、他のアプリケーションが中断する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="abc42-105">Parties and rules are visible at a group scope, so adding additional parties and rules could disrupt other applications.</span></span>  
  
-   <span data-ttu-id="abc42-106">別のアイテムが依存しているアイテムを展開解除する場合は、依存しているアイテムを先に展開解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abc42-106">If you are undeploying an artifact on which another artifact depends, the dependent artifact must be undeployed first.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="abc42-107">BizTalk Server 管理コンソールは警告を表示し、順序が正しくないアイテムの展開解除できない場合。</span><span class="sxs-lookup"><span data-stu-id="abc42-107">The BizTalk Server Administration console will display a warning and prevent you from undeploying artifacts in the incorrect order.</span></span>  
  
-   <span data-ttu-id="abc42-108">既存のアプリケーションでの BizTalk アセンブリが更新された場合、変更を有効にするためにホスト インスタンスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abc42-108">If a BizTalk assembly in an existing application is updated, you may need to restart host instances for the changes to take effect.</span></span> <span data-ttu-id="abc42-109">ホスト インスタンスを再起動すると、ホスト インスタンスで実行されているその他のすべてのアプリケーションが停止します。</span><span class="sxs-lookup"><span data-stu-id="abc42-109">Restarting a host instance stops all other applications that are running on the host instance.</span></span>  
  
-   <span data-ttu-id="abc42-110">Visual Studio を使用してアプリケーションを実稼働環境に展開した場合 (この操作は実行しないことをお勧めします)、プロジェクト プロパティの [ホスト インスタンスを再起動します] オプションが有効に設定されていると、このアプリケーションに関連付けられていないアプリケーションを含め、アプリケーションを展開すると、すべてのホスト インスタンスが再起動します。</span><span class="sxs-lookup"><span data-stu-id="abc42-110">If you use Visual Studio to deploy an application into a production environment (which we strongly recommend against doing) and the Restart Host Instances option is set to True in project properties, all host instances will restart when you deploy the application, including those that are not associated with this application.</span></span> <span data-ttu-id="abc42-111">これにより、ローカル コンピューターのホスト インスタンスで実行されている他のすべてのアプリケーションが停止します。</span><span class="sxs-lookup"><span data-stu-id="abc42-111">This will stop all other applications that are running on any host instance on the local computer.</span></span>  
  
-   <span data-ttu-id="abc42-112">BizTalk アプリケーションとして展開される BizTalk Server アセンブリ (オーケストレーション、スキーマ、マップを含む) を更新する場合は、以下のいずれかを実行できます。</span><span class="sxs-lookup"><span data-stu-id="abc42-112">If you want to update a BizTalk Server assembly (containing an orchestration, schema, or map) which is deployed as a BizTalk application, you can do any of the following:</span></span>  
  
    -   <span data-ttu-id="abc42-113">並列展開を実行します。</span><span class="sxs-lookup"><span data-stu-id="abc42-113">Perform a side-by-side deployment.</span></span> <span data-ttu-id="abc42-114">通常は、バージョン番号を増やすことによって新しいアセンブリを適切に修正することができます。</span><span class="sxs-lookup"><span data-stu-id="abc42-114">You can appropriately modify the newer assembly typically by incrementing the version.</span></span> <span data-ttu-id="abc42-115">これによって、両方のアセンブリが完全修飾アセンブリ名を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="abc42-115">This makes both the assemblies have a distinct fully qualified assembly name.</span></span> <span data-ttu-id="abc42-116">詳細については、次を参照してください。[実行サイド バイ サイド既存のバージョンへのアプリケーションの新しいバージョンを展開する方法](../core/deploy-new-application-version-to-run-side-by-side-with-existing-version.md)です。</span><span class="sxs-lookup"><span data-stu-id="abc42-116">For more information, see [How to Deploy a New Version of an Application to Run Side-by-side with an Existing Version](../core/deploy-new-application-version-to-run-side-by-side-with-existing-version.md).</span></span>  
  
    -   <span data-ttu-id="abc42-117">既存の BizTalk Server アセンブリを新しいアセンブリで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="abc42-117">Replace the existing BizTalk Server assembly with a new assembly.</span></span> <span data-ttu-id="abc42-118">古いアセンブリを読み込む可能性のあるホスト インスタンスをすべて停止し、GAC 内の古いアセンブリを置き換え、ホスト インスタンスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abc42-118">You must stop all host instances that can possibly load the out-dated assembly, replace the out-dated assembly in the GAC, and then restart the host instances.</span></span>  
  
-   <span data-ttu-id="abc42-119">まったく新しいアプリケーションを展開して既存のアプリケーションを置き換える場合は、このアプリケーションと他のアプリケーションとの間の参照をすべて修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abc42-119">If you deploy an entirely new application to replace an existing application, you must correct any references between other applications and the application that you are replacing.</span></span>  
  
## <a name="considerations-for-updating-schemas"></a><span data-ttu-id="abc42-120">スキーマを更新する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="abc42-120">Considerations for updating schemas</span></span>  
  
-   <span data-ttu-id="abc42-121">アセンブリを BizTalk グループ内の既存のスキーマと同じメッセージ型を持つ新しいスキーマを含むアプリケーションを追加する場合は、パイプラインでスキーマの解決が発生したときに最新のバージョン番号を持つスキーマが使用されます。</span><span class="sxs-lookup"><span data-stu-id="abc42-121">If you add an assembly to an application that includes a new schema with the same message type as an existing schema in the BizTalk group, the schema with the highest version number will be used when schema resolution occurs in pipelines.</span></span> <span data-ttu-id="abc42-122">さらに、1 つのメッセージ型は、1 つ以上の .NET 型を参照して、このあいまいさではパイプラインの実行エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="abc42-122">In addition, if one message type refers to more than one .NET type, this ambiguity may cause pipeline execution failure.</span></span> <span data-ttu-id="abc42-123">これは、メッセージの種類、ターゲットの名前空間、およびインスタンスのルート名がスキーマの検索に使用されるためです。</span><span class="sxs-lookup"><span data-stu-id="abc42-123">This is because schema lookup uses message type, the target namespace, and root name of the instance.</span></span> <span data-ttu-id="abc42-124">この問題は、新しいスキーマと同じメッセージの種類のスキーマを使用するアプリケーション内のパイプラインで発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="abc42-124">This can occur for pipelines in any application that uses a schema with the same message type as the new schema.</span></span> <span data-ttu-id="abc42-125">スキーマの解決の詳細については、次を参照してください。[スキーマの解決パイプライン コンポーネントで](../core/schema-resolution-in-pipeline-components.md)です。</span><span class="sxs-lookup"><span data-stu-id="abc42-125">For more information about schema resolution, see [Schema Resolution in Pipeline Components](../core/schema-resolution-in-pipeline-components.md).</span></span>  
  
-   <span data-ttu-id="abc42-126">スキーマを更新する場合は、そのスキーマを参照しているマップを更新する (または新しいマップを作成する) だけでなく、そのスキーマに依存するオーケストレーションもすべて更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abc42-126">When you update a schema, you must also update the maps that reference the schema (or create new maps) as well as any orchestrations that rely on the schema.</span></span>  
  
-   <span data-ttu-id="abc42-127">スキーマのバージョン番号を増分した場合は、そのスキーマを使用するパイプライン インスタンスとパイプライン コンポーネントについて、そのスキーマへの参照を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abc42-127">If you increment a schema version, you should update the reference to the schema for any pipeline instances and pipeline components that use it.</span></span>  
  
-   <span data-ttu-id="abc42-128">スキーマを展開解除すると、スキーマの前のバージョンが使用可能であれば、そのバージョンがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="abc42-128">Undeploying a schema causes the previous version of the schema, if available, to become active.</span></span>  
  
## <a name="considerations-for-updating-policies"></a><span data-ttu-id="abc42-129">ポリシーを更新する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="abc42-129">Considerations for updating policies</span></span>  
  
-   <span data-ttu-id="abc42-130">BizTalk Server ランタイムでは、展開状態のポリシーの最新バージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="abc42-130">The highest version of a policy that is in a deployed state is used by the BizTalk Server runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abc42-131">参照</span><span class="sxs-lookup"><span data-stu-id="abc42-131">See Also</span></span>  
 [<span data-ttu-id="abc42-132">BizTalk アプリケーションの更新</span><span class="sxs-lookup"><span data-stu-id="abc42-132">Updating BizTalk Applications</span></span>](../core/updating-biztalk-applications.md)