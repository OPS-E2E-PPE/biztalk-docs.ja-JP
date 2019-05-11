---
title: アプリケーションを更新するための重要な考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- updating, applications
- applications, planning
- applications, updating
- planning, applications
- planning, updating
- updating, planning
ms.assetid: e7690bdf-943d-4bb6-b8cd-a6841b722d40
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39b3bdd5d939edd1fa1d930d5711f8bac8a8f71c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382590"
---
# <a name="important-considerations-for-updating-applications"></a><span data-ttu-id="81394-102">アプリケーションを更新するための重要な考慮事項</span><span class="sxs-lookup"><span data-stu-id="81394-102">Important Considerations for Updating Applications</span></span>
<span data-ttu-id="81394-103">特に 1 つ、実稼働環境で実行されているアプリケーションを更新する前に考慮すべき重要な問題を次に示します。</span><span class="sxs-lookup"><span data-stu-id="81394-103">The following are important issues to consider before updating an application, especially one that is running in a production environment.</span></span>  
  
## <a name="general-considerations"></a><span data-ttu-id="81394-104">全般的な考慮事項</span><span class="sxs-lookup"><span data-stu-id="81394-104">General considerations</span></span>  
  
-   <span data-ttu-id="81394-105">パーティおよびルールは、他のアプリケーションに悪影響を及ぼすその他のパーティおよびルールを追加するため、グループのスコープで表示されます。</span><span class="sxs-lookup"><span data-stu-id="81394-105">Parties and rules are visible at a group scope, so adding additional parties and rules could disrupt other applications.</span></span>  
  
-   <span data-ttu-id="81394-106">別のアイテムが依存するアイテムの展開を解除する場合、依存するアイテムでなければなりませんデプロイ最初。</span><span class="sxs-lookup"><span data-stu-id="81394-106">If you are undeploying an artifact on which another artifact depends, the dependent artifact must be undeployed first.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="81394-107">BizTalk Server 管理コンソールは警告を表示して、間違った順序でアイテムの展開解除されないようにします。</span><span class="sxs-lookup"><span data-stu-id="81394-107">The BizTalk Server Administration console will display a warning and prevent you from undeploying artifacts in the incorrect order.</span></span>  
  
-   <span data-ttu-id="81394-108">既存のアプリケーションでの BizTalk アセンブリが更新された場合は、変更を反映するためのホスト インスタンスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81394-108">If a BizTalk assembly in an existing application is updated, you may need to restart host instances for the changes to take effect.</span></span> <span data-ttu-id="81394-109">ホスト インスタンスを再起動すると、ホスト インスタンスで実行されているその他のすべてのアプリケーションが停止します。</span><span class="sxs-lookup"><span data-stu-id="81394-109">Restarting a host instance stops all other applications that are running on the host instance.</span></span>  
  
-   <span data-ttu-id="81394-110">すべてのホスト インスタンスが、アプリケーションを展開するときに再起動されます (これは強く、操作は実行しないお勧めします)、運用環境にアプリケーションを配置する Visual Studio を使用すると、プロジェクトのプロパティで、ホスト インスタンスを再起動オプションが True に設定、このアプリケーションに関連付けられていないものも含めています。</span><span class="sxs-lookup"><span data-stu-id="81394-110">If you use Visual Studio to deploy an application into a production environment (which we strongly recommend against doing) and the Restart Host Instances option is set to True in project properties, all host instances will restart when you deploy the application, including those that are not associated with this application.</span></span> <span data-ttu-id="81394-111">ローカル コンピューター上の任意のホスト インスタンスで実行されているその他のすべてのアプリケーションを停止します。</span><span class="sxs-lookup"><span data-stu-id="81394-111">This will stop all other applications that are running on any host instance on the local computer.</span></span>  
  
-   <span data-ttu-id="81394-112">BizTalk アプリケーションとして展開される BizTalk Server アセンブリ (オーケストレーション、スキーマ、またはマップを含む) を更新する場合は、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="81394-112">If you want to update a BizTalk Server assembly (containing an orchestration, schema, or map) which is deployed as a BizTalk application, you can do any of the following:</span></span>  
  
    -   <span data-ttu-id="81394-113">サイド バイ サイド展開を実行します。</span><span class="sxs-lookup"><span data-stu-id="81394-113">Perform a side-by-side deployment.</span></span> <span data-ttu-id="81394-114">バージョンをインクリメントして通常適切に新しいアセンブリを変更できます。</span><span class="sxs-lookup"><span data-stu-id="81394-114">You can appropriately modify the newer assembly typically by incrementing the version.</span></span> <span data-ttu-id="81394-115">これにより、両方の完全修飾アセンブリ名があるアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="81394-115">This makes both the assemblies have a distinct fully qualified assembly name.</span></span> <span data-ttu-id="81394-116">詳細については、次を参照してください。[実行のサイド既存のバージョンへのアプリケーションの新しいバージョンをデプロイする方法](../core/deploy-new-application-version-to-run-side-by-side-with-existing-version.md)します。</span><span class="sxs-lookup"><span data-stu-id="81394-116">For more information, see [How to Deploy a New Version of an Application to Run Side-by-side with an Existing Version](../core/deploy-new-application-version-to-run-side-by-side-with-existing-version.md).</span></span>  
  
    -   <span data-ttu-id="81394-117">新しいアセンブリでは、既存の BizTalk Server アセンブリを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="81394-117">Replace the existing BizTalk Server assembly with a new assembly.</span></span> <span data-ttu-id="81394-118">古いアセンブリを読み込む可能性、GAC 内の古いアセンブリを交換し、ホスト インスタンスを再起動するすべてのホスト インスタンスを停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81394-118">You must stop all host instances that can possibly load the out-dated assembly, replace the out-dated assembly in the GAC, and then restart the host instances.</span></span>  
  
-   <span data-ttu-id="81394-119">既存のアプリケーションを置換するまったく新しいアプリケーションを展開する場合は、他のアプリケーションと交換するアプリケーションの間の参照を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81394-119">If you deploy an entirely new application to replace an existing application, you must correct any references between other applications and the application that you are replacing.</span></span>  
  
## <a name="considerations-for-updating-schemas"></a><span data-ttu-id="81394-120">スキーマの更新に関する注意点</span><span class="sxs-lookup"><span data-stu-id="81394-120">Considerations for updating schemas</span></span>  
  
-   <span data-ttu-id="81394-121">にアセンブリを BizTalk グループ内の既存のスキーマと同じメッセージ型を持つ新しいスキーマを含むアプリケーションを追加する場合は、スキーマの解決はパイプラインで発生すると最高のバージョン番号を持つスキーマが使用されます。</span><span class="sxs-lookup"><span data-stu-id="81394-121">If you add an assembly to an application that includes a new schema with the same message type as an existing schema in the BizTalk group, the schema with the highest version number will be used when schema resolution occurs in pipelines.</span></span> <span data-ttu-id="81394-122">さらに、1 つのメッセージの種類は、1 つ以上の .NET 型を参照している場合、このあいまいさは、パイプラインの実行エラーを生じる。</span><span class="sxs-lookup"><span data-stu-id="81394-122">In addition, if one message type refers to more than one .NET type, this ambiguity may cause pipeline execution failure.</span></span> <span data-ttu-id="81394-123">これは、メッセージの種類、ターゲットの名前空間、およびインスタンスのルート名がスキーマの検索に使用されるためです。</span><span class="sxs-lookup"><span data-stu-id="81394-123">This is because schema lookup uses message type, the target namespace, and root name of the instance.</span></span> <span data-ttu-id="81394-124">これは、パイプラインで、スキーマ、新しいスキーマと同じメッセージの種類を使用する任意のアプリケーションで発生します。</span><span class="sxs-lookup"><span data-stu-id="81394-124">This can occur for pipelines in any application that uses a schema with the same message type as the new schema.</span></span> <span data-ttu-id="81394-125">スキーマの解決の詳細については、次を参照してください。[スキーマの解決パイプライン コンポーネントで](../core/schema-resolution-in-pipeline-components.md)します。</span><span class="sxs-lookup"><span data-stu-id="81394-125">For more information about schema resolution, see [Schema Resolution in Pipeline Components](../core/schema-resolution-in-pipeline-components.md).</span></span>  
  
-   <span data-ttu-id="81394-126">スキーマを更新するときに、スキーマに依存するすべてのオーケストレーションとスキーマを参照します (または新しいマップを作成する) のマップを更新することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="81394-126">When you update a schema, you must also update the maps that reference the schema (or create new maps) as well as any orchestrations that rely on the schema.</span></span>  
  
-   <span data-ttu-id="81394-127">スキーマのバージョンをインクリメントする場合は、すべてのパイプライン インスタンスとそれを使用するパイプライン コンポーネントのスキーマへの参照を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81394-127">If you increment a schema version, you should update the reference to the schema for any pipeline instances and pipeline components that use it.</span></span>  
  
-   <span data-ttu-id="81394-128">スキーマを展開解除と、使用可能なアクティブになる場合のスキーマの以前のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="81394-128">Undeploying a schema causes the previous version of the schema, if available, to become active.</span></span>  
  
## <a name="considerations-for-updating-policies"></a><span data-ttu-id="81394-129">ポリシーの更新に関する注意点</span><span class="sxs-lookup"><span data-stu-id="81394-129">Considerations for updating policies</span></span>  
  
-   <span data-ttu-id="81394-130">展開された状態にあるポリシーの最新バージョンは、BizTalk Server ランタイムによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="81394-130">The highest version of a policy that is in a deployed state is used by the BizTalk Server runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81394-131">参照</span><span class="sxs-lookup"><span data-stu-id="81394-131">See Also</span></span>  
 [<span data-ttu-id="81394-132">BizTalk アプリケーションの更新</span><span class="sxs-lookup"><span data-stu-id="81394-132">Updating BizTalk Applications</span></span>](../core/updating-biztalk-applications.md)