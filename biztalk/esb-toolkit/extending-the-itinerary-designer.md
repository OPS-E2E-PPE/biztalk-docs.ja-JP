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
# <a name="extending-the-itinerary-designer"></a>Itinerary Designer を拡張します。
Microsoft Visual Studio で使用するための日程のグラフィカルなモデリングができるようにするには、行程デザイナーがビジュアルなドメイン固有言語 (DSL)、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。 デザイナーでは、開発者が新しい機能や新しい構成オプションを有効にするカスタム拡張機能を記述できるさまざまな拡張ポイントを公開します。  
  

  
 **カスタムの Itinerary エクスポーターを作成します。**  
  
 行程デザイナーのアーキテクチャではシリアル化、行程モデル内のデータを保持するカスタム モデル エクスポーターを作成します。  
  
 **メッセージング サービスのカスタムのエクステンダーを作成します。**  
  
 行程デザイナーのアーキテクチャでは、プロパティを使用するためのプロパティ バッグに追加するメッセージング サービスで使用できる行程サービス モデル要素のカスタムのエクステンダーを作成することができます。  
  
 このような extender を作成する方法のサンプルは、次を参照してください。[をインストールすると、デザイナーの機能拡張のサンプルを実行している](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)です。  
  
 **オーケストレーションに基づく Itinerary サービスのカスタムのエクステンダーを作成します。**  
  
 行程デザイナーのアーキテクチャでは、プロパティを使用するためのプロパティ バッグに追加するオーケストレーションに基づく itinerary サービスで使用できる行程サービス モデル要素のカスタムのエクステンダーを作成することができます。  
  
 このような extender を作成する方法のサンプルは、次を参照してください。[をインストールすると、デザイナーの機能拡張のサンプルを実行している](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)です。  
  
 **カスタム競合回避モジュールのエクステンダーを作成します。**  
  
 行程デザイナーのアーキテクチャでは、カスタム競合回避モジュールの構成のカスタムのエクステンダーを作成することができます。 これらのエクステンダー グラフィカル インターフェイスを提供競合回避モジュールの接続文字列の名前と値のペアを構成するために特定の競合回避モジュールの拡張クラスのプロパティにマップされます。  
  
 このような extender を作成する方法のサンプルは、次を参照してください。[をインストールすると、デザイナーの機能拡張のサンプルを実行している](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)です。  
  
 **カスタム アダプターのプロパティのマニフェスト ファイルを作成します。**  
  
 カスタム アダプター プロバイダーを作成するときに、エンドポイントの構成プロパティを表示するこれらの競合回避モジュール エクステンダー アダプター プロバイダーのデザイナーのサポートも提供する必要があります。 デザイナーのサポートを有効にするには、アダプター プロバイダーのマニフェスト ファイルを作成する必要があります。  
  
 アダプター プロバイダーのマニフェスト ファイルでは、特定のアダプター プロバイダー、それらの種類、説明、および見つかった、アセンブリに関連付けられたプロパティを定義します。 これらのマニフェスト ファイルは、一意の名前 (たとえば、FTPPropertyManifest.xml) 行程デザイナー バイナリ (たとえば、Microsoft.Practices.Itineary.DslPackage.dll) と同じフォルダーに配置する必要があります。  
  
 アダプター プロバイダー マニフェスト ファイル; の参照インスタンスを次に示しますカスタム マニフェスト ファイルを同様に構造化する必要があります。  
  
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
  
 行程デザイナーのアーキテクチャでは、カスタム フィルターの構成のカスタムのエクステンダーを作成することができます。 これらエクステンダー グラフィカル インターフェイスを提供フィルター接続文字列の名前と値のペアを構成するために特定のフィルターの extender クラスのプロパティにマップします。  
  
-   /サンプル/デザイナー拡張 Samples/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample  
  
-   /サンプル/デザイナー拡張 Samples/Extenders.Resolvers.ResolverSample/Extenders.Resolvers.ResolverSample  
  
 **カスタム検証規則を作成します。**  
  
 行程デザイナーによって導入された、最後に大幅な拡張機能は、外部的に関してドメイン固有言語 (DSL) を指定して、モデルの検証規則を実装することができますを検証メカニズムです。 メカニズム「フック関数に」DSL 検証フレームワークと、ユーザーがクリックしたときに起動**検証**または**すべて検証**モデルのショートカット メニューの します。 DSL フレームワークが呼び出されます**DslCommandSet**行程デザイナーでさらに、検証エンジンを呼び出すオブジェクト。  
  
 **ValidationEngine**クラスは、Enterprise Library 検証 Application Block を使用してモデル要素の検証を実行して、Microsoft Visual Studio IDE の [エラー一覧] ウィンドウに、検証エラーをログに記録します。 モデル内の要素の種類ごとに実行される検証は、エンタープライズ ライブラリの構成ファイルで定義されます。 ファイルは、Ruleset.config の名前は、行程デザイナーのすべてのバイナリが配置されているバイナリ フォルダーにあります。 次の例は、構成ファイルのフラグメントと (という名前の検証コントロール)、2 つの検証規則が含まれています、 **UddiResolver** extender、1 つ、 **ServerUrl**プロパティと、用**ServiceKey**プロパティです。  
  
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
  
 各規則は、検証規則を実装するコントロールを識別します。 行程デザイナーの検証コントロール クラスの大規模なセットが付属します。 これらがすべてデザイナー バイナリ フォルダーに Microsoft.Practices.Modeling.Validation プロジェクトです。  
  
 この検証メカニズムを使用して最終的な結果とは、ユーザーが、指定された規則と検証コントロールを変更するか、独自の規則と検証コントロールを追加することによって、モデルを検証する方法を変更することができます、行程デザイナーです。 これは、開く、変更、再構築、および次の 2 つの手順を実行することによって、Dsl を再デプロイすることがなく実行できます。  
  
1.  検証クラスを作成し、バイナリ フォルダー内のライブラリに格納場所、 **Microsoft.Practices.Modeling.Validation.dll**ライブラリがあります。  
  
2.  検証コントロールを適用するモデル要素クラスのプロパティを定義する Rules.config ファイルにエントリを追加します。