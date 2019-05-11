---
title: 手順 15:構成、送信ポートと受信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, ports
ms.assetid: d532b196-473e-4c8f-b4ed-acef674fc698
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efb16b8222e3ef2c6afebe0aaf63a0e203afc73e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289032"
---
# <a name="step-15-configure-the-send-and-receive-ports"></a>手順 15:構成、送信ポートと受信ポート
前の手順で作成論理送信と受信ポートをオーケストレーション デザイナーを使用し、「後で指定」をポートのバインドを設定します。 この手順では、物理のソースと変換先の場所を定義して、オーケストレーションで作成した論理ポートを物理ポートをバインドして、ポートの構成を確定するのに BizTalk エクスプ ローラーを使用します。  
  
## <a name="configure-the-send-and-receive-ports"></a>構成、送信ポートと受信ポート  
  
1.  BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**を展開し**BizTalk アプリケーション 1**します。  
  
2.  右クリックして**送信ポート**に新規作成 をポイントしてクリックして**静的な一方向送信ポート**します。  
  
3.  送信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに「 **MLLPSendPort**します。  
  
4.  **型**、 **MLLP**します。  
  
5.  をクリックして、**構成**ボタンの右側に、**型**フィールド。  
  
6.  MLLP トランスポートのプロパティ ダイアログ ボックスでの**接続名**入力**MLLPConnection**します。 **ホスト**入力**localhost**します。 **[OK]** をクリックします。  
  
7.  送信ポートのプロパティ ダイアログ ボックスでの**送信パイプライン**を選択します**BTAHL72XPipelines.BTAHL72XSendPipeline**、 をクリックし、 **OK**。  
  
8.  管理コンソールで、右クリック**MLLPSendPort**ポート、およびクリックして**開始**します。  
  
9. 展開**プラットフォームの設定**、 をクリックして**ホスト インスタンス**を右クリックして**BizTalkServerApplication**、順にクリックします**開始**します。 ホストが既に実行されている場合はクリックして**再起動**します。  
  
10. をクリックして**オーケストレーション**を右クリックして**BTAHL7_Project.Doorbell_Orchestration**、 をクリックし、**プロパティ**します。  
  
11. オーケストレーションのプロパティ] ダイアログ ボックスのコンソール ツリーで [**バインド**します。  
  
12. **バインド**ウィンドウの**ホスト**を選択します**BizTalkServerApplication**します。  
  
13. **SOAPReceivePort**、 **WebPort_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**で、**受信ポート**列。  
  
14. **MLLPSendPort**、 **MLLPSendPort**で、**送信ポート/送信ポート グループ**列。  
  
15. **[OK]** をクリックして変更を保存します。  
  
## <a name="msh-5-and-msh-6"></a>MSH 5 および MSH 6  
 MSH 5 および MSH 6 ヘッダー フィールドでは、コピー先のアプリケーションと機能をそれぞれ含まれます。 構成エクスプ ローラーで変更するメッセージの変換先の情報を表示する場合の MSH 5 および MSH 6、3 つのコンポーネントの各値を指定できます。 これは、元のメッセージがパーティに固有の情報が含まれない場合、可能性の高いシナリオです。 この手順は、宣言型 (パブリッシャー/サブスクライバー) モデルに適用できます。 環境内で該当する場合は、この手順を実行します。 これらの値を設定する方法についての詳細については、次を参照してください。[パーティー - BTAHL7 構成エクスプ ローラー](parties-tab.md)します。  
  
 続行する[手順 16。オーケストレーションを開始](../../adapters-and-accelerators/accelerator-hl7/step-16-start-the-orchestration.md)します。  
  
## <a name="see-also"></a>参照  
 [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)