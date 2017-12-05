---
title: ".NET プロジェクトで、WCF LOB Adapter SDK アダプターを使用する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6934b96d-5704-4f3c-b53f-4e36e352a338
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 622c6ad687e681591071d472e2ff8a9e8c515f95
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="consume-a-wcf-lob-adapter-sdk-adapter-in-a-net-project"></a>.NET プロジェクトで、WCF LOB Adapter SDK アダプターを使用します。
使用して構築されたアダプターを使用する、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]から[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクトにサービス参照を追加する必要があります。 これを行うことができます。  
  
-   使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]がの一部としてインストールされている、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。  
  
-   Windows SDK の一部としてインストールされている (、ServiceModel メタデータ ユーティリティ)、svcutil.exe を使用します。  
  
## <a name="add-a-service-reference-using-the-add-adapter-service-reference-plug-in"></a>アダプター サービス参照の追加プラグインを使用してサービス参照の追加します。  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照して、メタデータを検索し、選択した操作と型を使用して .NET CLR プロキシ クラスを生成するために使用できます。  
  
 
1.  .NET アプリケーションを開く[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。  
  
2.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を右クリックし、**プロジェクト** メニューをクリックして**アダプター サービス参照の追加**です。  
  
    > [!NOTE]
    >  このオプションは表示されません[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクト。  
  
3.  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]  画面から、**バインディングを選択**ドロップダウン リストで、アダプター バインドを選択します。  
  
4.  接続 URI、選択したアダプターのバインドを構成して、任意の資格情報、URI のプロパティのバインドのプロパティを提供するには、クリックして**構成**です。 実際の要件は、選択したアダプターのバインドによって異なります。  
  
5.  URI を構成した場合にクリックして**OK**です。  
  
6.  **[接続]**をクリックします。 接続 URI が有効であり、クライアントの資格情報 (存在する場合) が受け入れられたら場合、**カテゴリ**ペインは、アダプターによって提供される操作とカテゴリで表示されます必要があります。  
  
7.  アダプターは、検索をサポートする場合は、[検索] フィールドはアクティブになります。 それ以外の場合、コントラクト型でフィルター処理、内のノードをクリックして、型、および操作を調べ、**カテゴリ**ウィンドウです。  
  
8.  高度なプロキシの生成オプションをクリックして**詳細**です。 次のような方法があります。  
  
    |オプション|Svcutil.exe と同じオプション|Description|  
    |------------|-----------------------------------|-----------------|  
    |**非同期のメソッドを生成します。**|/async|両方の同期および非同期のメソッド署名を生成します。<br /><br /> (選択されていない) 場合は既定: 同期メソッド署名のみが生成されます。|  
    |**メッセージ コントラクトを生成します。**|/messageContract|メッセージ コントラクト型を生成します。|  
    |**内部型を作成します。**|/内部|内部としてマークされるクラスを生成します。<br /><br /> (選択されていない) 場合は既定: パブリック クラスを生成します。|  
    |**データ バインディングを有効にします。**|/enableDataBinding|データ バインディングを有効にするすべてのデータ コントラクト型にインターフェイスの実装、System.ComponentModel.INotifyPropertyChanged です。|  
    |**以外のデータ型を IXmlSerializable としてインポートします。**|/importXmlTypes|非データ コントラクト型を IXmlSerializable 型としてインポートするデータ コントラクト シリアライザーを構成します。|  
    |**チャネル インターフェイスを生成します。**||チャネル インターフェイスを生成します。|  
    |**シリアル化可能なマーク クラス**||シリアライザーでデータ型を生成するかどうかを選択します。|  
    |**App.config を生成しません。**|/noConfig|アプリケーション構成ファイルを生成しません。|  
    |**シリアライザー**<br /><br /> **Auto**|/serializer:Auto|シリアル化とシリアル化解除のシリアライザーが自動的に選択します。|  
    |**シリアライザー**<br /><br /> **DataContract シリアライザー**|/serializer:DataContractSerializer|シリアル化と逆シリアル化したデータ コントラクト シリアライザーを使用するデータ型が生成されます。|  
    |**シリアライザー**<br /><br /> **XmlSerializer**|/serializer:XmlSerializer|シリアル化と逆シリアル化に XmlSerializer を使用するデータ型を生成します。|  
  
9. プロキシの成果物を生成する をクリックして**OK**です。 成果物の数は、コントラクトの型によって異なります。  
  
    |コントラクトの型|成果物|Description||  
    |-------------------|--------------|-----------------|-|  
    |送信|CLR WCF プロキシ|コントラクトおよびサービス実装が含まれています。||  
    |送信||App.config|含まれています、\<エンドポイント\>と\<バインド\>要素\<システムです。ServiceModel\>\<クライアント\>です。|  
    |受信|CLR の WCF サービスのインターフェイス|コントラクトを含まれています。||  
    |受信||CLR の WCF サービスの実装|スタブに対応する、コントラクトから派生する実装。|  
    |受信||App.config|含まれています、\<エンドポイント\>、\<バインド\>と\<動作\>要素\<システムです。ServiceModel\>\<サービス\>です。|  
  
10. アプリケーションで、プロキシを使用できます。  
  
## <a name="adding-a-service-reference-by-using-svcutilexe"></a>Svcutil.exe を使用して、サービス参照の追加  
 Svcutil.exe はメタデータを取得しに追加することができる .NET CLR プロキシ クラスを生成するために使用できるコマンド ライン ユーティリティ、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。 Svcutil.exe の詳細については、次を参照してください。 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)です。 
  
 IIS でホストされているアダプターからプロキシ クラスを生成するには  
  
1.  コマンド プロンプトで次のように入力します。 **svcutil.exe"http://localhost/adapter/AdapterService.svc?wsdl"/config:app.config**です。HTTP パスをホストされているアダプターの正しいパスに置き換えます。 .NET CLR プロキシとを含む output.config を含む .cs ファイルが作成、\<バインド\>とクライアント\<エンドポイント\>の\<system.serviceModel\>です。  
  
    > [!NOTE]
    >  クエリ文字列を使用して返される操作を制限することができる場合は、アダプターには、多くの操作が含まれており、' op =' の関心がある操作の名前が続きます。 例: `svcutil.exe “http://localhost/adapter/AdapterService.svc?wsdl&op=Echo/EchoString&op=Echo/EchoArray”` EchoString および EchoArray 操作だけのプロキシ コードを生成します。  
  
2.  プロジェクトを開く[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。  
  
    1.  **ソリューション エクスプ ローラー**プロジェクトを右クリックしをポイントし、**追加**、クリックして**新しい項目の**します。 **既存項目の追加** ダイアログ ボックスで、選択、.cs ファイルおよび app.config ファイルが以前に作成します。  **[追加]**をクリックします。  
  
    2.  **ソリューション エクスプ ローラー**を右クリックして**参照**、クリックして**参照の追加**です。 **.NET** ] タブで [ **System.ServiceModel**、クリックして**[ok]**です。 アプリケーションで、プロキシを使用できます。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1: エコー アダプターを開発します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)   
 [WCF LOB Adapter SDK を使用して作成されたアダプターを使用します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/consume-an-adapter-created-using-the-wcf-lob-adapter-sdk.md)