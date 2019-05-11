---
title: カスタム アダプター プロバイダーの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb93acf8-fd9d-4315-8690-f0c152a954b5
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e6cc8b50a350e13c0269718783a33923d76490b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291506"
---
# <a name="creating-a-custom-adapter-provider"></a>カスタム アダプター プロバイダーの作成
前のセクションで説明した、競合回避モジュールの実行、後に、結果はエンドポイント (変換ではない) であるかどうか、動的解決サービスを確認します。 サービス インスタンスであるアダプター マネージャーがインスタンス化エンドポイントである場合の**AdapterMgr**クラス。  
  
 アダプター マネージャーでは、検証し、トランスポートの種類と、送信トランスポートの場所を修正します。 トランスポートの種類がまだない解決された場合、および URL が"http"または"https"で始まる場合は、アダプター マネージャーは、トランスポートの種類を"Wcf-wshttp"を設定します。  
  
 次に、アダプター マネージャーは、トランスポートの種類が、有効な Microsoft BizTalk Server アダプターに相当し、そのプロパティの名前空間が返されますことを確認します。 このプロセスは、すべてのアダプターの 1 回だけ実行し、同じアダプターを使用するその他の受信メッセージのクエリを繰り返しを避けるために、キャッシュに結果を格納します。  
  
 アダプター マネージャーは、トランスポートの種類を使用して (なし、"**://**"サフィックス) を適切なアダプター プロバイダーを決定します。 アダプター プロバイダーをカスタム アセンブリを実装する必要がありますが、 **IAdapterProvider**インターフェイス。 アダプター プロバイダーのプロパティを使用して、**解決**構造体、**ディクショナリ**できるメッセージのすべてのプロトコル固有のプロパティを設定する競合回避モジュールによって生成されたインスタンス、動的な解決を実行する Microsoft BizTalk Server ランタイム エンジン。  
  
 ように (前のセクションで説明)、競合回避モジュールを動的解決の機構を使用してエントリ Esb.config 構成ファイルでアダプター プロバイダーを見つけること。 次の XML では、構成ファイルのセクションを示します。  
  
```xml  
<adapterProviders cacheManager= "Adapter Providers Cache Manager"  absoluteExpiration="3600">  
     <adapterProvider name="WCF-WSHttp" type="Microsoft.Practices.ESB.Adapter.WcfWSHttp.AdapterProvider, Microsoft.Practices.ESB.Adapter.WcfWSHttp, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22" moniker="Http,Https" />  
     <adapterProvider name="WCF-BasicHttp" type="Microsoft.Practices.ESB.Adapter.WcfBasicHttp.AdapterProvider, Microsoft.Practices.ESB.Adapter.WcfBasicHttp, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22" moniker="Http,Https" />  
     <adapterProvider name="WCF-Custom" type="Microsoft.Practices.ESB.Adapter.WcfCustom.AdapterProvider, Microsoft.Practices.ESB.Adapter.WcfCustom, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22" moniker="mssql" />  
     <adapterProvider name="SMTP" type="Microsoft.Practices.ESB.Adapter.SMTP.AdapterProvider, Microsoft.Practices.ESB.Adapter.SMTP, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22" moniker="smtp" />  
     <adapterProvider name="FTP" type="Microsoft.Practices.ESB.Adapter.FTP.AdapterProvider, Microsoft.Practices.ESB.Adapter.FTP, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22">  
          <adapterConfig>  
               <add name="DefaultUsername" value="anonymous" />  
               <add name="DefaultPassword" value="" />  
          </adapterConfig>  
     </adapterProvider>  
     <adapterProvider name="MQSeries" type="Microsoft.Practices.ESB.Adapter.MQSeries.AdapterProvider, Microsoft.Practices.ESB.Adapter.MQSeries, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22" moniker="MQS" adapterAssembly="MQSeries, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
     <adapterProvider name="FILE" type="Microsoft.Practices.ESB.Adapter.FILE.AdapterProvider, Microsoft.Practices.ESB.Adapter.FILE, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22" moniker="File" />  
</adapterProviders>  
```  
  
## <a name="creating-a-custom-adapter-provider"></a>カスタム アダプター プロバイダーの作成  
 アダプター マネージャー (のインスタンス、 **AdapterMgr**クラス) は構成ファイルでアダプターのプロバイダーを検索し、適切なアセンブリを読み込みます。 動的解決の機構の具象実装が読み込まれたすべてのキャッシュ、 **IAdapterProvider**インターフェイスの構成情報とアセンブリの読み込み時に、いくつかの受信メッセージを使用して、繰り返される読み取りを回避するために、同じアダプター プロバイダーです。  
  
 最後に、アダプター マネージャーが実行される、 **SetEndPoint**の具象実装のメソッド、 **IAdapterProvider**インターフェイス、およびパイプライン コンポーネントは、BizTalk にメッセージを返しますメッセージ ボックス データベースです。  
  
 **カスタム アダプター プロバイダーを作成するには**  
  
1.  派生したアセンブリを作成、 **BaseAdapterProvider**基底クラスとが含まれています、 **SetEndPoint**エンドポイント、メッセージのコンテキスト プロパティを設定するメソッドです。  
  
2.  使用して Esb.config 構成ファイルに追加することによってアダプターのプロバイダーを登録、 **\<adapterProvider\>** としてアダプターの名前を持つ要素、**名前**属性クラスの完全修飾名、**型**属性は、モニカーとして、**モニカー**属性 (複数の値は、コンマで区切る必要があります)、およびアセンブリの必要に応じて、実際のアダプターとして、 **adapterAssembly**属性。  
  
3.  グローバル アセンブリ キャッシュに新しいアセンブリを登録します。