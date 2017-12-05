---
title: "Itinerary Designer を拡張 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f26b825b-ebab-4dac-b7ed-0608c79e146a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78490c7b6447ddb097c0ca61154aab20c44086c3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="extending-the-itinerary-designer"></a><span data-ttu-id="384f7-102">Itinerary Designer を拡張します。</span><span class="sxs-lookup"><span data-stu-id="384f7-102">Extending the Itinerary Designer</span></span>
<span data-ttu-id="384f7-103">Microsoft Visual Studio で使用するための日程のグラフィカルなモデリングができるようにするには、行程デザイナーがビジュアルなドメイン固有言語 (DSL)、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="384f7-103">The Itinerary Designer is a visual domain-specific language (DSL) for Microsoft Visual Studio that enables the graphical modeling of itineraries for use with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="384f7-104">デザイナーでは、開発者が新しい機能や新しい構成オプションを有効にするカスタム拡張機能を記述できるさまざまな拡張ポイントを公開します。</span><span class="sxs-lookup"><span data-stu-id="384f7-104">The designer exposes various extension points for which developers can write custom extensions to enable new functionality and/or new configuration options.</span></span>  
  

  
 <span data-ttu-id="384f7-105">**カスタムの Itinerary エクスポーターを作成します。**</span><span class="sxs-lookup"><span data-stu-id="384f7-105">**Creating a Custom Itinerary Exporter**</span></span>  
  
 <span data-ttu-id="384f7-106">行程デザイナーのアーキテクチャではシリアル化、行程モデル内のデータを保持するカスタム モデル エクスポーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="384f7-106">The architecture of the Itinerary Designer allows for the creation of custom model exporters that serialize and persist the data in an Itinerary model.</span></span>  
  
 <span data-ttu-id="384f7-107">**メッセージング サービスのカスタムのエクステンダーを作成します。**</span><span class="sxs-lookup"><span data-stu-id="384f7-107">**Creating a Custom Extender for a Messaging Service**</span></span>  
  
 <span data-ttu-id="384f7-108">行程デザイナーのアーキテクチャでは、プロパティを使用するためのプロパティ バッグに追加するメッセージング サービスで使用できる行程サービス モデル要素のカスタムのエクステンダーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="384f7-108">The architecture of the Itinerary Designer allows you to create custom extenders for Itinerary Service model elements that can be used to add properties to the property bag for use by Messaging Services.</span></span>  
  
 <span data-ttu-id="384f7-109">このような extender を作成する方法のサンプルは、次を参照してください。[をインストールすると、デザイナーの機能拡張のサンプルを実行している](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="384f7-109">For a sample of how to create such an extender, see [Installing and Running the Designer Extensibility Sample](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md).</span></span>  
  
 <span data-ttu-id="384f7-110">**オーケストレーションに基づく Itinerary サービスのカスタムのエクステンダーを作成します。**</span><span class="sxs-lookup"><span data-stu-id="384f7-110">**Creating a Custom Extender for an Orchestration-Based Itinerary Service**</span></span>  
  
 <span data-ttu-id="384f7-111">行程デザイナーのアーキテクチャでは、プロパティを使用するためのプロパティ バッグに追加するオーケストレーションに基づく itinerary サービスで使用できる行程サービス モデル要素のカスタムのエクステンダーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="384f7-111">The architecture of the Itinerary Designer allows you to create custom extenders for Itinerary Service model elements that can be used to add properties to the property bag for use by orchestration-based itinerary services.</span></span>  
  
 <span data-ttu-id="384f7-112">このような extender を作成する方法のサンプルは、次を参照してください。[をインストールすると、デザイナーの機能拡張のサンプルを実行している](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="384f7-112">For a sample of how to create such an extender, see [Installing and Running the Designer Extensibility Sample](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md).</span></span>  
  
 <span data-ttu-id="384f7-113">**カスタム競合回避モジュールのエクステンダーを作成します。**</span><span class="sxs-lookup"><span data-stu-id="384f7-113">**Creating a Custom Resolver Extender**</span></span>  
  
 <span data-ttu-id="384f7-114">行程デザイナーのアーキテクチャでは、カスタム競合回避モジュールの構成のカスタムのエクステンダーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="384f7-114">The architecture of the Itinerary Designer allows you to create custom extenders for the configuration of custom resolvers.</span></span> <span data-ttu-id="384f7-115">これらのエクステンダー グラフィカル インターフェイスを提供競合回避モジュールの接続文字列の名前と値のペアを構成するために特定の競合回避モジュールの拡張クラスのプロパティにマップされます。</span><span class="sxs-lookup"><span data-stu-id="384f7-115">These extenders provide a graphical interface for configuring the name-value pairs in the resolver connection string, which map to properties in the specific resolver extender class.</span></span>  
  
 <span data-ttu-id="384f7-116">このような extender を作成する方法のサンプルは、次を参照してください。[をインストールすると、デザイナーの機能拡張のサンプルを実行している](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="384f7-116">For a sample of how to create such an extender, see [Installing and Running the Designer Extensibility Sample](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md).</span></span>  
  
 <span data-ttu-id="384f7-117">**カスタム アダプターのプロパティのマニフェスト ファイルを作成します。**</span><span class="sxs-lookup"><span data-stu-id="384f7-117">**Creating a Manifest File for Custom Adapter Properties**</span></span>  
  
 <span data-ttu-id="384f7-118">カスタム アダプター プロバイダーを作成するときに、エンドポイントの構成プロパティを表示するこれらの競合回避モジュール エクステンダー アダプター プロバイダーのデザイナーのサポートも提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="384f7-118">When creating a custom adapter provider, you must also provide designer support for the adapter provider to those resolver extenders that display an endpoint configuration property.</span></span> <span data-ttu-id="384f7-119">デザイナーのサポートを有効にするには、アダプター プロバイダーのマニフェスト ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="384f7-119">To enable designer support, it is necessary to create an adapter provider manifest file.</span></span>  
  
 <span data-ttu-id="384f7-120">アダプター プロバイダーのマニフェスト ファイルでは、特定のアダプター プロバイダー、それらの種類、説明、および見つかった、アセンブリに関連付けられたプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="384f7-120">The adapter provider manifest file defines the properties associated with a specific adapter provider, their types, descriptions, and the assembly in which they can be found.</span></span> <span data-ttu-id="384f7-121">これらのマニフェスト ファイルは、一意の名前 (たとえば、FTPPropertyManifest.xml) 行程デザイナー バイナリ (たとえば、Microsoft.Practices.Itineary.DslPackage.dll) と同じフォルダーに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="384f7-121">These manifest files should be placed in the same folder as the Itinerary Designer binaries (for example, Microsoft.Practices.Itineary.DslPackage.dll) with a unique name (for example, FTPPropertyManifest.xml).</span></span>  
  
 <span data-ttu-id="384f7-122">アダプター プロバイダー マニフェスト ファイル; の参照インスタンスを次に示しますカスタム マニフェスト ファイルを同様に構造化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="384f7-122">The following is a reference instance of an adapter provider manifest file; custom manifest files should be structured likewise.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<adapterPropertyManifest adapterName="FTP">  
     <aliases>  
          <alias name="globalPropertySchemas" value="Microsoft.BizTalk.GlobalPropertySchemas, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
     </aliases>  
     <properties>  
          <property name="UserName" type="FTP.UserName" description="The user name for the connection." encrypted="true" assembly="globalPropertySchemas" />  
          <property name="Password" type="FTP.Password" description="The password for the conection." encrypted="true" assembly="globalPropertySchemas" />  
          <property name="MaxConnections" type="FTP.MaxConnections" description="The maximun number of connections." assembly="globalPropertySchemas" />  
          <property name="EventArgs" type="System.EventArgs" assembly="mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
     </properties>  
</adapterPropertyManifest>  
```  
  
 <span data-ttu-id="384f7-123">**カスタム フィルターのエクステンダーを作成します。**</span><span class="sxs-lookup"><span data-stu-id="384f7-123">**Creating a Custom Filter Extender**</span></span>  
  
 <span data-ttu-id="384f7-124">行程デザイナーのアーキテクチャでは、カスタム フィルターの構成のカスタムのエクステンダーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="384f7-124">The architecture of the Itinerary Designer allows you to create custom extenders for the configuration of custom filters.</span></span> <span data-ttu-id="384f7-125">これらエクステンダー グラフィカル インターフェイスを提供フィルター接続文字列の名前と値のペアを構成するために特定のフィルターの extender クラスのプロパティにマップします。</span><span class="sxs-lookup"><span data-stu-id="384f7-125">These extenders provide a graphical interface for configuring the name-value pairs in the filter connection string, which map to properties in the specific filter extender class.</span></span>  
  
-   <span data-ttu-id="384f7-126">/サンプル/デザイナー拡張 Samples/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample</span><span class="sxs-lookup"><span data-stu-id="384f7-126">/Samples/Designer Extensibility Samples/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample</span></span>  
  
-   <span data-ttu-id="384f7-127">/サンプル/デザイナー拡張 Samples/Extenders.Resolvers.ResolverSample/Extenders.Resolvers.ResolverSample</span><span class="sxs-lookup"><span data-stu-id="384f7-127">/Samples/Designer Extensibility Samples/Extenders.Resolvers.ResolverSample/Extenders.Resolvers.ResolverSample</span></span>  
  
 <span data-ttu-id="384f7-128">**カスタム検証規則を作成します。**</span><span class="sxs-lookup"><span data-stu-id="384f7-128">**Creating Custom Validation Rules**</span></span>  
  
 <span data-ttu-id="384f7-129">行程デザイナーによって導入された、最後に大幅な拡張機能は、外部的に関してドメイン固有言語 (DSL) を指定して、モデルの検証規則を実装することができますを検証メカニズムです。</span><span class="sxs-lookup"><span data-stu-id="384f7-129">The last significant extension introduced by the Itinerary Designer is a validation mechanism that allows you to externally, with respect to a domain-specific language (DSL), specify and implement the model validation rules.</span></span> <span data-ttu-id="384f7-130">メカニズム「フック関数に」DSL 検証フレームワークと、ユーザーがクリックしたときに起動**検証**または**すべて検証**モデルのショートカット メニューの します。</span><span class="sxs-lookup"><span data-stu-id="384f7-130">The mechanism "hooks into" the DSL validation framework and is activated when the user clicks **Validate** or **Validate all** on the shortcut menu of a model.</span></span> <span data-ttu-id="384f7-131">DSL フレームワークが呼び出されます**DslCommandSet**行程デザイナーでさらに、検証エンジンを呼び出すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="384f7-131">This invokes the DSL framework's **DslCommandSet** object that, in turn, calls the validation engine in the Itinerary Designer.</span></span>  
  
 <span data-ttu-id="384f7-132">**ValidationEngine**クラスは、Enterprise Library 検証 Application Block を使用してモデル要素の検証を実行して、Microsoft Visual Studio IDE の [エラー一覧] ウィンドウに、検証エラーをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="384f7-132">The **ValidationEngine** class performs the model element validation using the Enterprise Library Validation Application Block and logs the validation errors to the Error List window in Microsoft Visual Studio IDE.</span></span> <span data-ttu-id="384f7-133">モデル内の要素の種類ごとに実行される検証は、エンタープライズ ライブラリの構成ファイルで定義されます。</span><span class="sxs-lookup"><span data-stu-id="384f7-133">The validation that should be performed for each type of element in a model is defined in the Enterprise Library configuration file.</span></span> <span data-ttu-id="384f7-134">ファイルは、Ruleset.config の名前は、行程デザイナーのすべてのバイナリが配置されているバイナリ フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="384f7-134">The file is named Ruleset.config and is located in the binary folder where all the Itinerary Designer binaries are located.</span></span> <span data-ttu-id="384f7-135">次の例は、構成ファイルのフラグメントと (という名前の検証コントロール)、2 つの検証規則が含まれています、 **UddiResolver** extender、1 つ、 **ServerUrl**プロパティと、用**ServiceKey**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="384f7-135">The following example is a fragment of the configuration file and includes two validation rules (named validators) for the **UddiResolver** extender, one for the **ServerUrl** property and one for the **ServiceKey** property.</span></span>  
  
```  
<!--   
UddiResolver  
-->  
<type assemblyName="Microsoft.Practices.Services.Extenders.Resolvers.UDDI"  
 name="Microsoft.Practices.Services.Extenders.Resolvers.UDDI.UddiResolver">  
<ruleset name="Menu">  
<properties>  
<property name="ServerUrl">  
<validator type="Microsoft.Practices.Modeling.Validation.NotEmptyStringValidator, Microsoft.Practices.Modeling.Validation"  
          messageTemplate="The '{1}' property value should not be empty or null."  
          name="UddiResolver.ServerUrl not null validator"/>  
</property>  
<property name="ServiceKey">  
<validator type="Microsoft.Practices.Modeling.Validation.NotEmptyStringValidator, Microsoft.Practices.Modeling.Validation"  
          messageTemplate="The '{1}' property value should not be empty or null."  
          name="UddiResolver.ServiceKey not null validator"/>  
</property>  
</properties>  
</ruleset>  
</type>  
```  
  
 <span data-ttu-id="384f7-136">各規則は、検証規則を実装するコントロールを識別します。</span><span class="sxs-lookup"><span data-stu-id="384f7-136">Each rule identifies the validator that implements the rule.</span></span> <span data-ttu-id="384f7-137">行程デザイナーの検証コントロール クラスの大規模なセットが付属します。</span><span class="sxs-lookup"><span data-stu-id="384f7-137">The Itinerary Designer comes with a large set of validator classes.</span></span> <span data-ttu-id="384f7-138">これらがすべてデザイナー バイナリ フォルダーに Microsoft.Practices.Modeling.Validation プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="384f7-138">They are all in the Microsoft.Practices.Modeling.Validation project in the Designer binary folder.</span></span>  
  
 <span data-ttu-id="384f7-139">この検証メカニズムを使用して最終的な結果とは、ユーザーが、指定された規則と検証コントロールを変更するか、独自の規則と検証コントロールを追加することによって、モデルを検証する方法を変更することができます、行程デザイナーです。</span><span class="sxs-lookup"><span data-stu-id="384f7-139">The final result of using this validation mechanism is that Itinerary Designer users can modify how the models are validated by changing the provided rules and validators or by adding their own rules and validators.</span></span> <span data-ttu-id="384f7-140">これは、開く、変更、再構築、および次の 2 つの手順を実行することによって、Dsl を再デプロイすることがなく実行できます。</span><span class="sxs-lookup"><span data-stu-id="384f7-140">This can be done without opening, modifying, rebuilding, and re-deploying the DSLs by performing the following two steps:</span></span>  
  
1.  <span data-ttu-id="384f7-141">検証クラスを作成し、バイナリ フォルダー内のライブラリに格納場所、 **Microsoft.Practices.Modeling.Validation.dll**ライブラリがあります。</span><span class="sxs-lookup"><span data-stu-id="384f7-141">Create a validator class and put it in a library inside the binary folder where the **Microsoft.Practices.Modeling.Validation.dll** library is located.</span></span>  
  
2.  <span data-ttu-id="384f7-142">検証コントロールを適用するモデル要素クラスのプロパティを定義する Rules.config ファイルにエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="384f7-142">Add entries to the Rules.config file to define what property of what model element class the validator should be applied.</span></span>