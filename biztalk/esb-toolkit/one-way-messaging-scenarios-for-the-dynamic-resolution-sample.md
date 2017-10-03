---
title: "動的解決のサンプルの一方向のメッセージング シナリオ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 38237840-e957-4298-84c9-700ec72f2bc5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8296c46561a8afa928033ae6002e3de621170234
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="one-way-messaging-scenarios-for-the-dynamic-resolution-sample"></a>動的解決のサンプルの一方向のメッセージング シナリオ
このトピックの一方向のメッセージング シナリオを実行する方法を示しています、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]動的解決のサンプルです。  
  
 **動的解決のサンプルの一方向のメッセージング シナリオを実行するには**  
  
1.  最初にこのサンプルを実行する前に、受信場所の URL を指している適切なディレクトリを確認します。 ソース サブフォルダー \Source\Samples\DynamicResolution\Test\Filedrop\In、DynamicResolution_FILE 受信場所を指定します。 さらに、DynamicResolutionOneWay をという名前の動的送信ポートが存在することを確認します。  
  
    > [!NOTE]
    >  動的解決の例では、動的な解決メカニズムを使用して、出力フォルダー、FTP サイト、または MQSeries キューにメッセージを送信します。 このサンプルの静的な送信ポートが定義されていないためにです。 動的解決のコンポーネントが解像度と出力 URL を取得し、受信場所のアダプターのプロバイダー フレームワーク、DynamicResolution_FILE 内で構成されている ESBReceiveXml パイプラインによって呼び出されたときにします。  
  
2.  GlobalBank.ESB アプリケーションが既に実行されていない場合は、Microsoft BizTalk 管理コンソールを使用して、開始します。  
  
3.  実行する例を決定します。 NAOrderDoc.xml フォルダーにある、\Source\Samples\DynamicResolution\Test\Data としてファイル入力 DynamicResolution_FILE をという名前の受信場所にすべて一方向メッセージング (を除く、XPATH の競合回避モジュールを使用する 1 つ) の例を使用してください。 7 つの一方向メッセージングの例は、それぞれ固有のバインド ファイルで表されます。 次の表では、これらの例は、その関連付けられたバインド ファイルと説明の一覧表示します。  
  
    |ファイルのファイル、静的な競合回避モジュールを使用して送信する受信します。|  
    |-------------------------------------------------------------|  
    |GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。|  
    |受信ポートでマップを静的に設定します。|  
    |エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。|  
  
    |ファイルは、UDDI リゾルバーを使用して送信ファイルを受信します。|  
    |-----------------------------------------------------------|  
    |GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。|  
    |受信ポートでマップを静的に設定します。|  
    |エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。|  
  
    |ファイルは、UDDI サービスのキーを使用して UDDI リゾルバーを使用して送信ファイルを受信します。|  
    |----------------------------------------------------------------------------|  
    |GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_SERVICEKEY_ Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。|  
    |受信ポートでマップを静的に設定します。|  
    |エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。|  
  
    > [!NOTE]
    >  前の例では、ターゲット UDDI サーバー上に存在する 1 つに、バインド ファイル内のサービス キーを変更する必要があります。  
  
    |ファイルは、FTP、静的な競合回避モジュールを使用して送信する受信します。|  
    |------------------------------------------------------------|  
    |GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC_Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。|  
    |受信ポートでマップを静的に設定します。|  
    |エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。|  
  
    |FTP の静的な競合回避モジュールと ENDPOINTCONFIG パラメーターを使用して送信するファイルの受信します。|  
    |-----------------------------------------------------------------------------------------|  
    |GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC__ ENDPOINTCONFIG_Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。|  
    |受信ポートでマップを静的に設定します。|  
    |エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。|  
    |設定するアダプター プロバイダーの追加の名前/値ペアを渡します。|  
  
    |ファイルの MQS、静的な競合回避モジュールを使用して送信する受信します。|  
    |------------------------------------------------------------|  
    |GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_MQS_STATIC_Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。|  
    |受信ポートでマップを静的に設定します。|  
    |エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。|  
  
    |ファイルのファイルを XPATH の競合回避モジュールを使用して送信する受信します。|  
    |------------------------------------------------------------|  
    |GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_XPATH_STATIC_Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。|  
    |受信ポートでマップを静的に設定します。|  
    |エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。|  
    |メッセージ内の情報を使用して、適切なエンドポイントを決定します。 この例で使用できるテスト ファイルは NAOrderDoc_XPATH_FILE.xml、NAOrderDoc_XPATH_FTP.xml、および NAOrderDoc_XPATH_MQS.xml です。|  
  
4.  GlobalBank.ESB アプリケーションを実行するメッセージの例については、バインド ファイルをインポートします。  
  
5.  Windows エクスプ ローラーでフォルダー \Source\Samples\DynamicResolution\Test\Data 開きフォルダー \Source\Samples\DynamicResolution\Test\Filedrop\In に適切な入力ファイルをコピーします。 使用するファイルは、例を実行することが決定によって異なります。  
  
    -   XPATH の例を次のファイルのいずれかを使用: NAOrderDoc_XPATH_FILE.xml、NAOrderDoc_XPATH_FTP.xml、または NAOrderDoc_XPATH_MQS.xml です。  
  
    -   その他のすべての例では、ファイル NAOrderDoc.xml を使用します。  
  
6.  配信されたメッセージの適切な場所を検索します。 場所を使用して、バインド ファイルに依存します。 例を次に示します。  
  
    -   FTP 送信の例には、ファイルの受信メッセージが配信を Out という FTP 仮想ディレクトリに、サンプルのインストール時に作成したことです。  
  
    -   送信ファイルの例には、ファイルの受信メッセージを配信します \DynamicResolution\Test\Filedrop\Out サブフォルダーです。  
  
    -   MQS 送信の例には、ファイルの受信メッセージを配信しますテストします。ときに作成したキューをサンプルのインストール。  
  
    -   メッセージで指定された場所にメッセージを配信するファイル呼び出し力方向 XPATH 競合回避モジュールの使用例を使用してファイルを受信します。 サンプル ドキュメントには、移行先の場所およびトランスポートの種類が含まれて (トランスポートの種類は、メッセージのファイル名に追加されます。 たとえば、NAOrderDoc_XPATH_FTP.xml メッセージが FTP トランスポートの型の仕様が含まれます)。  
  
 このサンプルでの ESB ディスパッチャーと ESB ディスパッチャーの逆アセンブラー パイプライン コンポーネントの使用方法を理解するのを参照してください。 [「動的解決サンプルの動作](../esb-toolkit/how-the-dynamic-resolution-sample-works.md)です。