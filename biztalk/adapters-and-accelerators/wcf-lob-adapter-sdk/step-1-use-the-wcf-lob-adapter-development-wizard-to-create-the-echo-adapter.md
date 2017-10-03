---
title: "手順 1: エコー アダプター プロジェクトを作成する WCF LOB アダプター開発ウィザードを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 634a6498-55b0-462d-a5ca-16507b3787f5
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffad8f817cf3a13b3d3af3264438bafa639181a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-use-the-wcf-lob-adapter-development-wizard-to-create-the-echo-adapter-project"></a>手順 1: WCF LOB アダプター開発ウィザードを使用してエコー アダプター プロジェクトを作成するには
![手順 9 の 1](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-1of9.gif "Step_1of9")  
  
 **所要時間:** 15 分  
  
 このステップでを使用してプロジェクトを作成、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]と[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]です。 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]に従ってシステムのカスタム アダプターの開発に必要な手順を実行します。 メッセージ交換パターン、メタデータの機能、アダプターのプロパティ、および接続のプロパティに関する情報を収集します。 ウィザードが正常に完了すると、一連のファイルを生成します。  
  
## <a name="prerequisites"></a>前提条件  
 説明されている知識を持つ必要があります[チュートリアルを開始する前に](../../core/before-you-begin-the-tutorial.md)を使用して、アダプター開発用コンピューターを正常に設定し、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。  
  
## <a name="choose-wcf-lob-adapter-plug-in-in-visual-studio"></a>Visual Studio でプラグイン WCF LOB アダプターを選択します。  
  
1.  Visual Studio を起動し、**ファイル** メニューのをポイント**新規**、クリックして**プロジェクト**です。  
  
2.  **新しいプロジェクト** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロジェクトの種類**|をクリックして**Visual c#**です。|  
    |**[テンプレート]**|をクリックして**WCF LOB アダプター**です。|  
    |**名前**|型**EchoAdapter**です。|  
    |**場所**|型**C:\Tutorials**です。|  
    |**ソリューションのディレクトリを作成します。**|ソリューション ファイルのディレクトリを作成するには、このチェック ボックスをオンにします。|  
    |**[ソリューション名]**|型**EchoAdapterSampleV2**です。|  
  
     次の図に示しています、**新しいプロジェクト** ダイアログ ボックス。  
  
     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/3a349be4-1a7d-480a-8e9d-cfcba63cd14a.gif "3a349be4-1a7d-480a-8e9d-cfcba63cd14a")  
  
3.  **[OK]**をクリックします。  
  
4.  **ようこそ** ページで、をクリックして**次**です。 次の図に示しています、**ようこそ**ページ。  
  
     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/0b8ef97f-044d-481f-8c7c-0d034fdba37d.gif "0b8ef97f-044d-481f-8c7c-0d034fdba37d")  
  
5.  **[次へ]**をクリックします。  
  
## <a name="enter-the-scheme-and-namespace-information"></a>スキームと名前空間の情報を入力します。  
  
1.  **スキーム、Namespace、および URI 情報** ページで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**スキーム**|型**echov2**です。|  
    |**プロジェクトの名前空間**|型**Microsoft.Adapters.Samples.EchoV2**です。|  
  
     次の図に示しています、**スキーム、Namespace、および URI 情報**ページ。  
  
     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/0d72dab2-7992-47e4-bc4e-3e720b1cde38.gif "0d72dab2-7992-47e4-bc4e-3e720b1cde38")  
  
2.  **[次へ]**をクリックします。  
  
## <a name="enter-the-data-flow-and-metadata-features"></a>データ フローとメタデータ機能を入力します。  
  
1.  **のデータ フロー**と**メタデータ機能** ページで、次の操作します。  
  
     **メッセージ交換パターン**  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**送信同期**|チェック ボックスを選択します。|  
    |**同期受信**|チェック ボックスを選択します。|  
  
     **メタデータの機能**  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**取得**|チェック ボックスを選択します。|  
    |**参照**|チェック ボックスを選択します。|  
    |**検索**|チェック ボックスを選択します。|  
  
    > [!NOTE]
    >  このコンテキストでのデータ フローでは、概念説明のトピックで使用される用語のメッセージ交換パターンの場合と同じ意味です。  
  
     次の図に示しています、**のデータ フロー**と**メタデータ機能**ページ。  
  
     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/4fa6f67d-4703-41db-b5f3-28cf9d6a40d2.gif "4fa6f67d-4703-41db-b5f3-28cf9d6a40d2")  
  
2.  **[次へ]**をクリックします。  
  
## <a name="enter-the-adapter-properties"></a>アダプターのプロパティを入力してください。  
  
1.  **アダプター プロパティ** ページで、次の操作します。  
  
2.  という名前のプロパティを追加**カウント**です。 この番号は、エコー アダプターのすべての操作を使用します。 各操作には、入力値が返されます、**カウント**回数。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ名**|型**カウント**です。|  
    |**データ型**|選択**System.Int32**です。|  
    |**既定値**|型**5**です。|  
    |**[追加]**|新しいアダプター プロパティを追加する をクリックします。|  
  
3.  という名前のプロパティを追加**EnableConnectionPooling**です。 このフラグを使用して、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]を有効にするにまたはランタイム接続プールを無効にします。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ名**|型**EnableConnectionPooling**です。|  
    |**データ型**|選択**System.Boolean**です。|  
    |**既定値**|型**true**です。|  
    |**[追加]**|新しいアダプター プロパティを追加する をクリックします。|  
  
4.  という名前のプロパティを追加**InboundFileFilter**です。 このプロパティは、この拡張機能のファイルを監視する、FileSystemWatcher を使用します。 このプロパティは、入力方向のシナリオのみに適用します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ名**|型**InboundFileFilter**です。|  
    |**データ型**|選択**System.String**です。|  
    |**既定値**|型 **\*.txt**です。|  
    |**[追加]**|新しいアダプター プロパティを追加する をクリックします。|  
  
5.  という名前のプロパティを追加**InboundFileSystemWatcherFolder**です。 このプロパティは、アダプターに通知を発生させる FileSystemWatcher のファイルを削除する場所のフォルダー設定を使用します。 このプロパティは、入力方向のシナリオのみに適用します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ名**|型**InboundFileSystemWatcherFolder**です。|  
    |**データ型**|選択**System.String**です。|  
    |**既定値**|型**c:\\\inbound\\\watcher**です。|  
    |**[追加]**|新しいアダプター プロパティを追加する をクリックします。|  
  
     次の図に示しています、**アダプター プロパティ**ページ。  
  
     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/84de11a5-a737-4aa5-96c8-61922e704f2b.gif "84de11a5-a737-4aa5-96c8-61922e704f2b")  
  
6.  **[次へ]**をクリックします。  
  
## <a name="enter-the-connection-properties"></a>接続プロパティを入力します。  
  
1.  **接続プロパティ** ページで、次の操作します。  
  
2.  という名前のプロパティを追加**アプリケーション**です。 このプロパティは、例示のみを目的のためです。 エコー アダプターは、任意の LOB システムには関与しません。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ名**|型**アプリケーション**です。|  
    |**データ型**|選択**System.String**です。|  
    |**既定値**|型**lobapplication**です。|  
    |**[追加]**|新しいアダプター プロパティを追加する をクリックします。|  
  
3.  という名前のプロパティを追加**EnableAuthentication**です。 ときに`true`アダプターはクライアントの資格情報内のユーザー名フィールドに値を期待します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ名**|型**EnableAuthentication**です。|  
    |**データ型**|選択**System.Boolean**です。|  
    |**既定値**|型**false**です。|  
    |**[追加]**|新しいアダプター プロパティを追加する をクリックします。|  
  
4.  という名前のプロパティを追加**HostName**です。 このプロパティは、説明目的でのみ、プロパティのような**アプリケーション**です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ名**|型**Hostname**です。|  
    |**データ型**|選択**System.String**です。|  
    |**既定値**|型**lobhostname**です。|  
    |**[追加]**|新しいアダプター プロパティを追加する をクリックします。|  
  
5.  という名前のプロパティを追加**EchoInUpperCase**です。 このプロパティ コントロールは、大文字に変換する文字列がエコーされますいくつかの操作に変換するかどうかや、元の形式のままにします。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ名**|型**EchoInUpperCase**です。|  
    |**データ型**|選択**System.Boolean**です。|  
    |**既定値**|型**False**です。|  
    |**[追加]**|新しいアダプター プロパティを追加する をクリックします。|  
  
6.  **[次へ]**をクリックします。  
  
## <a name="end-the-wizard"></a>ウィザードを終了します。  
  
1.  **概要**] ページで [**完了**です。 次に示します**ソリューション エクスプ ローラー**で、 **EchoAdapter**プロジェクト。  
  
     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/06b45c3e-d056-48f4-a246-642d9ac5e23e.gif "06b45c3e-d056-48f4-a246-642d9ac5e23e")  
  
     プロジェクトには、同じファイルを追加する必要があります。 そうでない場合は、Visual Studio を終了、削除、 **EchoAdapterSampleV2**フォルダー、し、このチュートリアルの手順を再起動します。  
  
2.  Visual Studio での**ファイル** メニューのをクリックして**すべて保存**です。  
  
    > [!NOTE]
    >  これで作業が保存されました。 安全にこの時点で Visual Studio を終了したり、次の手順に進みます[手順 2: アダプターと接続のプロパティを分類](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)です。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 このステップで Visual Studio を使用してエコー アダプター ソリューションを作成して、[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]です。 次の表には、ファイルおよび各ファイルが、新機能のセットが含まれています。  
  
|**[ファイル名]**|**Description**|  
|-------------------|---------------------|  
|EchoAdapter.cs|これは、メインのアダプター クラスから継承される`Microsoft.ServiceModel.Channels.Common.Adapter`です。<br /><br /> エコー アダプターの変更は不要です。|  
|EchoAdapterBinding.cs|これは、アダプターのバインドを作成するときに使用されるクラスです。<br /><br /> エコー アダプターの変更は不要です。|  
|EchoAdapterBindingCollectionElement.cs|これは、バインドのコレクション要素クラスを実装する、`System.ServiceModel.Configuration.StandardBindingCollectionElement`です。<br /><br /> エコー アダプターの変更は不要です。|  
|EchoAdapterBindingElement.cs|これは、構成要素の基本クラスを提供します。<br /><br /> エコー アダプターのアダプターとの接続のプロパティを分類するために従う[手順 2: アダプターと接続のプロパティを分類](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)です。|  
|EchoAdapterBindingElementExtensionElement.cs|ユーザー定義 WCF カスタム バインド内で使用できるように、このクラスは、バインド要素として、アダプターを表すあります。<br /><br /> エコー アダプターのアダプターとの接続のプロパティを分類するために従う[手順 2: アダプターと接続のプロパティを分類](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)です。|  
|EchoAdapterHandlerBase.cs|これは、基本クラスによって公開されている共通のプロパティ/ヘルパー関数を格納するために使用するハンドラーの基本クラスです。<br /><br /> エコー アダプターのアダプターとの接続のプロパティを分類するために従う[手順 2: アダプターと接続のプロパティを分類](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)です。|  
|EchoAdapterConnection.cs|これは、ターゲット システムへの接続を定義します。<br /><br /> 次のターゲット システムにエコー アダプターの接続をサポートする[手順 3: エコー アダプターの接続を実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)です。|  
|EchoAdapterConnectionFactory.cs|これは、ターゲット システムの接続ファクトリを定義します。<br /><br /> 次のターゲット システムにエコー アダプターの接続をサポートする[手順 3: エコー アダプターの接続を実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)です。|  
|EchoAdapterConnectionUri.cs|これは、アダプターの接続 Uri を表すクラスです。<br /><br /> 次のターゲット システムにエコー アダプターの接続をサポートする[手順 3: エコー アダプターの接続を実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md))。|  
|EchoAdapterMetadataBrowseHandler.cs|このクラスは、対象システムからのメタデータの接続に基づく参照を実行中に使用されます。<br /><br /> 次のメタデータのエコー アダプターの機能の参照をサポートするために[手順 4: エコー アダプターのメタデータ参照ハンドラーの実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md)です。|  
|EchoAdapterMetadataSearchHandler.cs|このクラスは、ターゲット システムからのメタデータの接続ベースの検索を実行するために使用されます。<br /><br /> エコー アダプターの機能を検索するメタデータをサポートするに従って[手順 5: エコー アダプターのメタデータの検索ハンドラーの実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md)です。|  
|EchoAdapterMetadataResolve.cs|このクラスは、ターゲット システムからのメタデータの接続に基づく検索を実行するために使用されます。<br /><br /> 以下のエコー アダプターの機能を解決するメタデータをサポートするために[手順 6: エコー アダプターのメタデータを解決するハンドラーの実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md)です。|  
|EchoAdapterOutboundHandler.cs|このクラスは、ターゲット システムにデータを送信するために使用されます。<br /><br /> エコー アダプターの送信メッセージの交換をサポートするために次の[手順 7: エコー アダプターの同期送信ハンドラーの実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)です。|  
|EchoAdapterInboundHandler.cs|このクラスは、リッスンしているかにデータをポーリングのインターフェイスを実装します。<br /><br /> エコー アダプターの受信メッセージの交換をサポートするために次の[手順 8: エコー アダプターの同期受信ハンドラーの実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md)です。|  
|EchoAdapterTrace.cs|このクラスは、デバッグとトラブルシューティング用のアダプターのトレースを実装します。|  
  
## <a name="next-steps"></a>次の手順  
 UI 論理グループのアダプターとの接続のプロパティを分類し、接続、メタデータの参照、検索、および機能、および送信および受信のメッセージ交換の解決を実装するとします。 最後に、ビルドおよび展開するエコー アダプター。  
  
## <a name="see-also"></a>参照  
 [手順 2: 分類、アダプターと接続のプロパティ](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)   
 [チュートリアル 1: エコー アダプターを開発します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)