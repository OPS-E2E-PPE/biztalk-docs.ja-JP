---
title: "手順 5: メッセージを配信する送信ポートの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f56ad7a7-5c77-4191-a001-691e5e0652a1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e85033256f7a49ed506fea00a7b48db67b0da1b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-create-a-send-port-to-deliver-messages"></a>手順 5: メッセージを配信する送信ポートを作成します。
このステップでは、作成し、受信したバッチに含まれている個々 のメッセージを送信するためのポートを構成します。 チュートリアルの後半では、送信元パーティ (Tutorial_BatchSource) の断片化を有効[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。 その結果、BizTalk 統合エンジンをフラグメント化、バッチを個別のメッセージと[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]この手順で作成した送信ポート経由でそれらのメッセージを送信します。  
  
 これはのみに関連付けられます MLLP アダプター、およびが特定の送信先 (送信先の基幹業務アプリケーション) にのみ送信できるように、静的であるにこのポートを作成します。 このチュートリアルでは、その出力先で MESA_IS、MSH5、個々 のメッセージに含まれているとします。 ACK_024_GLO_DEF スキーマまたは静的の確認 (ACK) に準拠したメッセージをフィルター処理していない受信確認のメッセージを送信するポートを制限するフィルターを使用して、ポートを作成します。  
  
 この送信ポート構成の Ack を受信する、ターゲットという名前の受信ポートと送信ポートを関連付けることによって**TwoWayAckReceivePort**です。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]セットアップはこのポートを作成しに付属の受信場所の**TwoWayAckReceiveLocation**です。 設定して、このポートを使用する送信ポートを設定する**送信請求-応答を有効にする**に**はい**と設定、**受信場所の URI を送信**に**127.0.0.1:65535** (Ack を受け入れるように必要な設定)。 詳細については、次を参照してください。[設定を、送信ポートの受信確認の](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)します。  
  
### <a name="to-create-a-send-port-to-deliver-messages"></a>メッセージを配信する送信ポートを作成するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。  
  
2.  [送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**Tutorial_2wayMsg**です。|  
    |**トランスポートの種類**|選択**MLLP**ドロップダウン リストからです。|  
    |**構成**|をクリックして**構成**MLLP トランスポートのプロパティ ダイアログ ボックスを開きます。|  
  
3.  MLLP トランスポートのプロパティ ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**接続名**|型**2wayMsg**です。|  
    |**ホスト**|型**localhost**です。|  
    |**[ポート]**|型**41000**です。|  
    |**送信請求応答を有効になっています。**|フィールドの右側をクリックして**送信請求-応答の有効な**、し、**はい**ドロップダウン リストからです。|  
    |**送信の受信確認の場所 (URI)**|型**127.0.0.1:65535**|  
  
4.  **[OK]**をクリックします。  
  
5.  送信ポートのプロパティ] ダイアログ ボックスの**送信パイプライン**[ **BTAHL72XPipelines.BTAHL72XSendPipeline**です。  
  
6.  コンソール ツリーでクリックして**フィルター**、し、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ**(1 行目)|下のフィールドをクリックして**プロパティ**、し、 **BTS です。MessageType**ドロップダウン リストからです。|  
    |**演算子**|選択**! =**ドロップダウン リストからです。|  
    |**値**|型**http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**です。|  
    |**グループ化**|選択**AND**ドロップダウン リストからです。|  
    |**プロパティ**(2 番目の行)|下のフィールドをクリックして**プロパティ**、し、 **BTS です。MessageType**ドロップダウン リストからです。|  
    |**演算子**|選択**! =**ドロップダウン リストからです。|  
    |**値**|型**http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF です。**|  
    |**グループ化**|選択**と**ドロップダウン リストからです。|  
    |**プロパティ**(3 行目)|下にある 2 番目の行でフィールドをクリックして**プロパティ**、し、 **BTS です。MessageType**ドロップダウン リストからです。|  
    |**演算子**|選択**! =**ドロップダウン リストからです。|  
    |**値**|型**StaticAck**です。|  
  
7.  **Enter**をクリックします。 クリックしてダイアログ ボックスの下部にあるペインで、フィルター式の入力が正しいことを確認してください**OK**です。  
  
8.  管理コンソールで、をクリックして**送信ポート**を右クリックして**Tutorial_2wayMsg**、クリックして**開始**です。  
  
 進みます[手順 6: 受信確認を配信する送信ポートを作成](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-acknowledgments.md)です。