---
title: 動的解決サンプルの一方向のメッセージング シナリオ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 38237840-e957-4298-84c9-700ec72f2bc5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 359b91a1a5da9ce435d3d9aa5884d6928d0e0a9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987539"
---
# <a name="one-way-messaging-scenarios-for-the-dynamic-resolution-sample"></a>動的解決サンプルの一方向のメッセージング シナリオ
このトピックでは、の一方向メッセージング シナリオを実行する方法、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]動的解決サンプル。  

 **動的解決サンプルの一方向メッセージング シナリオを実行するには**  

1. 最初にこのサンプルを実行する前に、受信場所の URL を指している適切なディレクトリを確認します。 ソースのサブフォルダー \Source\Samples\DynamicResolution\Test\Filedrop\In、DynamicResolution_FILE 受信場所を指定します。 さらに、DynamicResolutionOneWay をという名前の動的送信ポートが存在することを確認します。  

   > [!NOTE]
   >  動的解決サンプルでは、動的解決の機構を使用して、出力フォルダー、FTP サイト、または MQSeries キューにメッセージを送信します。 このサンプルの静的な送信ポートが定義されていないためにです。 動的解決のコンポーネントは、解像度から出力 URL を取得し、受信場所のアダプターのプロバイダー フレームワーク、DynamicResolution_FILE 内で構成されている ESBReceiveXml パイプラインによって呼び出されたときにします。  

2. GlobalBank.ESB アプリケーションが実行されていない場合は、Microsoft の BizTalk 管理コンソールを使用して、開始します。  

3. 実行する例を決定します。 DynamicResolution_FILE という名前の受信場所に入力 NAOrderDoc.xml として \Source\Samples\DynamicResolution\Test\Data フォルダーにあるファイルをすべて一方向メッセージング (を除く、XPATH の競合回避モジュールを使用する 1 つ) の例を使用します。 7 つの一方向メッセージングの例は、それぞれの一意のバインド ファイルで表されます。 次の表は、その関連付けられたバインド ファイルの説明と、これらの例を一覧表示します。  

   |ファイルの受信ファイル、静的な競合回避モジュールを使用して送信する|  
   |-------------------------------------------------------------|  
   |受信場所を設定し、送信ポートのプロパティを GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml をという名前のバインド ファイルを使用します。|  
   |受信ポートでマップを静的に設定します。|  
   |ESB ディスパッチャーを受信場所でエンドポイントの解決を使用します。|  

   |ファイルに着信する UDDI リゾルバーを使用して送信ファイル|  
   |-----------------------------------------------------------|  
   |受信場所を設定し、送信ポートのプロパティを GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_Bindings.xml をという名前のバインド ファイルを使用します。|  
   |受信ポートでマップを静的に設定します。|  
   |ESB ディスパッチャーを受信場所でエンドポイントの解決を使用します。|  

   |UDDI サービスのキーを使用して UDDI リゾルバーを使用して送信ファイルへのファイルの受信します。|  
   |----------------------------------------------------------------------------|  
   |受信場所を設定し、送信ポートのプロパティを GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_SERVICEKEY_ Bindings.xml をという名前のバインド ファイルを使用します。|  
   |受信ポートでマップを静的に設定します。|  
   |ESB ディスパッチャーを受信場所でエンドポイントの解決を使用します。|  

   > [!NOTE]
   >  前の例では、ターゲットの UDDI サーバー上に存在する 1 つに、バインド ファイルにサービス キーを変更する必要があります。  

   |ファイルが着信 FTP 静的リゾルバーを使用して送信する|  
   |------------------------------------------------------------|  
   |受信場所を設定し、送信ポートのプロパティを GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC_Bindings.xml をという名前のバインド ファイルを使用します。|  
   |受信ポートでマップを静的に設定します。|  
   |ESB ディスパッチャーを受信場所でエンドポイントの解決を使用します。|  

   |ファイルが着信 FTP 静的競合回避モジュールと ENDPOINTCONFIG パラメーターを使用して送信する|  
   |-----------------------------------------------------------------------------------------|  
   |受信場所を設定し、送信ポートのプロパティを GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC__ ENDPOINTCONFIG_Bindings.xml をという名前のバインド ファイルを使用します。|  
   |受信ポートでマップを静的に設定します。|  
   |ESB ディスパッチャーを受信場所でエンドポイントの解決を使用します。|  
   |設定するアダプター プロバイダーの追加の名前/値ペアを渡します。|  

   |ファイルの着信 MQS 静的リゾルバーを使用して送信する|  
   |------------------------------------------------------------|  
   |受信場所を設定し、送信ポートのプロパティを GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_MQS_STATIC_Bindings.xml をという名前のバインド ファイルを使用します。|  
   |受信ポートでマップを静的に設定します。|  
   |ESB ディスパッチャーを受信場所でエンドポイントの解決を使用します。|  

   |                                                                             ファイルの着信ファイルを XPATH の競合回避モジュールを使用して送信する                                                                             |
   |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                        受信場所を設定し、送信ポートのプロパティを GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_XPATH_STATIC_Bindings.xml をという名前のバインド ファイルを使用します。                        |
   |                                                                                 受信ポートでマップを静的に設定します。                                                                                  |
   |                                                                    ESB ディスパッチャーを受信場所でエンドポイントの解決を使用します。                                                                    |
   | メッセージ内の情報を使用して、適切なエンドポイントを決定します。 この例で使用できるテスト ファイルには、NAOrderDoc_XPATH_FILE.xml、NAOrderDoc_XPATH_FTP.xml、NAOrderDoc_XPATH_MQS.xml が。 |


4. メッセージングに GlobalBank.ESB アプリケーションを実行する例については、バインド ファイルをインポートします。  

5. Windows エクスプ ローラーでフォルダー \Source\Samples\DynamicResolution\Test\Data 開きフォルダー \Source\Samples\DynamicResolution\Test\Filedrop\In に適切な入力ファイルをコピーします。 使用するファイルは、実行することを決定した例では、によって異なります。  

   -   XPATH の例で、次のファイルのいずれかを使用: NAOrderDoc_XPATH_FILE.xml、NAOrderDoc_XPATH_FTP.xml、または NAOrderDoc_XPATH_MQS.xml します。  

   -   その他のすべての例では、NAOrderDoc.xml ファイルを使用します。  

6. 適切な場所に配信されたメッセージを確認します。 場所は、使用するバインド ファイルに依存します。 例を次に示します。  

   -   FTP 送信の例は、ファイルの受信、メッセージを配信をという名前の FTP 仮想ディレクトリ、サンプルのインストール時に作成したこと。  

   -   \DynamicResolution\Test\Filedrop\Out サブフォルダーに、メッセージを配信する送信ファイルの例にファイルを受信します。  

   -   MQS 送信の例は、ファイルの受信には、テストにメッセージが配信されます。時に作成したキューをサンプルのインストール。  

   -   ファイル送信の例では、XPATH の競合回避モジュールを使用するファイルの受信メッセージで指定した場所にメッセージが配信されます。 サンプル ドキュメントには、移行先の場所およびトランスポートの種類を含めることが (トランスポートの種類がメッセージのファイル名に追加されます。 たとえば、NAOrderDoc_XPATH_FTP.xml メッセージには、FTP トランスポートの型の仕様が含まれます。)。  

   ESB ディスパッチャーと ESB ディスパッチャー逆アセンブラー パイプライン コンポーネントのサンプルの使用については、[、動的解決サンプルのしくみ](../esb-toolkit/how-the-dynamic-resolution-sample-works.md)を参照してください。