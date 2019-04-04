---
title: Itinerary Designer を拡張 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f26b825b-ebab-4dac-b7ed-0608c79e146a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fbe9e24560f8f00f4b3d806c76ebc326240add5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980747"
---
# <a name="extending-the-itinerary-designer"></a><span data-ttu-id="b4578-102">Itinerary Designer を拡張します。</span><span class="sxs-lookup"><span data-stu-id="b4578-102">Extending the Itinerary Designer</span></span>
<span data-ttu-id="b4578-103">旅行プラン デザイナーでは、ビジュアルなドメイン固有言語 (DSL) は for Microsoft Visual Studio で使用するためのスケジュールのグラフィカルなモデリングができる、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="b4578-103">The Itinerary Designer is a visual domain-specific language (DSL) for Microsoft Visual Studio that enables the graphical modeling of itineraries for use with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="b4578-104">デザイナーでは、開発者が新しい機能や新しい構成オプションを有効にするカスタム拡張機能を記述できますのさまざまな拡張機能ポイントを公開します。</span><span class="sxs-lookup"><span data-stu-id="b4578-104">The designer exposes various extension points for which developers can write custom extensions to enable new functionality and/or new configuration options.</span></span>  
  

  
 <span data-ttu-id="b4578-105">**カスタム スケジュール オンランプ エクスポーターを作成します。**</span><span class="sxs-lookup"><span data-stu-id="b4578-105">**Creating a Custom Itinerary Exporter**</span></span>  
  
 <span data-ttu-id="b4578-106">旅行プラン デザイナーのアーキテクチャでは、旅行プラン モデル内のデータを永続化およびシリアル化モデルのカスタム エクスポートを作成するため。</span><span class="sxs-lookup"><span data-stu-id="b4578-106">The architecture of the Itinerary Designer allows for the creation of custom model exporters that serialize and persist the data in an Itinerary model.</span></span>  
  
 <span data-ttu-id="b4578-107">**メッセージング サービスのカスタム エクステンダーを作成します。**</span><span class="sxs-lookup"><span data-stu-id="b4578-107">**Creating a Custom Extender for a Messaging Service**</span></span>  
  
 <span data-ttu-id="b4578-108">旅行プラン デザイナーのアーキテクチャでは、カスタム エクステンダーのプロパティを使用するためのプロパティ バッグに追加するメッセージング サービスで使用できるスケジュール サービス モデル要素を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b4578-108">The architecture of the Itinerary Designer allows you to create custom extenders for Itinerary Service model elements that can be used to add properties to the property bag for use by Messaging Services.</span></span>  
  
 <span data-ttu-id="b4578-109">このようなエクステンダーを作成する方法のサンプルでは、[をインストールすると、デザイナーの機能拡張サンプルを実行している](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4578-109">For a sample of how to create such an extender, see [Installing and Running the Designer Extensibility Sample](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md).</span></span>  
  
 <span data-ttu-id="b4578-110">**オーケストレーションに基づくスケジュール サービスのカスタム エクステンダーを作成します。**</span><span class="sxs-lookup"><span data-stu-id="b4578-110">**Creating a Custom Extender for an Orchestration-Based Itinerary Service**</span></span>  
  
 <span data-ttu-id="b4578-111">旅行プラン デザイナーのアーキテクチャでは、カスタム エクステンダーのプロパティを使用するためのプロパティ バッグに追加するオーケストレーションに基づくスケジュール サービスで使用できるスケジュール サービス モデル要素を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b4578-111">The architecture of the Itinerary Designer allows you to create custom extenders for Itinerary Service model elements that can be used to add properties to the property bag for use by orchestration-based itinerary services.</span></span>  
  
 <span data-ttu-id="b4578-112">このようなエクステンダーを作成する方法のサンプルでは、[をインストールすると、デザイナーの機能拡張サンプルを実行している](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4578-112">For a sample of how to create such an extender, see [Installing and Running the Designer Extensibility Sample](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md).</span></span>  
  
 <span data-ttu-id="b4578-113">**カスタム競合回避モジュールのエクステンダーを作成します。**</span><span class="sxs-lookup"><span data-stu-id="b4578-113">**Creating a Custom Resolver Extender**</span></span>  
  
 <span data-ttu-id="b4578-114">旅行プラン デザイナーのアーキテクチャでは、カスタム競合回避モジュールの構成のカスタム エクステンダーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b4578-114">The architecture of the Itinerary Designer allows you to create custom extenders for the configuration of custom resolvers.</span></span> <span data-ttu-id="b4578-115">これらのエクステンダーは、競合回避モジュールの特定のエクステンダー クラスのプロパティにマップされるに競合回避モジュールの接続文字列に名前/値ペアを構成するため、グラフィカル インターフェイスに提供します。</span><span class="sxs-lookup"><span data-stu-id="b4578-115">These extenders provide a graphical interface for configuring the name-value pairs in the resolver connection string, which map to properties in the specific resolver extender class.</span></span>  
  
 <span data-ttu-id="b4578-116">このようなエクステンダーを作成する方法のサンプルでは、[をインストールすると、デザイナーの機能拡張サンプルを実行している](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4578-116">For a sample of how to create such an extender, see [Installing and Running the Designer Extensibility Sample](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md).</span></span>  
  
 <span data-ttu-id="b4578-117">**カスタム アダプターのプロパティのマニフェスト ファイルを作成します。**</span><span class="sxs-lookup"><span data-stu-id="b4578-117">**Creating a Manifest File for Custom Adapter Properties**</span></span>  
  
 <span data-ttu-id="b4578-118">カスタム アダプター プロバイダーを作成する場合は、エンドポイントの構成プロパティを表示するこれらの競合回避モジュール エクステンダーにアダプター プロバイダーのデザイナーのサポートも提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4578-118">When creating a custom adapter provider, you must also provide designer support for the adapter provider to those resolver extenders that display an endpoint configuration property.</span></span> <span data-ttu-id="b4578-119">デザイナー サポートを有効にするには、アダプター プロバイダーのマニフェスト ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4578-119">To enable designer support, it is necessary to create an adapter provider manifest file.</span></span>  
  
 <span data-ttu-id="b4578-120">アダプター プロバイダーのマニフェスト ファイルは、特定のアダプターのプロバイダー、その種類、説明、およびアセンブリが見つからないことができますに関連付けられたプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="b4578-120">The adapter provider manifest file defines the properties associated with a specific adapter provider, their types, descriptions, and the assembly in which they can be found.</span></span> <span data-ttu-id="b4578-121">これらのマニフェスト ファイルは、一意の名前 (たとえば、FTPPropertyManifest.xml)、旅行プラン デザイナー バイナリ (たとえば、Microsoft.Practices.Itineary.DslPackage.dll) と同じフォルダーに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4578-121">These manifest files should be placed in the same folder as the Itinerary Designer binaries (for example, Microsoft.Practices.Itineary.DslPackage.dll) with a unique name (for example, FTPPropertyManifest.xml).</span></span>  
  
 <span data-ttu-id="b4578-122">アダプター プロバイダー マニフェスト ファイル; の参照インスタンスを次に示しますカスタム マニフェスト ファイルは、同様に構造化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4578-122">The following is a reference instance of an adapter provider manifest file; custom manifest files should be structured likewise.</span></span>  
  
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
  
 <span data-ttu-id="b4578-123">**カスタム フィルターのエクステンダーを作成します。**</span><span class="sxs-lookup"><span data-stu-id="b4578-123">**Creating a Custom Filter Extender**</span></span>  
  
 <span data-ttu-id="b4578-124">旅行プラン デザイナーのアーキテクチャでは、カスタム フィルターの構成のカスタム エクステンダーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b4578-124">The architecture of the Itinerary Designer allows you to create custom extenders for the configuration of custom filters.</span></span> <span data-ttu-id="b4578-125">これらのエクステンダーは、特定のフィルターのエクステンダー クラスのプロパティにマップされるにフィルター接続文字列に名前/値ペアを構成するため、グラフィカル インターフェイスに提供します。</span><span class="sxs-lookup"><span data-stu-id="b4578-125">These extenders provide a graphical interface for configuring the name-value pairs in the filter connection string, which map to properties in the specific filter extender class.</span></span>  
  
- <span data-ttu-id="b4578-126">/サンプル/デザイナー機能拡張 Samples/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample</span><span class="sxs-lookup"><span data-stu-id="b4578-126">/Samples/Designer Extensibility Samples/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample</span></span>  
  
- <span data-ttu-id="b4578-127">/サンプル/デザイナー機能拡張 Samples/Extenders.Resolvers.ResolverSample/Extenders.Resolvers.ResolverSample</span><span class="sxs-lookup"><span data-stu-id="b4578-127">/Samples/Designer Extensibility Samples/Extenders.Resolvers.ResolverSample/Extenders.Resolvers.ResolverSample</span></span>  
  
  <span data-ttu-id="b4578-128">**カスタム検証規則を作成します。**</span><span class="sxs-lookup"><span data-stu-id="b4578-128">**Creating Custom Validation Rules**</span></span>  
  
  <span data-ttu-id="b4578-129">旅行プラン デザイナーで導入された、最後に重要な拡張機能は、外部でに関してドメイン固有言語 (DSL) を指定し、モデルの検証ルールを実装するための検証メカニズムです。</span><span class="sxs-lookup"><span data-stu-id="b4578-129">The last significant extension introduced by the Itinerary Designer is a validation mechanism that allows you to externally, with respect to a domain-specific language (DSL), specify and implement the model validation rules.</span></span> <span data-ttu-id="b4578-130">メカニズム、DSL 検証フレームワークに「フック」と、ユーザーがクリックしたときに起動される**検証**または**すべて検証**モデルのショートカット メニューの します。</span><span class="sxs-lookup"><span data-stu-id="b4578-130">The mechanism "hooks into" the DSL validation framework and is activated when the user clicks **Validate** or **Validate all** on the shortcut menu of a model.</span></span> <span data-ttu-id="b4578-131">これは呼び出す DSL フレームワークの**DslCommandSet**旅行プラン デザイナーで、検証エンジンを呼び出すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b4578-131">This invokes the DSL framework's **DslCommandSet** object that, in turn, calls the validation engine in the Itinerary Designer.</span></span>  
  
  <span data-ttu-id="b4578-132">**ValidationEngine**クラスがエンタープライズ ライブラリ検証アプリケーション ブロックを使用してモデル要素の検証を実行し、Microsoft Visual Studio IDE の [エラー一覧] ウィンドウの検証エラーをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="b4578-132">The **ValidationEngine** class performs the model element validation using the Enterprise Library Validation Application Block and logs the validation errors to the Error List window in Microsoft Visual Studio IDE.</span></span> <span data-ttu-id="b4578-133">モデル内の要素の種類ごとに実行される検証は、Enterprise Library の構成ファイルで定義されます。</span><span class="sxs-lookup"><span data-stu-id="b4578-133">The validation that should be performed for each type of element in a model is defined in the Enterprise Library configuration file.</span></span> <span data-ttu-id="b4578-134">ファイルは、ある Ruleset.config の名前は、旅行プラン デザイナーのすべてのバイナリが配置されるバイナリ フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="b4578-134">The file is named Ruleset.config and is located in the binary folder where all the Itinerary Designer binaries are located.</span></span> <span data-ttu-id="b4578-135">次の例は、構成ファイルのフラグメントと (検証コントロールをという名前)、2 つの検証規則が含まれています、 **UddiResolver** 1 つずつ、エクステンダー、 **ServerUrl**プロパティと 1 つずつ、 **ServiceKey**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="b4578-135">The following example is a fragment of the configuration file and includes two validation rules (named validators) for the **UddiResolver** extender, one for the **ServerUrl** property and one for the **ServiceKey** property.</span></span>  
  
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
  
 <span data-ttu-id="b4578-136">各規則は、ルールを実装する検証コントロールを識別します。</span><span class="sxs-lookup"><span data-stu-id="b4578-136">Each rule identifies the validator that implements the rule.</span></span> <span data-ttu-id="b4578-137">旅行プラン デザイナーの検証コントロール クラスの大規模なセットが付属します。</span><span class="sxs-lookup"><span data-stu-id="b4578-137">The Itinerary Designer comes with a large set of validator classes.</span></span> <span data-ttu-id="b4578-138">デザイナーのバイナリ フォルダーで Microsoft.Practices.Modeling.Validation プロジェクトすべてにあります。</span><span class="sxs-lookup"><span data-stu-id="b4578-138">They are all in the Microsoft.Practices.Modeling.Validation project in the Designer binary folder.</span></span>  
  
 <span data-ttu-id="b4578-139">この検証メカニズムを使用して最終的な結果は、その行程デザイナーのユーザーが、指定された規則と検証コントロールを変更するか、独自の規則と検証コントロールを追加することで、モデルを検証する方法を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="b4578-139">The final result of using this validation mechanism is that Itinerary Designer users can modify how the models are validated by changing the provided rules and validators or by adding their own rules and validators.</span></span> <span data-ttu-id="b4578-140">これは、開く、変更、再構築、および次の 2 つの手順を実行することで、Dsl を再デプロイせず実行できます。</span><span class="sxs-lookup"><span data-stu-id="b4578-140">This can be done without opening, modifying, rebuilding, and re-deploying the DSLs by performing the following two steps:</span></span>  
  
1.  <span data-ttu-id="b4578-141">検証コントロール クラスを作成し、バイナリ フォルダー内のライブラリに配置場所、 **Microsoft.Practices.Modeling.Validation.dll**ライブラリがあります。</span><span class="sxs-lookup"><span data-stu-id="b4578-141">Create a validator class and put it in a library inside the binary folder where the **Microsoft.Practices.Modeling.Validation.dll** library is located.</span></span>  
  
2.  <span data-ttu-id="b4578-142">検証コントロールを適用するどのようなモデル要素のクラスのプロパティを定義する Rules.config ファイルにエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="b4578-142">Add entries to the Rules.config file to define what property of what model element class the validator should be applied.</span></span>