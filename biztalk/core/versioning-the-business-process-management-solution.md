---
title: "ビジネス プロセス管理ソリューションのバージョン管理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- versioning, process management solutions
- process management solution tutorial, modifying
- process management solution tutorial, versioning
- processing, stages
- process management solution tutorial, processing stages
ms.assetid: 501b2162-821f-44e1-87c0-8628cc5bd9c3
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af8afd3666a35b827ff25b243c1bfb4c81262273
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="versioning-the-business-process-management-solution"></a><span data-ttu-id="52027-102">ビジネス プロセス管理ソリューションのバージョン管理</span><span class="sxs-lookup"><span data-stu-id="52027-102">Versioning the Business Process Management Solution</span></span>
<span data-ttu-id="52027-103">ビジネス プロセス管理ソリューションは、必要に応じてステージを置換できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="52027-103">The Business Process Management solution is designed so that you can replace stages if necessary.</span></span> <span data-ttu-id="52027-104">スキーマのバージョンを簡単に管理する機能も備えています。</span><span class="sxs-lookup"><span data-stu-id="52027-104">The design also provides for an easier method of versioning schemas.</span></span>  
  
 <span data-ttu-id="52027-105">ビジネス プロセスをステージに分割する方法については、次を参照してください。[ビジネス プロセス管理ソリューションで一部の設計原則](../core/some-design-principles-in-the-business-process-management-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="52027-105">For information about dividing a business process into stages, see [Some Design Principles in the Business Process Management Solution](../core/some-design-principles-in-the-business-process-management-solution.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52027-106">ソリューションの要素は、メッセージ構造に大きく依存します。</span><span class="sxs-lookup"><span data-stu-id="52027-106">Elements of the solution are highly dependent on the message structures.</span></span> <span data-ttu-id="52027-107">メッセージ構造を変更するには、オーケストレーションを大幅に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52027-107">Changing message structures requires substantial changes to the orchestrations.</span></span>  
  
 <span data-ttu-id="52027-108">配置されたソリューションとスクリプトの記述に関するガイドラインの更新を処理するアセンブリの更新に関する一般的な手順については、次を参照してください。 [BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)です。</span><span class="sxs-lookup"><span data-stu-id="52027-108">For general directions about updating assemblies in a deployed solution and guidelines for writing scripts to handle the update, see [Updating BizTalk Applications](../core/updating-biztalk-applications.md).</span></span>  
  
## <a name="adding-replacing-or-removing-stages"></a><span data-ttu-id="52027-109">ステージの追加、置換、または削除</span><span class="sxs-lookup"><span data-stu-id="52027-109">Adding, Replacing, or Removing Stages</span></span>  
 <span data-ttu-id="52027-110">注文処理ステージ オーケストレーションは、2 種類のコードを含める: ビジネス プロセスと、ソリューション内に操作できるように、インフラストラクチャを提供するコードを実装するコードです。</span><span class="sxs-lookup"><span data-stu-id="52027-110">The order processing stage orchestrations contain two kinds of code: code that implements the business process and code that provides the infrastructure so that it can operate in the solution.</span></span> <span data-ttu-id="52027-111">ステージ オーケストレーションの両方で**CableOrder1**と**CableOrder2**、ビジネス プロセス コード グループ図形内のラベルは「ビジネス処理します」。</span><span class="sxs-lookup"><span data-stu-id="52027-111">In both of the stage orchestrations, **CableOrder1** and **CableOrder2**, the business process code is inside a group shape labeled "Business Processing."</span></span>  
  
 <span data-ttu-id="52027-112">新しい段階を作成する最も簡単な方法では、登録、「ビジネス プロセス」グループ内のコードをコードに置き換えますをインフラストラクチャ コードをそのまま残す段階の 1 つをコピーします。</span><span class="sxs-lookup"><span data-stu-id="52027-112">The easiest way to create a new stage is to copy one of the stages, replace the code in the "Business Processing" group with your code, and leave the infrastructure code intact.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52027-113">**CableOrder2**オーケストレーションは、「ビジネス プロセス」の 2 つのグループ、2 番目は Update History Send 図形です。</span><span class="sxs-lookup"><span data-stu-id="52027-113">The **CableOrder2** orchestration has two "Business Processing" groups, the second around the Update History Send shape.</span></span> <span data-ttu-id="52027-114">送信図形は、効率的な送信スコープの一部です。</span><span class="sxs-lookup"><span data-stu-id="52027-114">The Send shape is part of an efficient send scope.</span></span> <span data-ttu-id="52027-115">(詳細についてを参照してください「向上パフォーマンスで入れ子になったスコープ」 [OrderBroker オーケストレーションで処理](../core/processing-in-the-orderbroker-orchestration.md))。グループ図形はスコープ図形の一部と重ねることができないので、2 番目のグループにはビジネス プロセス コードの一部であることを示すラベルが付けられます。</span><span class="sxs-lookup"><span data-stu-id="52027-115">(For more information, see "Improving Performance with Nested Scopes" in [Processing in the OrderBroker Orchestration](../core/processing-in-the-orderbroker-orchestration.md).) Because a Group shape cannot overlap part of a scope shape, the second group is labeled to indicate it is part of the business process code.</span></span>  
  
 <span data-ttu-id="52027-116">新しいオーケストレーションのフィルタ式に連番を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52027-116">You must set the filter expression on the new orchestration to its number in the sequence.</span></span> <span data-ttu-id="52027-117">**OrderManager**ステージ番号が 1 つで始まり、各次のステージ (1, 2, 3...) の 1 つ増やしますを前提としています。</span><span class="sxs-lookup"><span data-stu-id="52027-117">The **OrderManager** assumes stage numbers begin with one and increase by one for each following stage (1, 2, 3 …).</span></span> <span data-ttu-id="52027-118">3 番目のステージをフィルタリングするには、フィルタ式を次のように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52027-118">To filter for a third stage, you would set the filter expression to the following:</span></span>  
  
 `(Microsoft.Samples.BizTalk.SouthridgeVidoe.Schemas.Stage == 3)`  
  
 <span data-ttu-id="52027-119">ソリューションは、BAM API を使用して、注文処理ステージなどソリューション内のイベントを追跡します。</span><span class="sxs-lookup"><span data-stu-id="52027-119">The solution uses the BAM API to track events in the solution, including the order processing stages.</span></span> <span data-ttu-id="52027-120">最初のステージで BAM アクティビティが開始され、最終ステージで終了します。</span><span class="sxs-lookup"><span data-stu-id="52027-120">The first stage starts the BAM activity; the final stage ends it.</span></span> <span data-ttu-id="52027-121">例外が発生した場合、ソリューション内のハンドラは BAM 関連アクティビティを終了させます。</span><span class="sxs-lookup"><span data-stu-id="52027-121">If there exceptions, the handlers in the solution end the BAM activities involved.</span></span> <span data-ttu-id="52027-122">BAM は不連続の操作を効果的にまとめて、1 つの連続したビューとして監視できるようにします。</span><span class="sxs-lookup"><span data-stu-id="52027-122">BAM effectively re-assembles the discontinuous operations into a continuous view for monitoring.</span></span>  
  
## <a name="changing-configuration"></a><span data-ttu-id="52027-123">構成の変更</span><span class="sxs-lookup"><span data-stu-id="52027-123">Changing Configuration</span></span>  
 <span data-ttu-id="52027-124">変更によりステージ数が増減する場合は、エンタープライズ シングル サインオン (SSO) シークレット ストアに格納された構成情報を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52027-124">If your changes increase or decrease the number of stages, you must change the configuration information stored in the Enterprise Single Sign-On (SSO) secret store.</span></span>  
  
 <span data-ttu-id="52027-125">アプリケーションを展開していない場合は、構成設定を変更することができます**TotalStages** CreateSouthridgeVideoApplication.cmd スクリプト ファイルにします。</span><span class="sxs-lookup"><span data-stu-id="52027-125">If you haven't deployed the application, you can modify the configuration setting for **TotalStages** in the CreateSouthridgeVideoApplication.cmd script file.</span></span> <span data-ttu-id="52027-126">展開時にスクリプトが実行されると、値が変更されます。</span><span class="sxs-lookup"><span data-stu-id="52027-126">The value will change when the script is run during deployment.</span></span>  
  
 <span data-ttu-id="52027-127">アプリケーションが展開済みである場合、SDK\Common\SsoApplicationConfig フォルダのコマンド ライン ユーティリティ BTSScnSSOApplicationConfig を実行することによって値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="52027-127">If you have already deployed the application, you can change value by running a command line utility, BTSScnSSOApplicationConfig, in the SDK\Common\SsoApplicationConfig folder.</span></span> <span data-ttu-id="52027-128">ステージの合計数を 3 に設定するには、次のコマンド ラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="52027-128">To set the total number of stages to three, you'd use the following command line:</span></span>  
  
 `BTSScnSSOApplicationConfig -set SouthRidgeVideo.CableOrder ConfigProperties TotalStages 3`  
  
 <span data-ttu-id="52027-129">構成値はキャッシュされるので、新しい値が有効になるには、キャッシュ更新間隔が経過するのを待つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="52027-129">Because the solution caches the configuration values, you must wait until the  refresh interval passes for the new value to take effect.</span></span>  
  
## <a name="versioning-schemas"></a><span data-ttu-id="52027-130">バージョン管理スキーマ</span><span class="sxs-lookup"><span data-stu-id="52027-130">Versioning Schemas</span></span>  
 <span data-ttu-id="52027-131">BizTalk は、スキーマを含むアセンブリの最新バージョンからスキーマを取得します。</span><span class="sxs-lookup"><span data-stu-id="52027-131">BizTalk takes a schema from the most recent version of the assembly containing it.</span></span> <span data-ttu-id="52027-132">つまり、スキーマの新しいバージョンを作成すると、スキーマのすべての旧バージョンが置き換えられるということです。</span><span class="sxs-lookup"><span data-stu-id="52027-132">This means that if you create a new version of a schema it completely replaces all previous versions of the schema.</span></span> <span data-ttu-id="52027-133">これは、短期間のトランザクションの場合に有効です。</span><span class="sxs-lookup"><span data-stu-id="52027-133">This works well when transactions are short-lived.</span></span> <span data-ttu-id="52027-134">ただし、ビジネス プロセス管理ソリューション内のトランザクションは有効期間が長い: 注文かかる場合があります、年を完了します。</span><span class="sxs-lookup"><span data-stu-id="52027-134">However, transactions in the Business Process Management solution are long-lived: an order may take up to a year to complete.</span></span>  
  
 <span data-ttu-id="52027-135">スキーマの複数のバージョンが使用される可能性を考慮して、ソリューションの各スキーマは名前空間にバージョン番号を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="52027-135">To allow for the possibility of using multiple versions of a schema being in use, each schema in the solution includes a version number in its namespace.</span></span> <span data-ttu-id="52027-136">たとえば、注文スキーマの名前空間は次のようになっています。</span><span class="sxs-lookup"><span data-stu-id="52027-136">For example, the namespace for the Order schema is as follows:</span></span>  
  
```  
http://Microsoft.Samples.BizTalk.SouthridgeVideo.Schemas.Order.v1  
```  
  
 <span data-ttu-id="52027-137">名前空間がスキーマを識別し、バージョン番号を含めることで名前空間がスキーマに対して一意になっているので、新しいスキーマを旧バージョンと区別できます。</span><span class="sxs-lookup"><span data-stu-id="52027-137">Because the namespace identifies the schema and inclusion of the version number makes the namespace unique to the schema, the new schema will be distinct from the older version.</span></span> <span data-ttu-id="52027-138">したがって、古いスキーマを置き換えずに新しいスキーマを使用できます。</span><span class="sxs-lookup"><span data-stu-id="52027-138">Thus, a new schema can be used without supplanting the old schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52027-139">参照</span><span class="sxs-lookup"><span data-stu-id="52027-139">See Also</span></span>  
 [<span data-ttu-id="52027-140">ビジネス プロセス管理ソリューションの開発</span><span class="sxs-lookup"><span data-stu-id="52027-140">Developing a Business Process Management Solution</span></span>](../core/developing-a-business-process-management-solution.md)