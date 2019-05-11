---
title: 手順 1:WCF LOB アダプター開発ウィザードを使用してエコー アダプター プロジェクトを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 634a6498-55b0-462d-a5ca-16507b3787f5
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da2e6ebce130716d2a1fb79766e4760c1fa79897
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363244"
---
# <a name="step-1-use-the-wcf-lob-adapter-development-wizard-to-create-the-echo-adapter-project"></a>手順 1:WCF LOB アダプター開発ウィザードを使用してエコー アダプター プロジェクトを作成するには
![手順 9 の 1](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-1of9.gif "Step_1of9")  

 **所要時間:** 15 分  

 この手順でを使用してプロジェクトを作成、 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] 、[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]します。 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]システム用のカスタム アダプターの開発に関連する手順を説明します。 メッセージ交換パターン、メタデータ機能、アダプターのプロパティ、および接続のプロパティに関する情報を収集します。 ウィザードが正常に完了すると、一連のファイルを生成します。  

## <a name="prerequisites"></a>前提条件  
 説明されている知識を持つ必要があります[チュートリアルを開始する前に](../../core/before-you-begin-the-tutorial.md)を使用して、アダプター開発用にコンピューターを正常に設定して、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。  

## <a name="choose-wcf-lob-adapter-plug-in-in-visual-studio"></a>WCF LOB アダプターでは、Visual Studio プラグインの選択します。  

1.  Visual Studio を起動し、**ファイル**メニューで、**新規**、 をクリックし、**プロジェクト**します。  

2.  **新しいプロジェクト** ダイアログ ボックスで、次の操作を行います。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロジェクトの種類**|クリックして**Visual c#** します。|  
    |**[テンプレート]**|クリックして**WCF LOB Adapter**します。|  
    |**名前**|型**EchoAdapter**します。|  
    |**場所**|型**C:\Tutorials**します。|  
    |**ソリューションのディレクトリを作成します。**|ソリューション ファイルのディレクトリを作成するには、このチェック ボックスをオンにします。|  
    |**[ソリューション名]**|型**EchoAdapterSampleV2**します。|  

     次に示します、**新しいプロジェクト** ダイアログ ボックス。  

     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/3a349be4-1a7d-480a-8e9d-cfcba63cd14a.gif "3a349be4-1a7d-480a-8e9d-cfcba63cd14a")  

3.  **[OK]** をクリックします。  

4.  **へようこそ**  ページで **次**します。 次に示します、**ようこそ**ページ。  

     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/0b8ef97f-044d-481f-8c7c-0d034fdba37d.gif "0b8ef97f-044d-481f-8c7c-0d034fdba37d")  

5.  **[次へ]** をクリックします。  

## <a name="enter-the-scheme-and-namespace-information"></a>スキームと名前空間の情報を入力します  

1.  **スキーム、Namespace、および URI 情報**ページで、次の操作を行います。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |**スキーム**|型**echov2**します。|  
    |**プロジェクトの名前空間**|型**Microsoft.Adapters.Samples.EchoV2**します。|  

     次に示します、**スキーム、Namespace、および URI 情報**ページ。  

     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/0d72dab2-7992-47e4-bc4e-3e720b1cde38.gif "0d72dab2-7992-47e4-bc4e-3e720b1cde38")  

2.  **[次へ]** をクリックします。  

## <a name="enter-the-data-flow-and-metadata-features"></a>データ フローとメタデータ機能を入力します。  

1.  **データ フロー**と**メタデータ機能**ページで、次の操作を行います。  

     **メッセージ交換パターン**  

    |プロパティ|目的|  
    |--------------|----------------|  
    |**送信同期**|チェック ボックスを選択します。|  
    |**同期受信**|チェック ボックスを選択します。|  

     **メタデータ機能**  

    |プロパティ|目的|  
    |--------------|----------------|  
    |**取得**|チェック ボックスを選択します。|  
    |**[参照]**|チェック ボックスを選択します。|  
    |**検索**|チェック ボックスを選択します。|  

    > [!NOTE]
    >  このコンテキストでデータ フローは、概念説明のトピックで使用される用語メッセージ交換のパターンと同じことを意味します。  

     次に示します、**データ フロー**と**メタデータ機能**ページ。  

     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/4fa6f67d-4703-41db-b5f3-28cf9d6a40d2.gif "4fa6f67d-4703-41db-b5f3-28cf9d6a40d2")  

2.  **[次へ]** をクリックします。  

## <a name="enter-the-adapter-properties"></a>アダプターのプロパティを入力します。  

1. **アダプター プロパティ**ページで、次の操作を行います。  

2. という名前のプロパティを追加**カウント**します。 この数は、エコー アダプターのすべての操作によって使用されます。 各操作には、入力値が返されます、**カウント**回数。  


   |     プロパティ      |               目的               |
   |-------------------|----------------------------------------|
   | **プロパティ名** |            型**カウント**します。             |
   |   **データ型**   |        選択**System.Int32**します。        |
   | **既定値** |              型**5**します。               |
   |      **[追加]**      | 新しいアダプターのプロパティを追加する をクリックします。 |


3. という名前のプロパティを追加**EnableConnectionPooling**します。 このフラグを使用して、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]を有効またはランタイム接続プーリングを無効にします。  


   |     プロパティ      |               目的               |
   |-------------------|----------------------------------------|
   | **プロパティ名** |   型**EnableConnectionPooling**します。    |
   |   **データ型**   |       選択**System.Boolean**します。       |
   | **既定値** |             型**true**します。             |
   |      **[追加]**      | 新しいアダプターのプロパティを追加する をクリックします。 |


4. という名前のプロパティを追加**InboundFileFilter**します。 このプロパティは、この拡張機能のファイルを監視するために、filesystemwatcher クラスによって使用されます。 このプロパティは、受信のシナリオにのみ適用できます。  


   |     プロパティ      |               目的               |
   |-------------------|----------------------------------------|
   | **プロパティ名** |      型**InboundFileFilter**します。       |
   |   **データ型**   |       選択**System.String**します。        |
   | **既定値** |            型 **\*.txt**します。            |
   |      **[追加]**      | 新しいアダプターのプロパティを追加する をクリックします。 |


5. という名前のプロパティを追加**InboundFileSystemWatcherFolder**します。 このプロパティは、アダプターに通知を発生させる FileSystemWatcher のファイルを削除、フォルダーの設定に使用されます。 このプロパティは、受信のシナリオにのみ適用できます。  

   |プロパティ|目的|  
   |--------------|----------------|  
   |**プロパティ名**|型**InboundFileSystemWatcherFolder**します。|  
   |**データ型**|選択**System.String**します。|  
   |**既定値**|型**c:\\\inbound\\\watcher**します。|  
   |**[追加]**|新しいアダプターのプロパティを追加する をクリックします。|  

    次に示します、**アダプター プロパティ**ページ。  

    ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/84de11a5-a737-4aa5-96c8-61922e704f2b.gif "84de11a5-a737-4aa5-96c8-61922e704f2b")  

6. **[次へ]** をクリックします。  

## <a name="enter-the-connection-properties"></a>接続のプロパティを入力します。  

1.  **接続プロパティ**ページで、次の操作を行います。  

2.  という名前のプロパティを追加**アプリケーション**します。 このプロパティは、例示のみを目的のためです。 エコー アダプターは、任意の LOB システムには関与しません。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ名**|型**アプリケーション**します。|  
    |**データ型**|選択**System.String**します。|  
    |**既定値**|型**lobapplication**します。|  
    |**[追加]**|新しいアダプターのプロパティを追加する をクリックします。|  

3.  という名前のプロパティを追加**EnableAuthentication**します。 ときに`true`アダプターがクライアントの資格情報内のユーザー名フィールドの値が必要です。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ名**|型**EnableAuthentication**します。|  
    |**データ型**|選択**System.Boolean**します。|  
    |**既定値**|型**false**します。|  
    |**[追加]**|新しいアダプターのプロパティを追加する をクリックします。|  

4.  という名前のプロパティを追加**HostName**します。 このプロパティは説明目的でのみ、プロパティのような**アプリケーション**します。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ名**|型**Hostname**します。|  
    |**データ型**|選択**System.String**します。|  
    |**既定値**|型**lobhostname**します。|  
    |**[追加]**|新しいアダプターのプロパティを追加する をクリックします。|  

5.  という名前のプロパティを追加**EchoInUpperCase**します。 このプロパティ コントロールは、大文字に変換する文字列をエコーいくつかの操作に変換するかどうかや、元の形式のままにします。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ名**|型**EchoInUpperCase**します。|  
    |**データ型**|選択**System.Boolean**します。|  
    |**既定値**|型**False**します。|  
    |**[追加]**|新しいアダプターのプロパティを追加する をクリックします。|  

6.  **[次へ]** をクリックします。  

## <a name="end-the-wizard"></a>ウィザードを終了します。  

1.  **概要**] ページで [**完了**します。 次に示します**ソリューション エクスプ ローラー**で、 **EchoAdapter**プロジェクト。  

     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/06b45c3e-d056-48f4-a246-642d9ac5e23e.gif "06b45c3e-d056-48f4-a246-642d9ac5e23e")  

     プロジェクトには、同じファイルを含める必要があります。 そうでない場合は、Visual Studio を終了、削除、 **EchoAdapterSampleV2**フォルダー、し、このチュートリアルのこの手順を再起動します。  

2.  Visual Studio での**ファイル** メニューのをクリックして**すべて保存**します。  

    > [!NOTE]
    >  これで作業が保存されました。 安全にこの時点で Visual Studio を閉じて、次の手順に進むまたは[手順 2。アダプターおよび接続のプロパティを分類](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)します。  

## <a name="what-did-i-just-do"></a>でしただけ何か。  
 この手順で Visual Studio を使用してエコー アダプターのソリューションを作成した、[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]します。 次の表には、各ファイルの新機能およびファイルのセットが含まれています。  

|**[ファイル名]**|**[説明]**|  
|-------------------|---------------------|  
|EchoAdapter.cs|これは、メインのアダプター クラスを継承する`Microsoft.ServiceModel.Channels.Common.Adapter`します。<br /><br /> エコー アダプターの変更は不要です。|  
|EchoAdapterBinding.cs|これは、アダプターのバインドを作成するときに使用されるクラスです。<br /><br /> エコー アダプターの変更は不要です。|  
|EchoAdapterBindingCollectionElement.cs|これは、コレクションの要素のバインディング クラスを実装する、`System.ServiceModel.Configuration.StandardBindingCollectionElement`します。<br /><br /> エコー アダプターの変更は不要です。|  
|EchoAdapterBindingElement.cs|これは、構成要素の基本クラスを提供します。<br /><br /> エコー アダプターのアダプターと接続のプロパティを分類するには、次の[手順 2。アダプターおよび接続のプロパティを分類](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)します。|  
|EchoAdapterBindingElementExtensionElement.cs|ユーザー定義 WCF カスタム バインド内で使用できるように、このクラスは、バインド要素として、アダプターを表す提供されます。<br /><br /> エコー アダプターのアダプターと接続のプロパティを分類するには、次の[手順 2。アダプターおよび接続のプロパティを分類](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)します。|  
|EchoAdapterHandlerBase.cs|これは、基底クラスによって公開されている共通のプロパティ/ヘルパー関数を格納するために使用するハンドラーの基本クラスです。<br /><br /> エコー アダプターのアダプターと接続のプロパティを分類するには、次の[手順 2。アダプターおよび接続のプロパティを分類](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)します。|  
|EchoAdapterConnection.cs|これは、ターゲット システムに接続を定義します。<br /><br /> 次のターゲット システムにエコー アダプターの接続をサポートする[手順 3。エコー アダプターの接続を実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)します。|  
|EchoAdapterConnectionFactory.cs|これには、ターゲット システムの接続ファクトリを定義します。<br /><br /> 次のターゲット システムにエコー アダプターの接続をサポートする[手順 3。エコー アダプターの接続を実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)します。|  
|EchoAdapterConnectionUri.cs|これは、アダプターの接続 Uri を表すクラスです。<br /><br /> 次のターゲット システムにエコー アダプターの接続をサポートする[手順 3。エコー アダプターの接続を実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md))。|  
|EchoAdapterMetadataBrowseHandler.cs|このクラスは、ターゲット システムからのメタデータの接続に基づく参照の実行中に使用されます。<br /><br /> 次のメタデータのエコー アダプターの機能の参照をサポートするために[手順 4。エコー アダプターのメタデータ参照ハンドラーを実装する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md)します。|  
|EchoAdapterMetadataSearchHandler.cs|このクラスは、ターゲット システムからのメタデータには、接続ベースの検索を実行するために使用されます。<br /><br /> エコー アダプターの機能を検索するメタデータをサポートするに従って[手順 5。エコー アダプターのメタデータ検索ハンドラーの実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md)します。|  
|EchoAdapterMetadataResolve.cs|このクラスは、ターゲット システムからのメタデータの接続ベースの取得を実行するために使用されます。<br /><br /> エコー アダプターの機能を解決するメタデータをサポートするに従って[手順 6。エコー アダプターのメタデータ解決ハンドラーを実装する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md)します。|  
|EchoAdapterOutboundHandler.cs|このクラスは、ターゲット システムにデータを送信するために使用されます。<br /><br /> 次のエコー アダプターの送信メッセージの交換をサポートするために[手順 7。エコー アダプターの同期送信ハンドラーを実装する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)します。|  
|EchoAdapterInboundHandler.cs|このクラスは、リッスンしているかにデータをポーリングするためのインターフェイスを実装します。<br /><br /> 次のエコー アダプターの受信メッセージの交換をサポートするために[手順 8。エコー アダプターの同期受信ハンドラーを実装する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md)します。|  
|EchoAdapterTrace.cs|このクラスは、デバッグとトラブルシューティングのためのアダプターのトレースを実装します。|  

## <a name="next-steps"></a>次の手順  
 UI 論理グループのアダプターと接続のプロパティを分類し、接続、メタデータの参照、検索、および機能、および送信および受信のメッセージ交換の解決を実装します。 最後に、ビルドし、エコー アダプターを展開します。  

## <a name="see-also"></a>参照  
 [手順 2:アダプターと接続のプロパティを分類します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)   
 [チュートリアル 1:エコー アダプターを開発する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)