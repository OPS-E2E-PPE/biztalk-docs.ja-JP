---
title: "手順 3: オーケストレーション ポートを追加、|Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 245df16e-d327-4c79-be85-004134d5ea6f
caps.latest.revision: "45"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13af336b2162e0f784195bf7c789c0dff984cb04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-add-ports-to-the-orchestration"></a>ステップ 3: オーケストレーションへのポートの追加
![手順 4 の 3](../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **所要時間:** 10 分  
  
 **目標:**このステップで、EAIProcess オーケストレーションに 3 つのポートを追加してそれらを構成します。  
  
 **目的:**ポート、オーケストレーションはメッセージを送信し、他のビジネス プロセスからメッセージを受信方法を指定します。 各ポートは、種類、方向、バインドを保持しています。これらの組み合わせによって、通信方向、通信方式、メッセージの送信先場所と送信元場所、および通信の実行方法が決まります。 このステップで作成および構成する 3 つのポートには、それぞれ次の役割があります。  
  
-   **ReceiveRequestPort**倉庫から在庫補充要求メッセージを受信します。  
  
-   **[Sendtoerp]** ERP システムに要求メッセージを転送します。  
  
-   **SendDeclinePort**要求拒否メッセージ倉庫に返送します。  
  
 詳細については、次を参照してください。[オーケストレーションで使用するポート](../core/using-ports-in-orchestrations.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このステップを開始する前に、以下の要件を確認してください。  
  
-   この手順を開始する前に行う必要があります[手順 2: ビジネス プロセスの定義](../core/step-2-define-the-business-process.md)です。  
  
## <a name="procedures"></a>手順  
  
#### <a name="to-create-and-configure-receiverequestport"></a>ReceiveRequestPort を作成および構成するには  
  
1.  ソリューション エクスプ ローラーで、 **EAIProcess.odx**です。  
  
2.  オーケストレーション デザイナで、オーケストレーション ツールボックスからドラッグして、**ポート**図形を左側の**ポート画面**並列に、 **ReceiveRequest**図形です。 ポート構成ウィザードが自動的に起動します。  
  
3.  **[ポート構成ウィザードへようこそ]** ページで、 **[次へ]**をクリックします。  
  
4.  **ポートのプロパティ** ページで、次の操作をクリックして**次**です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**ReceiveRequestPort**です。|  
  
5.  **ポートの種類を選択して** ページで、次の操作をクリックして**次**です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**このポートに使用するポートの種類を選択します。**|選択、**新しいポートの種類を作成する**オプション。|  
    |**ポートの種類名:**|型**ReceiveRequestPortType**です。|  
    |**通信方式**|選択**一方向**です。|  
    |**アクセスの制限**|選択**内部 - このプロジェクト限定**です。|  
  
6.  **ポートのバインド** ページで、次の操作をクリックして**次**です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ポートの通信方向**|選択**常にこのポートでメッセージを受信**です。|  
    |**ポートのバインド**|選択から**後指定**です。|  
  
7.  **ポート ウィザードの完了**] ページで [**完了**です。  
  
#### <a name="to-create-and-configure-senddeclineport"></a>SendDeclinePort を作成および構成するには  
  
1.  オーケストレーション ツールボックスからドラッグして、**ポート**図形を左側の**ポート画面**並列に、 **SendRequestDecline**図形です。  
  
2.  次の表に、情報を使用して、作成、 **SendDeclinePort**ポートを送信します。  
  
    |プロパティ|値|  
    |--------------|-----------|  
    |**名前**|型**SendDeclinePort**です。|  
    |**このポートに使用するポートの種類を選択します。**|選択**新しいポートの種類を作成する**です。|  
    |**ポートの種類名**|型**SendDeclinePortType**です。|  
    |**通信方式**|選択**一方向**です。|  
    |**アクセスの制限**|選択**内部 - このプロジェクト限定**です。|  
    |**ポートの通信方向**|ドロップダウン リストから選択**すればを常にメッセージを送信するこのポートで**です。|  
    |**ポートのバインド**|ドロップダウン リストから選択**後指定**です。|  
  
#### <a name="to-create-and-configure-sendtoerpport"></a>SendToERPPort を作成および構成するには  
  
1.  オーケストレーション ツールボックスからドラッグして、**ポート**図形を右側にある**ポート画面**並列に、 **SendToERP**図形です。  
  
2.  次の表に、情報を使用して、ポート構成ウィザードを完了、 **SendToERP**ポートを送信します。  
  
    |プロパティ|値|  
    |--------------|-----------|  
    |**名前**|型**SendToERPPort**です。|  
    |**このポートに使用するポートの種類を選択します。**|選択**新しいポートの種類を作成する**です。|  
    |**ポートの種類名**|型**SendToERPPortType**です。|  
    |**通信方式**|選択、**一方向**オプション。|  
    |**アクセスの制限**|選択、**内部 - このプロジェクト限定**オプション。|  
    |**ポートの通信方向**|ドロップダウン リストから選択**すればを常にメッセージを送信するこのポートで**です。|  
    |**ポートのバインド**|ドロップダウン リストから選択**後指定**です。|  
  
#### <a name="to-connect-the-ports-to-the-action-shapes"></a>ポートをアクション図形に接続するには  
  
-   オーケストレーション デザイナーのデザイン画面で、各ポートに表示されている緑色の矢印のハンドルをドラッグし、アクション図形の対応する緑色のハンドルにドロップします。  
  
    |このポートを接続します。|接続先のアクション図形|  
    |-----------------------|--------------------------|  
    |**ReceiveReqPort**|**Receive_Request**|  
    |**SendDeclinePort**|**Send_ReqDenied**|  
    |**[Sendtoerp]**|**Send_ReqToERP**|  
  
     すべてのポートが接続された EAIProcess オーケストレーションを次に示します。  
  
     ![ポートが接続された EAIProcess オーケストレーションです。] (../core/media/tut1-eaiprocessportsconnected.gif "Tut1_EAIProcessPortsConnected")  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 このステップでは、EAIProcess オーケストレーションに 3 つのポートを追加し、それらを構成しました。  
  
## <a name="next-steps"></a>次の手順  
 プロジェクトをビルドする[手順 4: EAIOrchestration プロジェクトをビルド](../core/step-4-build-the-eaiorchestration-project.md)です。  
  
## <a name="see-also"></a>参照  
 [手順 1: EAIOrchestration プロジェクトをソリューションに追加します。](../core/step-1-add-eaiorchestration-project-to-the-solution.md)   
 [手順 2: ビジネス プロセスを定義します。](../core/step-2-define-the-business-process.md)   
 [手順 4: EAIOrchestration プロジェクトをビルドします。](../core/step-4-build-the-eaiorchestration-project.md)