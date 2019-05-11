---
title: .NET プロジェクトで、WCF LOB Adapter SDK のアダプターの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6934b96d-5704-4f3c-b53f-4e36e352a338
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1968f0ab8e6d6c01a98db04379ea4df21fb59be4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363745"
---
# <a name="consume-a-wcf-lob-adapter-sdk-adapter-in-a-net-project"></a>.NET プロジェクトで、WCF LOB Adapter SDK のアダプターを使用します。
使用して構築されたアダプターを使用する、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]から[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクトにサービス参照を追加する必要があります。 、これを行うことができます。  

- 使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]の一部としてインストールされている、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。  

- Windows SDK の一部としてインストールされています (、ServiceModel メタデータ ユーティリティ)、svcutil.exe を使用します。  

## <a name="add-a-service-reference-using-the-add-adapter-service-reference-plug-in"></a>Add Adapter Service Reference プラグインを使用してサービス参照の追加します。  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照し、メタデータを検索して、選択した操作と型を使用して .NET CLR プロキシ クラスを生成するために使用できます。  


1. .NET アプリケーションを開く[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。  

2. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を右クリックし、**プロジェクト** メニューをクリックして**アダプター サービス参照の追加**です。  

   > [!NOTE]
   >  このオプションは表示されません[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクト。  

3. [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]  画面から、**バインディングを選択**ドロップダウン リストで、アダプターのバインドを選択します。  

4. 選択したアダプターのバインドの接続 URI を構成して、任意の資格情報、URI のプロパティ、およびバインドのプロパティを提供するクリックして**構成**します。 実際の要件は、選択したアダプターのバインドによって異なります。  

5. URI を構成している場合にクリックして**OK**します。  

6. **[接続]** をクリックします。 接続 URI が有効であり (あれば) のクライアント資格情報が受け入れられたら場合、**カテゴリ**ウィンドウ、カテゴリと、アダプターによって提供される操作を入力します。  

7. アダプターは、検索をサポートする場合、検索フィールドがアクティブになります。 それ以外の場合、コントラクト型でフィルター処理、内のノードをクリックして、型、および操作を調べ、**カテゴリ**ウィンドウ。  

8. 高度なプロキシの生成オプションをクリックして**詳細**します。 次のような方法があります。  


   |                         オプション                         |   Svcutil.exe と同じオプション    |                                                                     説明                                                                     |
   |--------------------------------------------------------|------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
   |           **非同期のメソッドを生成します。**            |               /async               | 両方の同期および非同期のメソッド署名を生成します。<br /><br /> (選択されていない) 場合の既定: 同期メソッド署名のみが生成されます。 |
   |             **メッセージ コントラクトを生成します。**             |          /messageContract          |                                                          メッセージ コントラクト型を生成します。                                                          |
   |                **内部型を作成します。**                 |             /内部              |                   内部としてマークされているクラスを生成します。<br /><br /> (選択されていない) 場合の既定: パブリック クラスを生成します。                    |
   |                **データ バインディングを有効にします。**                 |         /enableDataBinding         |              データ バインディングを有効にするためのすべてのデータ コントラクト型での実装、System.ComponentModel.INotifyPropertyChanged インターフェイスします。               |
   |     **以外のデータ型を IXmlSerializable としてインポートします。**      |          /importXmlTypes           |                        IXmlSerializable 型として非データ コントラクト型をインポートするデータ コントラクト シリアライザーを構成します。                         |
   |             **チャネル インターフェイスを生成します。**             |                                    |                                                          チャネル インターフェイスを生成します。                                                           |
   |             **シリアル化可能なマーク クラス**              |                                    |                                            シリアライザーのデータ型を生成するかどうかを選択します。                                            |
   |             **App.config を生成できません。**             |             /noConfig              |                                                  アプリケーション構成ファイルを生成しません。                                                  |
   |          **シリアライザー**<br /><br /> **Auto**           |          /serializer:Auto          |                                     シリアル化およびシリアル化解除のシリアライザーを自動的に選択します。                                      |
   | **シリアライザー**<br /><br /> **DataContract シリアライザー** | /serializer:DataContractSerializer |                         シリアル化および逆シリアル化、データ コントラクト シリアライザーを使用するデータ型を生成します。                          |
   |      **シリアライザー**<br /><br /> **XmlSerializer**      |     /serializer:XmlSerializer      |                               シリアル化と逆シリアル化に XmlSerializer を使用するデータ型を生成します。                                |


9. プロキシの成果物を生成する をクリックして**OK**します。 成果物の数は、コントラクトの型によって異なります。  


   | コントラクト型 |         成果物          |                    説明                    |                                                                                                            |
   |---------------|---------------------------|---------------------------------------------------|------------------------------------------------------------------------------------------------------------|
   |   送信    |       CLR の WCF プロキシ       | コントラクトおよびサービスの実装が含まれています。 |                                                                                                            |
   |   送信    |                           |                    App.config                     |         含まれています、\<エンドポイント\>と\<バインド\>要素\<システム。ServiceModel\>\<クライアント\>します。         |
   |    受信    | CLR の WCF サービスのインターフェイス |              コントラクトが含まれています。               |                                                                                                            |
   |    受信    |                           |          CLR の WCF サービスの実装           |                            コントラクトから派生するスタブ実装します。                             |
   |    受信    |                           |                    App.config                     | 含まれています、\<エンドポイント\>、\<バインド\>と\<動作\>要素\<システム。ServiceModel\>\<サービス\>します。 |


10. アプリケーションで、プロキシを使えるようになりました。  

## <a name="adding-a-service-reference-by-using-svcutilexe"></a>Svcutil.exe を使用してサービス参照の追加  
 Svcutil.exe はメタデータを取得し、後に追加できる .NET CLR プロキシ クラスを生成するために使用できるコマンド ライン ユーティリティ、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。 Svcutil.exe の詳細については、次を参照してください。 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)します。 

 IIS でホストされているアダプターからプロキシ クラスを生成するには  

1. コマンド プロンプトで次のように入力します。 **svcutil.exe"<http://localhost/adapter/AdapterService.svc?wsdl”> /config:app.config**します。HTTP パスをホストされているアダプターの正しいパスに置き換えます。 .NET CLR プロキシとを含む output.config を含む .cs ファイルが作成されます、\<バインド\>とクライアント\<エンドポイント\>の\<system.serviceModel\>します。  

   > [!NOTE]
   >  クエリ文字列を使用して返される操作を制限することができる場合、アダプターには、多くの操作が含まれており、' op =' 後に目的の操作の名前。 例: `svcutil.exe “http://localhost/adapter/AdapterService.svc?wsdl&op=Echo/EchoString&op=Echo/EchoArray”` EchoString と EchoArray の操作のプロキシ コードを生成します。  

2. プロジェクトを開き[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。  

   1.  **ソリューション エクスプ ローラー**、プロジェクトを右クリックし、 をポイント**追加**、 をクリックし、**新しい項目の**します。 **既存項目の追加** ダイアログ ボックスで、選択、.cs ファイルと app.config ファイルが以前に作成します。  **[追加]** をクリックします。  

   2.  **ソリューション エクスプ ローラー**を右クリックして**参照**、 をクリックし、**参照の追加**します。 **.NET** ] タブで [ **System.ServiceModel**、順にクリックします**OK**します。 アプリケーションで、プロキシを使えるようになりました。  

## <a name="see-also"></a>参照  
 [チュートリアル 1:エコー アダプターを開発します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)   
 [WCF LOB Adapter SDK を使用して作成されたアダプタを使用します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/consume-an-adapter-created-using-the-wcf-lob-adapter-sdk.md)