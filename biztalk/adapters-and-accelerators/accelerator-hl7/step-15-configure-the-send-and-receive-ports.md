---
title: 手順 15 は、送信を構成し、受信ポート |Microsoft ドキュメント
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
ms.openlocfilehash: 020d83db1db86f9ff9ce116578cf58f19ba08241
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206458"
---
# <a name="step-15-configure-the-send-and-receive-ports"></a>手順 15 は、送信を構成し、受信ポート
前の手順で作成論理送信および受信ポートをオーケストレーション デザイナーを使用し、「後で」ポートのバインドの設定。 このステップでは、物理的な送信元と送信先の場所を定義して、オーケストレーションで作成した論理ポートを物理ポートをバインドして、ポートの構成を確定するのに BizTalk エクスプ ローラーを使用します。  
  
## <a name="configure-the-send-and-receive-ports"></a>構成、送信ポートと受信ポート  
  
1.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**の順に展開および**BizTalk アプリケーション 1**です。  
  
2.  右クリック**送信ポート**、新規作成 をポイントし、クリックして**静的な一方向送信ポート**です。  
  
3.  送信ポートのプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**MLLPSendPort**です。  
  
4.  **型** **MLLP**です。  
  
5.  クリックして、**構成**の右側にあるボタン、**型**フィールドです。  
  
6.  MLLP トランスポートのプロパティ ダイアログ ボックスの**接続名**入力**MLLPConnection**です。 **ホスト**入力**localhost**です。 **[OK]** をクリックします。  
  
7.  送信ポートのプロパティ ダイアログ ボックスでの**送信パイプライン**を選択**BTAHL72XPipelines.BTAHL72XSendPipeline**、順にクリック**OK**です。  
  
8.  管理コンソールで、右クリック**MLLPSendPort**ポート、およびクリックして**開始**です。  
  
9. 展開**プラットフォームの設定**、 をクリックして**ホスト インスタンス**を右クリックして**BizTalkServerApplication**、クリックして**開始**です。 ホストが既に実行されている場合にクリックして**再起動**です。  
  
10. をクリックして**オーケストレーション**を右クリックして**BTAHL7_Project.Doorbell_Orchestration**、クリックして**プロパティ**です。  
  
11. [オーケストレーションのプロパティ] ダイアログ ボックスのコンソール ツリーで、**バインド**です。  
  
12. **バインド**] ウィンドウの**ホスト**[ **BizTalkServerApplication**です。  
  
13. **SOAPReceivePort** **WebPort_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**で、**受信ポート**列です。  
  
14. **MLLPSendPort** **MLLPSendPort**で、**送信ポート/送信ポート グループ**列です。  
  
15. をクリックして**OK**変更を保存します。  
  
## <a name="msh-5-and-msh-6"></a>MSH 5 と MSH 6  
 MSH 5 および 6 の MSH ヘッダー フィールドでは、コピー先のアプリケーションと機能をそれぞれ含まれます。 構成エクスプ ローラーで、MSH 5 と MSH 6 の 3 つのコンポーネントを変更するメッセージの送信先の情報が必要な場合の各値を指定できます。 これは、元のメッセージがパーティに固有の情報が含まれない場合に可能性の高いシナリオです。 この手順では、宣言 (パブリッシャー/サブスクライバー) モデルに該当します。 環境内で適切である場合は、この手順を実行します。 これらの値の設定の詳細については、次を参照してください。 [BTAHL7 構成エクスプ ローラーの パーティ -](parties-tab.md)です。  
  
 進みます[手順 16.: オーケストレーションを開始](../../adapters-and-accelerators/accelerator-hl7/step-16-start-the-orchestration.md)です。  
  
## <a name="see-also"></a>参照  
 [メッセージの強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)