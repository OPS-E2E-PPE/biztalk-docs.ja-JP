---
title: "手順 6: 受信確認を配信する送信ポートの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 739b3e60-db56-46e9-a6b1-0acbe0c08f55
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 978ccb9bf01fe71c3ccce7315e0286ee862bb7ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-6-create-a-send-port-to-deliver-acknowledgments"></a>手順 6: 受信確認を配信する送信ポートを作成します。
この手順では、バッチの発生元への受信確認を返信するポートを作成します。  
  
 これはのみに関連付けられます MLLP アダプター、およびが特定の送信先 (バッチのソース) にのみ送信できるように、静的であるにこのポートを作成します。 このチュートリアルでは、ソースは、パーティ Tutorial_BatchSource に関連付けられます。 この送信元パーティは、個々 のメッセージと FHS3 MSH3 と元のバッチの BHS3 に含まれます。  
  
 いないデータ メッセージの受信確認を送信するポートを制限するフィルターを使用して、ポートを作成します。 これらのフィルターは、ACK_024_GLO_DEF と Tutorial_BatchSource の出力先のメッセージの種類を指定します。  
  
 この送信ポート構成受信確認をターゲットという名前の受信ポートと送信ポートを関連付けることによって**TwoWayAckReceivePort**です。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]セットアップはこのポートを作成しに付属の受信場所の**TwoWayAckReceiveLocation**です。 設定して、このポートを使用する送信ポートを設定する**送信請求-応答を有効にする**に**いいえ**と設定、**受信場所の URI を送信**に**127.0.0.1:65535** (Ack を受け入れるように必要な設定)。 詳細については、次を参照してください。[設定を、送信ポートの受信確認の](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)します。  
  
### <a name="to-create-a-send-port-to-deliver-acknowledgments"></a>受信確認を配信する送信ポートを作成するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。  
  
2.  [送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**Tutorial_2wayAck**です。|  
    |**トランスポートの種類**|選択**MLLP**ドロップダウン リストからです。|  
    |**構成**|をクリックして**構成**を開くには、 **MLLP トランスポートのプロパティ** ダイアログ ボックス。|  
  
3.  MLLP トランスポートのプロパティ ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**接続名**|型**2wayAck**です。|  
    |**ホスト**|型**localhost**です。|  
    |**[ポート]**|型**41002**です。|  
    |**送信請求応答を有効になっています。**|としてフィールドを保持**いいえ**です。|  
    |**送信の受信確認の場所 (URI)**|型**127.0.0.1:65535**|  
  
4.  **[OK]**をクリックします。  
  
5.  送信ポートのプロパティ] ダイアログ ボックスの**送信パイプライン**[ **BTAHL72XPipelines.BTAHL72XSendPipeline**です。  
  
6.  コンソール ツリーでクリックして**フィルター**、し、次の操作を行います。  
  
    > [!NOTE]
    >  次のデータを示すとおりに入力することを確認します。 このデータは、大文字小文字を区別します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ**(1 行目)|下のフィールドをクリックして**プロパティ**選択してから、 **BTS です。MessageType**ドロップダウン リストからです。|  
    |**演算子**|選択 **==** ドロップダウン リストからです。|  
    |**値**|型**http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**です。|  
    |**グループ化**|選択**または**ドロップダウン リストからです。|  
    |**プロパティ**(2 番目の行)|下のフィールドをクリックして**プロパティ**、し、 **BTS です。MessageType**ドロップダウン リストからです。|  
    |**演算子**|選択 **==** ドロップダウン リストからです。|  
    |**値**|型**http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF です。**|  
    |**グループ化**|選択**と**ドロップダウン リストからです。|  
    |**プロパティ**(3 行目)|下にある 2 番目の行でフィールドをクリックして**プロパティ**選択してから、 **BTAHL7Schemas.MSH5_1**です。|  
    |**演算子**|選択 **==** ドロップダウン リストからです。|  
    |**値**|型**Tutorial_BatchSource**です。|  
  
    > [!NOTE]
    >  最初のフィルターは、受信確認メッセージをサブスクライブしたことを意味します。 2 番目のフィルターは、パブリッシャーでのコピー先を持つことを確認することを意味**Tutorial_BatchSource**です。  
  
7.  **Enter**をクリックします。 クリックしてダイアログ ボックスの下部にあるペインで、フィルター式の入力が正しいことを確認してください**OK**です。  
  
8.  管理コンソールで **送信ポート**を右クリックして**Tutorial_2wayAck**、し、**開始**です。  
  
    > [!NOTE]
    >  TwoWayAckReceivePort を有効にする必要があります、Tutorial_2wayAck の送信ポートが正しく機能するの受信場所。  
  
9. をクリックして**受信場所**です。 TwoWayAckReceiveLocation の状態が有効になっていることを確認します。 いない場合を右クリックし**TwoWayAckReceiveLocation**、クリックして**を有効にする**です。  
  
 進みます[手順 7: を作成し、送信元パーティを構成する](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)です。