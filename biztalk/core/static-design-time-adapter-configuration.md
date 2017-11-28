---
title: "静的デザイン時アダプター構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 332723a4-e39d-43f5-af4d-bf9f56496535
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8337e4f53afe22ccbde0e1d1d2a6437d280011d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="static-design-time-adapter-configuration"></a><span data-ttu-id="d51ad-102">静的デザイン時アダプター構成</span><span class="sxs-lookup"><span data-stu-id="d51ad-102">Static Design-Time Adapter Configuration</span></span>
<span data-ttu-id="d51ad-103">アダプターのデザイン時部分では、使用可能なすべてのプロパティを定義し、ユーザー入力を検証します。</span><span class="sxs-lookup"><span data-stu-id="d51ad-103">The design-time part of the adapter is responsible for defining all the available properties and for validating user input.</span></span> <span data-ttu-id="d51ad-104">アダプターの静的デザイン時構成では、既定のユーザー インターフェイス (UI) を使用して、そのプロパティを表示および編集します。</span><span class="sxs-lookup"><span data-stu-id="d51ad-104">In a static design-time configuration the adapter uses the default user interface (UI) for displaying and editing its properties.</span></span>  
  
 <span data-ttu-id="d51ad-105">このセクションでは、カスタム アダプターの静的デザイン時構成機能を実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d51ad-105">This section explains how to implement static design-time configuration capability for your custom adapter.</span></span> <span data-ttu-id="d51ad-106">どのように変更するかは、アダプターが通信するアプリケーションの要件、およびアダプターが実装するロジックに基づいて決定します。</span><span class="sxs-lookup"><span data-stu-id="d51ad-106">The changes you decide to make will be based on the needs of the applications with which the adapter communicates and the logic that the adapter needs to implement.</span></span> <span data-ttu-id="d51ad-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプでこれらの手順や背景情報が詳しく説明されている場合は、該当するセクションへのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d51ad-107">Links to sections of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help that describe these steps in more detail or provide additional background are provided when available.</span></span> <span data-ttu-id="d51ad-108">また、サンプル ファイルのアダプター ドキュメント内で、関連する例が記載されている部分を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="d51ad-108">Additionally it calls out the places in the sample file adapter documentation that provide relevant examples.</span></span>  
  
## <a name="guidelines-for-the-static-development-process"></a><span data-ttu-id="d51ad-109">静的な開発プロセスのガイドライン</span><span class="sxs-lookup"><span data-stu-id="d51ad-109">Guidelines for the Static Development Process</span></span>  
 <span data-ttu-id="d51ad-110">以下に、静的デザイン時機能をアダプターに組み込む場合の推奨事項を示します。</span><span class="sxs-lookup"><span data-stu-id="d51ad-110">The following list provides recommendations for building static design-time functionality into your adapter.</span></span> <span data-ttu-id="d51ad-111">開発中は、これらの手順をすべて実行する必要はありません。また、記述されているとおりの順序で実行する必要もありません。</span><span class="sxs-lookup"><span data-stu-id="d51ad-111">During development you may not need to do all of these steps, nor execute them in a rigid sequence.</span></span>  
  
1.  <span data-ttu-id="d51ad-112">アダプター構成要件、および設定する必要がある構成パラメーターの一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="d51ad-112">Create a list of adapter configuration requirements and configuration parameters that you need to set.</span></span> <span data-ttu-id="d51ad-113">すべての受信場所と送信ポートでグローバルに使用するパラメーターは、ハンドラー スキーマ構成ファイルで指定します。</span><span class="sxs-lookup"><span data-stu-id="d51ad-113">If the parameters are globally used for all receive locations and send ports, specify them in the handler schema configuration file.</span></span> <span data-ttu-id="d51ad-114">特定のポートまたは特定の場所で使用するパラメーターは、送信ポート構成ファイルと受信場所構成ファイルでそれぞれ構成します。</span><span class="sxs-lookup"><span data-stu-id="d51ad-114">If they are port or location specific, configure them in the send port and receive location configuration files.</span></span>  
  
2.  <span data-ttu-id="d51ad-115">アダプターのプロパティ ページを新しい構成パラメーターに対応するように変更します。</span><span class="sxs-lookup"><span data-stu-id="d51ad-115">Modify the adapter property pages to account for any new configuration parameters.</span></span> <span data-ttu-id="d51ad-116">この手順については、次を参照してください。[アダプター構成スキーマ](../core/adapter-configuration-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="d51ad-116">For information about this step, see [Adapter Configuration Schemas](../core/adapter-configuration-schemas.md).</span></span>  
  
3.  <span data-ttu-id="d51ad-117">アダプター メタデータの追加ウィザードを使用して、スキーマ カテゴリのツリー ビューを変更します。</span><span class="sxs-lookup"><span data-stu-id="d51ad-117">Modify the tree view of the schema categories by using the Add Adapter Metadata Wizard.</span></span> <span data-ttu-id="d51ad-118">この手順の詳細については、次を参照してください[アダプター メタデータの追加ウィザードのスキーマ カテゴリ。](../core/schema-categories-in-the-add-adapter-metadata-wizard.md)</span><span class="sxs-lookup"><span data-stu-id="d51ad-118">For more information about this step, see [Schema Categories in the Add Adapter Metadata Wizard](../core/schema-categories-in-the-add-adapter-metadata-wizard.md)</span></span>  
  
4.  <span data-ttu-id="d51ad-119">スキーマが Web サービス記述言語 (WSDL) ファイルとして返されるようにサンプル コードを修正します。</span><span class="sxs-lookup"><span data-stu-id="d51ad-119">Modify the sample code to return schemas as Web Services Description Language (WSDL) files.</span></span> <span data-ttu-id="d51ad-120">この手順の詳細については、次を参照してください。[静的アダプターの IStaticAdapterConfig インターフェイス](../core/static-adapter-istaticadapterconfig-interface.md)です。</span><span class="sxs-lookup"><span data-stu-id="d51ad-120">For more information about this step, see [Static Adapter IStaticAdapterConfig Interface](../core/static-adapter-istaticadapterconfig-interface.md).</span></span>  
  
5.  <span data-ttu-id="d51ad-121">既存の WSDL ファイルを変更するか、新しい WSDL ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d51ad-121">Modify the existing WSDL files or create new WSDL files.</span></span> <span data-ttu-id="d51ad-122">この手順の詳細については、次を参照してください。[アダプター WSDL ファイル](../core/adapter-wsdl-files.md)です。</span><span class="sxs-lookup"><span data-stu-id="d51ad-122">For more information about this step, see [Adapter WSDL Files](../core/adapter-wsdl-files.md).</span></span>  
  
6.  <span data-ttu-id="d51ad-123">サンプル コードを変更して、WSDL ファイルに含まれていないアダプターによって必要とされている追加の XSD ファイルを返します。</span><span class="sxs-lookup"><span data-stu-id="d51ad-123">Modify the sample code to return additional XSD files needed by the adapter that are not included in the WSDL files.</span></span> <span data-ttu-id="d51ad-124">この手順の詳細については、次を参照してください。[アダプターの GetSchema メソッド](../core/adapter-getschema-method.md)です。</span><span class="sxs-lookup"><span data-stu-id="d51ad-124">For more information about this step, see [Adapter GetSchema Method](../core/adapter-getschema-method.md).</span></span>  
  
7.  <span data-ttu-id="d51ad-125">アダプターのレジストリ キーを変更して、アダプターのレジストリ ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="d51ad-125">Modify the adapter registry keys and run the adapter registry file.</span></span> <span data-ttu-id="d51ad-126">この手順の詳細については、次を参照してください。[アダプターの登録ファイル](../core/adapter-registration-file.md)です。</span><span class="sxs-lookup"><span data-stu-id="d51ad-126">For more information about this step, see [Adapter Registration File](../core/adapter-registration-file.md).</span></span>  
  
8.  <span data-ttu-id="d51ad-127">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に静的アダプターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d51ad-127">Install the static adapter into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d51ad-128">この手順の詳細については、次を参照してください。[アダプターを BizTalk Server インストール](../core/install-the-adapter-into-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="d51ad-128">For more information about this step, see [Install the Adapter into BizTalk Server](../core/install-the-adapter-into-biztalk-server.md).</span></span>  
  
9. <span data-ttu-id="d51ad-129">アダプターのプロパティ ページに対して行われた変更をテストします。</span><span class="sxs-lookup"><span data-stu-id="d51ad-129">Test the changes made to the adapter property pages.</span></span> <span data-ttu-id="d51ad-130">アダプターを再ビルドして、アダプター メタデータの追加ウィザードに表示される UI をテストします。</span><span class="sxs-lookup"><span data-stu-id="d51ad-130">Rebuild the adapter to test the UI that appears in the Add Adapter Metadata Wizard.</span></span> <span data-ttu-id="d51ad-131">この手順の詳細については、次を参照してください[のビルドとアダプター プロジェクトのテスト。](../core/build-and-test-the-adapter-project.md)</span><span class="sxs-lookup"><span data-stu-id="d51ad-131">For more information about this step, see [Build and Test the Adapter Project](../core/build-and-test-the-adapter-project.md)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d51ad-132">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d51ad-132">In This Section</span></span>  
  
-   [<span data-ttu-id="d51ad-133">静的アダプターの IStaticAdapterConfig インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d51ad-133">Static Adapter IStaticAdapterConfig Interface</span></span>](../core/static-adapter-istaticadapterconfig-interface.md)  
  
-   [<span data-ttu-id="d51ad-134">スキーマのカテゴリ、アダプター メタデータのウィザードの追加</span><span class="sxs-lookup"><span data-stu-id="d51ad-134">Schema Categories in the Add Adapter Metadata Wizard</span></span>](../core/schema-categories-in-the-add-adapter-metadata-wizard.md)