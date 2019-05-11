---
title: バージョン管理、ビジネス プロセス管理ソリューション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- versioning, process management solutions
- process management solution tutorial, modifying
- process management solution tutorial, versioning
- processing, stages
- process management solution tutorial, processing stages
ms.assetid: 501b2162-821f-44e1-87c0-8628cc5bd9c3
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f3b030ed67745e37b9808d888a5f0df07e57bba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393753"
---
# <a name="versioning-the-business-process-management-solution"></a><span data-ttu-id="406bf-102">ビジネス プロセス管理ソリューションのバージョン管理</span><span class="sxs-lookup"><span data-stu-id="406bf-102">Versioning the Business Process Management Solution</span></span>
<span data-ttu-id="406bf-103">ビジネス プロセス管理ソリューションでは、必要に応じてステージを置換できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="406bf-103">The Business Process Management solution is designed so that you can replace stages if necessary.</span></span> <span data-ttu-id="406bf-104">設計を簡単にスキーマのバージョン管理も提供します。</span><span class="sxs-lookup"><span data-stu-id="406bf-104">The design also provides for an easier method of versioning schemas.</span></span>  
  
 <span data-ttu-id="406bf-105">ビジネス プロセスをステージに分割する方法の詳細については、次を参照してください。 [、ビジネス プロセス管理ソリューションの一部の設計原則](../core/some-design-principles-in-the-business-process-management-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="406bf-105">For information about dividing a business process into stages, see [Some Design Principles in the Business Process Management Solution](../core/some-design-principles-in-the-business-process-management-solution.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="406bf-106">ソリューションの要素は、メッセージ構造に大きく依存します。</span><span class="sxs-lookup"><span data-stu-id="406bf-106">Elements of the solution are highly dependent on the message structures.</span></span> <span data-ttu-id="406bf-107">メッセージの構造を変更するには、オーケストレーションに大幅な変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="406bf-107">Changing message structures requires substantial changes to the orchestrations.</span></span>  
  
 <span data-ttu-id="406bf-108">更新プログラムを処理するためにデプロイ済みのソリューションとスクリプトの記述に関するガイドラインのアセンブリの更新に関する一般的な説明は、次を参照してください。 [BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="406bf-108">For general directions about updating assemblies in a deployed solution and guidelines for writing scripts to handle the update, see [Updating BizTalk Applications](../core/updating-biztalk-applications.md).</span></span>  
  
## <a name="adding-replacing-or-removing-stages"></a><span data-ttu-id="406bf-109">追加、置換、またはステージを削除します。</span><span class="sxs-lookup"><span data-stu-id="406bf-109">Adding, Replacing, or Removing Stages</span></span>  
 <span data-ttu-id="406bf-110">注文処理ステージ オーケストレーションは、2 種類のコードを含める: ビジネス プロセスと、ソリューションで動作できるように、インフラストラクチャを提供するコードを実装するコードです。</span><span class="sxs-lookup"><span data-stu-id="406bf-110">The order processing stage orchestrations contain two kinds of code: code that implements the business process and code that provides the infrastructure so that it can operate in the solution.</span></span> <span data-ttu-id="406bf-111">ステージのオーケストレーションの両方で**CableOrder1**と**CableOrder2**、ビジネス プロセス コード グループ図形内のラベルは「ビジネス処理します」。</span><span class="sxs-lookup"><span data-stu-id="406bf-111">In both of the stage orchestrations, **CableOrder1** and **CableOrder2**, the business process code is inside a group shape labeled "Business Processing."</span></span>  
  
 <span data-ttu-id="406bf-112">新しいステージを作成する最も簡単な方法では、各ステージの 1 つをコピー、「ビジネス プロセス」グループ内のコードをコードに置き換えます、インフラストラクチャ コードをそのままです。</span><span class="sxs-lookup"><span data-stu-id="406bf-112">The easiest way to create a new stage is to copy one of the stages, replace the code in the "Business Processing" group with your code, and leave the infrastructure code intact.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="406bf-113">**CableOrder2**オーケストレーションが、「ビジネス プロセス」の 2 つのグループ、2 番目は Update History Send 図形です。</span><span class="sxs-lookup"><span data-stu-id="406bf-113">The **CableOrder2** orchestration has two "Business Processing" groups, the second around the Update History Send shape.</span></span> <span data-ttu-id="406bf-114">送信図形には、効率的な送信スコープの一部です。</span><span class="sxs-lookup"><span data-stu-id="406bf-114">The Send shape is part of an efficient send scope.</span></span> <span data-ttu-id="406bf-115">(詳細についてを参照してください「の向上パフォーマンスで入れ子になったスコープ」 [OrderBroker オーケストレーションで処理](../core/processing-in-the-orderbroker-orchestration.md))。グループ図形はスコープ図形の一部を重ねることはできません、ため、2 番目のグループは、ビジネス プロセス コードの一部であることを示すラベルします。</span><span class="sxs-lookup"><span data-stu-id="406bf-115">(For more information, see "Improving Performance with Nested Scopes" in [Processing in the OrderBroker Orchestration](../core/processing-in-the-orderbroker-orchestration.md).) Because a Group shape cannot overlap part of a scope shape, the second group is labeled to indicate it is part of the business process code.</span></span>  
  
 <span data-ttu-id="406bf-116">シーケンスの番号に新しいオーケストレーションのフィルター式を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="406bf-116">You must set the filter expression on the new orchestration to its number in the sequence.</span></span> <span data-ttu-id="406bf-117">**OrderManager**ステージ番号は、いずれかで始めるし、各次のステージ (1, 2, 3...) を 1 ずつ増加を前提としています。</span><span class="sxs-lookup"><span data-stu-id="406bf-117">The **OrderManager** assumes stage numbers begin with one and increase by one for each following stage (1, 2, 3 …).</span></span> <span data-ttu-id="406bf-118">3 番目のステージをフィルター処理するには、次のフィルター式を設定します。</span><span class="sxs-lookup"><span data-stu-id="406bf-118">To filter for a third stage, you would set the filter expression to the following:</span></span>  
  
 `(Microsoft.Samples.BizTalk.SouthridgeVidoe.Schemas.Stage == 3)`  
  
 <span data-ttu-id="406bf-119">ソリューションでは、BAM API を使用して、注文処理ステージを含む、ソリューション内のイベントを追跡します。</span><span class="sxs-lookup"><span data-stu-id="406bf-119">The solution uses the BAM API to track events in the solution, including the order processing stages.</span></span> <span data-ttu-id="406bf-120">最初の段階、BAM アクティビティを開始します。最終ステージで終了します。</span><span class="sxs-lookup"><span data-stu-id="406bf-120">The first stage starts the BAM activity; the final stage ends it.</span></span> <span data-ttu-id="406bf-121">場合は、ソリューション内のハンドラー、例外が関連する BAM アクティビティを終了があります。</span><span class="sxs-lookup"><span data-stu-id="406bf-121">If there exceptions, the handlers in the solution end the BAM activities involved.</span></span> <span data-ttu-id="406bf-122">BAM は、効果的に再組み立てられますを監視するための継続的なビューに連続していない操作。</span><span class="sxs-lookup"><span data-stu-id="406bf-122">BAM effectively re-assembles the discontinuous operations into a continuous view for monitoring.</span></span>  
  
## <a name="changing-configuration"></a><span data-ttu-id="406bf-123">構成を変更します。</span><span class="sxs-lookup"><span data-stu-id="406bf-123">Changing Configuration</span></span>  
 <span data-ttu-id="406bf-124">場合は、変更内容を拡大またはステージの数を減らす、エンタープライズ シングル サインオン (SSO) シークレット ストアに格納されている構成情報を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="406bf-124">If your changes increase or decrease the number of stages, you must change the configuration information stored in the Enterprise Single Sign-On (SSO) secret store.</span></span>  
  
 <span data-ttu-id="406bf-125">構成設定を変更するには、アプリケーションを展開していない場合**TotalStages** CreateSouthridgeVideoApplication.cmd スクリプト ファイル。</span><span class="sxs-lookup"><span data-stu-id="406bf-125">If you haven't deployed the application, you can modify the configuration setting for **TotalStages** in the CreateSouthridgeVideoApplication.cmd script file.</span></span> <span data-ttu-id="406bf-126">値は、デプロイ時に、スクリプトの実行時に変更されます。</span><span class="sxs-lookup"><span data-stu-id="406bf-126">The value will change when the script is run during deployment.</span></span>  
  
 <span data-ttu-id="406bf-127">アプリケーションが既にある場合は、sdk \common\ssoapplicationconfig フォルダでコマンド ライン ユーティリティ BTSScnSSOApplicationConfig を実行して値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="406bf-127">If you have already deployed the application, you can change value by running a command line utility, BTSScnSSOApplicationConfig, in the SDK\Common\SsoApplicationConfig folder.</span></span> <span data-ttu-id="406bf-128">ステージの合計数を 3 に設定するには、次のコマンドラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="406bf-128">To set the total number of stages to three, you'd use the following command line:</span></span>  
  
 `BTSScnSSOApplicationConfig -set SouthRidgeVideo.CableOrder ConfigProperties TotalStages 3`  
  
 <span data-ttu-id="406bf-129">ソリューションが構成値をキャッシュするために、更新間隔が経過を有効にする新しい値になるまでを待つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="406bf-129">Because the solution caches the configuration values, you must wait until the  refresh interval passes for the new value to take effect.</span></span>  
  
## <a name="versioning-schemas"></a><span data-ttu-id="406bf-130">バージョン管理スキーマ</span><span class="sxs-lookup"><span data-stu-id="406bf-130">Versioning Schemas</span></span>  
 <span data-ttu-id="406bf-131">BizTalk は、それを含むアセンブリの最新のバージョンからのスキーマです。</span><span class="sxs-lookup"><span data-stu-id="406bf-131">BizTalk takes a schema from the most recent version of the assembly containing it.</span></span> <span data-ttu-id="406bf-132">これは、スキーマの新しいバージョンを作成する場合、完全にスキーマのすべての以前のバージョンが置き換えられますことを意味します。</span><span class="sxs-lookup"><span data-stu-id="406bf-132">This means that if you create a new version of a schema it completely replaces all previous versions of the schema.</span></span> <span data-ttu-id="406bf-133">これは、短期間のトランザクションの場合に有効です。</span><span class="sxs-lookup"><span data-stu-id="406bf-133">This works well when transactions are short-lived.</span></span> <span data-ttu-id="406bf-134">ただし、ビジネス プロセス管理ソリューションでのトランザクションは有効期間が長い: 完了 1 年間に注文かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="406bf-134">However, transactions in the Business Process Management solution are long-lived: an order may take up to a year to complete.</span></span>  
  
 <span data-ttu-id="406bf-135">スキーマの複数のバージョンが使用される可能性を考慮して、ソリューションの各スキーマは名前空間にバージョン番号を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="406bf-135">To allow for the possibility of using multiple versions of a schema being in use, each schema in the solution includes a version number in its namespace.</span></span> <span data-ttu-id="406bf-136">たとえば、注文スキーマの名前空間は次のようになっています。</span><span class="sxs-lookup"><span data-stu-id="406bf-136">For example, the namespace for the Order schema is as follows:</span></span>  
  
```  
http://Microsoft.Samples.BizTalk.SouthridgeVideo.Schemas.Order.v1  
```  
  
 <span data-ttu-id="406bf-137">名前空間は、スキーマとバージョン番号は含めることにも、スキーマに対して一意の名前空間を識別、ために、新しいスキーマは、以前のバージョンから個別になります。</span><span class="sxs-lookup"><span data-stu-id="406bf-137">Because the namespace identifies the schema and inclusion of the version number makes the namespace unique to the schema, the new schema will be distinct from the older version.</span></span> <span data-ttu-id="406bf-138">したがって、古いスキーマを置き換えずに新しいスキーマを使用できます。</span><span class="sxs-lookup"><span data-stu-id="406bf-138">Thus, a new schema can be used without supplanting the old schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="406bf-139">参照</span><span class="sxs-lookup"><span data-stu-id="406bf-139">See Also</span></span>  
 [<span data-ttu-id="406bf-140">ビジネス プロセス管理ソリューションの開発</span><span class="sxs-lookup"><span data-stu-id="406bf-140">Developing a Business Process Management Solution</span></span>](../core/developing-a-business-process-management-solution.md)