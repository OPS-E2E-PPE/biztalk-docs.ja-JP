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
ms.openlocfilehash: a853328e955f017a370b3025adb52d8f8706f796
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249928"
---
# <a name="extending-the-itinerary-designer"></a>Itinerary Designer を拡張します。
旅行プラン デザイナーでは、ビジュアルなドメイン固有言語 (DSL) は for Microsoft Visual Studio で使用するためのスケジュールのグラフィカルなモデリングができる、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。 デザイナーでは、開発者が新しい機能や新しい構成オプションを有効にするカスタム拡張機能を記述できますのさまざまな拡張機能ポイントを公開します。  
  

  
 **カスタム スケジュール オンランプ エクスポーターを作成します。**  
  
 旅行プラン デザイナーのアーキテクチャでは、旅行プラン モデル内のデータを永続化およびシリアル化モデルのカスタム エクスポートを作成するため。  
  
 **メッセージング サービスのカスタム エクステンダーを作成します。**  
  
 旅行プラン デザイナーのアーキテクチャでは、カスタム エクステンダーのプロパティを使用するためのプロパティ バッグに追加するメッセージング サービスで使用できるスケジュール サービス モデル要素を作成できます。  
  
 このようなエクステンダーを作成する方法のサンプルでは、次を参照してください。[をインストールすると、デザイナーの機能拡張サンプルを実行している](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)します。  
  
 **オーケストレーションに基づくスケジュール サービスのカスタム エクステンダーを作成します。**  
  
 旅行プラン デザイナーのアーキテクチャでは、カスタム エクステンダーのプロパティを使用するためのプロパティ バッグに追加するオーケストレーションに基づくスケジュール サービスで使用できるスケジュール サービス モデル要素を作成できます。  
  
 このようなエクステンダーを作成する方法のサンプルでは、次を参照してください。[をインストールすると、デザイナーの機能拡張サンプルを実行している](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)します。  
  
 **カスタム競合回避モジュールのエクステンダーを作成します。**  
  
 旅行プラン デザイナーのアーキテクチャでは、カスタム競合回避モジュールの構成のカスタム エクステンダーを作成できます。 これらのエクステンダーは、競合回避モジュールの特定のエクステンダー クラスのプロパティにマップされるに競合回避モジュールの接続文字列に名前/値ペアを構成するため、グラフィカル インターフェイスに提供します。  
  
 このようなエクステンダーを作成する方法のサンプルでは、次を参照してください。[をインストールすると、デザイナーの機能拡張サンプルを実行している](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)します。  
  
 **カスタム アダプターのプロパティのマニフェスト ファイルを作成します。**  
  
 カスタム アダプター プロバイダーを作成する場合は、エンドポイントの構成プロパティを表示するこれらの競合回避モジュール エクステンダーにアダプター プロバイダーのデザイナーのサポートも提供する必要があります。 デザイナー サポートを有効にするには、アダプター プロバイダーのマニフェスト ファイルを作成する必要があります。  
  
 アダプター プロバイダーのマニフェスト ファイルは、特定のアダプターのプロバイダー、その種類、説明、およびアセンブリが見つからないことができますに関連付けられたプロパティを定義します。 これらのマニフェスト ファイルは、一意の名前 (たとえば、FTPPropertyManifest.xml)、旅行プラン デザイナー バイナリ (たとえば、Microsoft.Practices.Itineary.DslPackage.dll) と同じフォルダーに配置する必要があります。  
  
 アダプター プロバイダー マニフェスト ファイル; の参照インスタンスを次に示しますカスタム マニフェスト ファイルは、同様に構造化する必要があります。  
  
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
  
 **カスタム フィルターのエクステンダーを作成します。**  
  
 旅行プラン デザイナーのアーキテクチャでは、カスタム フィルターの構成のカスタム エクステンダーを作成できます。 これらのエクステンダーは、特定のフィルターのエクステンダー クラスのプロパティにマップされるにフィルター接続文字列に名前/値ペアを構成するため、グラフィカル インターフェイスに提供します。  
  
- /Samples/Designer Extensibility Samples/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample  
  
- /サンプル/デザイナー機能拡張 Samples/Extenders.Resolvers.ResolverSample/Extenders.Resolvers.ResolverSample  
  
  **カスタム検証規則を作成します。**  
  
  旅行プラン デザイナーで導入された、最後に重要な拡張機能は、外部でに関してドメイン固有言語 (DSL) を指定し、モデルの検証ルールを実装するための検証メカニズムです。 メカニズム、DSL 検証フレームワークに「フック」と、ユーザーがクリックしたときに起動される**検証**または**すべて検証**モデルのショートカット メニューの します。 これは呼び出す DSL フレームワークの**DslCommandSet**旅行プラン デザイナーで、検証エンジンを呼び出すオブジェクト。  
  
  **ValidationEngine**クラスがエンタープライズ ライブラリ検証アプリケーション ブロックを使用してモデル要素の検証を実行し、Microsoft Visual Studio IDE の [エラー一覧] ウィンドウの検証エラーをログに記録します。 モデル内の要素の種類ごとに実行される検証は、Enterprise Library の構成ファイルで定義されます。 ファイルは、ある Ruleset.config の名前は、旅行プラン デザイナーのすべてのバイナリが配置されるバイナリ フォルダーにあります。 次の例は、構成ファイルのフラグメントと (検証コントロールをという名前)、2 つの検証規則が含まれています、 **UddiResolver** 1 つずつ、エクステンダー、 **ServerUrl**プロパティと 1 つずつ、 **ServiceKey**プロパティ。  
  
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
  
 各規則は、ルールを実装する検証コントロールを識別します。 旅行プラン デザイナーの検証コントロール クラスの大規模なセットが付属します。 デザイナーのバイナリ フォルダーで Microsoft.Practices.Modeling.Validation プロジェクトすべてにあります。  
  
 この検証メカニズムを使用して最終的な結果は、その行程デザイナーのユーザーが、指定された規則と検証コントロールを変更するか、独自の規則と検証コントロールを追加することで、モデルを検証する方法を変更することができます。 これは、開く、変更、再構築、および次の 2 つの手順を実行することで、Dsl を再デプロイせず実行できます。  
  
1.  検証コントロール クラスを作成し、バイナリ フォルダー内のライブラリに配置場所、 **Microsoft.Practices.Modeling.Validation.dll**ライブラリがあります。  
  
2.  検証コントロールを適用するどのようなモデル要素のクラスのプロパティを定義する Rules.config ファイルにエントリを追加します。