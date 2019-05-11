---
title: 手順 3:オーケストレーションへのポートの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 245df16e-d327-4c79-be85-004134d5ea6f
caps.latest.revision: 45
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 310c9b5640d8b975e2f11f7ab52d314236c0d43e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392694"
---
# <a name="step-3-add-ports-to-the-orchestration"></a>手順 3:オーケストレーションへのポートの追加
![手順 4 の 3](../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **所要時間:** 10 分  
  
 **目標:** この手順では、EAIProcess オーケストレーションに 3 つのポートを追加し、それらを構成します。  
  
 **目的:** ポートは、オーケストレーションはメッセージを送信し、他のビジネス プロセスからメッセージを受信する方法を指定します。 各ポートは、種類、方向、バインドを保持しています。これらの組み合わせによって、通信方向、通信方式、メッセージの送信先場所と送信元場所、および通信の実行方法が決まります。 このステップで作成および構成する 3 つのポートには、それぞれ次の役割があります。  
  
- **ReceiveRequestPort**倉庫から在庫補充要求メッセージを受信します。  
  
- **SendToERP**要求メッセージを ERP システムに転送します。  
  
- **SendDeclinePort**要求拒否メッセージを倉庫に返送します。  
  
  詳細については、次を参照してください。[オーケストレーションで使用するポート](../core/using-ports-in-orchestrations.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 このステップを開始する前に、以下の要件を確認してください。  
  
-   この手順を開始する前に行う必要があります[手順 2。ビジネス プロセスの定義](../core/step-2-define-the-business-process.md)します。  
  
## <a name="procedures"></a>手順  
  
#### <a name="to-create-and-configure-receiverequestport"></a>ReceiveRequestPort を作成および構成するには  
  
1.  ソリューション エクスプ ローラーでダブルクリック**EAIProcess.odx**します。  
  
2.  オーケストレーション デザイナで、オーケストレーション ツールボックスからドラッグして、**ポート**図形を左側にある**ポート画面**並列に、 **ReceiveRequest**図形。 ポート構成ウィザードが自動的に起動します。  
  
3.  **[ポート構成ウィザードへようこそ]** ページで、 **[次へ]** をクリックします。  
  
4.  **ポートのプロパティ** ページで、以下を実行してをクリックし、**次**。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**ReceiveRequestPort**します。|  
  
5.  **ポートの種類を選択します。**  ページで、以下を実行して順にクリックします**次**します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**このポートに使用するポートの種類を選択します。**|選択、**新しいポートの種類を作成する**オプション。|  
    |**ポートの種類名:**|型**ReceiveRequestPortType**します。|  
    |**通信方式**|選択**一方向**します。|  
    |**アクセスの制限**|選択**内部 - このプロジェクト限定**します。|  
  
6.  **ポートのバインド** ページで、以下を実行してをクリックし、**次**します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ポートの通信方向**|選択**常にこのポートでメッセージを受信**します。|  
    |**ポートのバインド**|選択から**後で指定する**します。|  
  
7.  **ポート ウィザードの完了**] ページで [**完了**です。  
  
#### <a name="to-create-and-configure-senddeclineport"></a>SendDeclinePort を作成および構成するには  
  
1.  オーケストレーション ツールボックスからドラッグして、**ポート**図形を左側にある**ポート画面**並列に、 **SendRequestDecline**図形。  
  
2.  次の表の情報を使用して、作成、 **SendDeclinePort**ポートを送信します。  
  
    |プロパティ|値|  
    |--------------|-----------|  
    |**名前**|型**SendDeclinePort**します。|  
    |**このポートに使用するポートの種類を選択します。**|選択**新しいポートの種類を作成する**します。|  
    |**ポートの種類名**|型**SendDeclinePortType**します。|  
    |**通信方式**|選択**一方向**します。|  
    |**アクセスの制限**|選択**内部 - このプロジェクト限定**します。|  
    |**ポートの通信方向**|ドロップダウン リストから選択**は常にメッセージを送信しますこのポートで**します。|  
    |**ポートのバインド**|ドロップダウン リストから選択**後で指定する**します。|  
  
#### <a name="to-create-and-configure-sendtoerpport"></a>SendToERPPort を作成および構成するには  
  
1.  オーケストレーション ツールボックスからドラッグして、**ポート**図形を右側にある**ポート画面**並列に、 **SendToERP**図形。  
  
2.  次の表に、情報を使用して、ポート構成ウィザードを完了、 **SendToERP**ポートを送信します。  
  
    |プロパティ|値|  
    |--------------|-----------|  
    |**名前**|型**SendToERPPort**します。|  
    |**このポートに使用するポートの種類を選択します。**|選択**新しいポートの種類を作成する**します。|  
    |**ポートの種類名**|型**SendToERPPortType**します。|  
    |**通信方式**|選択、**一方向**オプション。|  
    |**アクセスの制限**|選択、**内部 - このプロジェクト限定**オプション。|  
    |**ポートの通信方向**|ドロップダウン リストから選択**は常にメッセージを送信しますこのポートで**します。|  
    |**ポートのバインド**|ドロップダウン リストから選択**後で指定する**します。|  
  
#### <a name="to-connect-the-ports-to-the-action-shapes"></a>ポートをアクション図形に接続するには  
  
-   オーケストレーション デザイナーのデザイン画面で、各ポートに表示されている緑色の矢印のハンドルをドラッグし、アクション図形の対応する緑色のハンドルにドロップします。  
  
    |このポートを接続します。|接続先のアクション図形|  
    |-----------------------|--------------------------|  
    |**ReceiveReqPort**|**Receive_Request**|  
    |**SendDeclinePort**|**Send_ReqDenied**|  
    |**SendToERP**|**Send_ReqToERP**|  
  
     すべてのポートが接続された EAIProcess オーケストレーションを次に示します。  
  
     ![ポートが接続された EAIProcess オーケストレーションです。](../core/media/tut1-eaiprocessportsconnected.gif "Tut1_EAIProcessPortsConnected")  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 このステップでは、EAIProcess オーケストレーションに 3 つのポートを追加し、それらを構成しました。  
  
## <a name="next-steps"></a>次の手順  
 プロジェクトをビルドする[手順 4。EAIOrchestration プロジェクトのビルド](../core/step-4-build-the-eaiorchestration-project.md)します。  
  
## <a name="see-also"></a>参照  
 [ステップ 1: EAIOrchestration プロジェクトをソリューションに追加します。](../core/step-1-add-eaiorchestration-project-to-the-solution.md)   
 [手順 2:ビジネス プロセスを定義します。](../core/step-2-define-the-business-process.md)   
 [手順 4:EAIOrchestration プロジェクトをビルドします。](../core/step-4-build-the-eaiorchestration-project.md)