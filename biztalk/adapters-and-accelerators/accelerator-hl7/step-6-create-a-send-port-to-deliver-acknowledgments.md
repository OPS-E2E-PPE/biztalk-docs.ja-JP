---
title: '手順 6: 受信確認を配信する送信ポートの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 739b3e60-db56-46e9-a6b1-0acbe0c08f55
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47e30db70d67cb70ba87cf661e46ca325de1f3cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003619"
---
# <a name="step-6-create-a-send-port-to-deliver-acknowledgments"></a>手順 6: 受信確認を配信する送信ポートを作成します。
この手順では、バッチのソースへの受信確認を返信するポートを作成します。  

 MLLP アダプターでは、関連付けられているのみなります、、特定の宛先 (バッチのソース) にのみ送信されるように静的であるには、このポートを作成します。 このチュートリアルでは、ソースは、Tutorial_BatchSource パーティに関連付けられます。 この送信元パーティは、個々 のメッセージと FHS3 MSH3 と元のバッチの BHS3 に含まれます。  

 受信確認をしないデータ メッセージの送信にポートを制限するフィルターを使用してポートを作成します。 これらのフィルターは、ACK_024_GLO_DEF および Tutorial_BatchSource の変換先のメッセージの種類を指定します。  

 この送信ポート構成受信確認を宛先からという名前の受信ポートと送信ポートを関連付けることによって**TwoWayAckReceivePort**します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] セットアップ、このポートを作成してに付属の受信場所の**TwoWayAckReceiveLocation**します。 設定して、このポートを使用する送信ポートを設定する**送信請求-応答を有効にする**に**いいえ**と設定、**受信場所の URI を送信**に**127.0.0.1:65535** (Ack をそのまま使用するために必要な設定)。 詳細については、次を参照してください。[設定を、送信ポートの受信確認の](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)します。  

### <a name="to-create-a-send-port-to-deliver-acknowledgments"></a>確認を配信する送信ポートを作成するには  

1. 右クリックし、BizTalk Server 管理コンソールで**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**。  

2. [送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。  


   |      プロパティ      |                                目的                                 |
   |--------------------|---------------------------------------------------------------------------|
   |      **名前**      |                        型**Tutorial_2wayAck**します。                         |
   | **トランスポートの種類** |                 選択**MLLP**ドロップダウン リストから。                  |
   |   **構成**    | クリックして**構成**を開く、 **MLLP トランスポート プロパティ** ダイアログ ボックス。 |


3. MLLP トランスポートのプロパティ ダイアログ ボックスで、次の手順を実行します。  


   |                 プロパティ                  |        目的         |
   |-------------------------------------------|---------------------------|
   |            **接続名**            |     型**2wayAck**します。     |
   |                 **ホスト**                  |    型**localhost**します。    |
   |                 **[ポート]**                  |      型**41002**します。      |
   |       **有効になっている応答を送信請求します。**        | フィールドとして保持**いいえ**します。 |
   | **送信の受信確認の場所 (URI)** | 型**127.0.0.1:65535**  |


4. **[OK]** をクリックします。  

5. 送信ポートのプロパティ ダイアログ ボックスでの**送信パイプライン**、 **BTAHL72XPipelines.BTAHL72XSendPipeline**します。  

6. コンソール ツリーで、クリックして**フィルター**、し、次の操作を行います。  

   > [!NOTE]
   >  次のデータを示すとおりに入力することを確認します。 このデータは、大文字小文字を区別します。  

   |          プロパティ          |                                            目的                                            |
   |----------------------------|--------------------------------------------------------------------------------------------------|
   | **プロパティ**(1 行目)  |   下のフィールドをクリックします。**プロパティ**を選択し、 **BTS します。MessageType**ドロップダウン リストから。   |
   |        **[演算子]**        |                              選択**==** ドロップダウン リストから。                              |
   |         **[値]**          |                型 **<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>** します。                 |
   |        **グループ化**        |                              選択**または**ドロップダウン リストから。                              |
   | **プロパティ**(2 行目) | 下のフィールドをクリックします。**プロパティ**、し、 **BTS します。MessageType**ドロップダウン リストから。 |
   |        **[演算子]**        |                              選択**==** ドロップダウン リストから。                              |
   |         **[値]**          |                型**<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>します。**                 |
   |        **グループ化**        |                             選択**と**ドロップダウン リストから。                              |
   | **プロパティ**(3 行目)  |   下にある 2 番目の行のフィールドをクリックします。**プロパティ**を選択し、 **BTAHL7Schemas.MSH5_1**します。   |
   |        **[演算子]**        |                              選択**==** ドロップダウン リストから。                              |
   |         **[値]**          |                                  型**Tutorial_BatchSource**します。                                  |

   > [!NOTE]
   >  最初のフィルターは、受信確認メッセージをサブスクライブしていることを意味します。 2 番目のフィルターは、発行元の変換先を含む受信確認をすることを意味**Tutorial_BatchSource**します。  

7. **Enter**をクリックします。 クリックしてダイアログ ボックスの下部にあるウィンドウで、フィルター式の入力が正しいことを確認します**OK**します。  

8. 管理コンソールで、**送信ポート**を右クリックして**Tutorial_2wayAck**、し、**開始**します。  

   > [!NOTE]
   >  TwoWayAckReceivePort を有効にする必要があります、Tutorial_2wayAck ご送信ポートが正しく機能する、受信場所。  

9. クリックして**受信場所**します。 TwoWayAckReceiveLocation の状態が有効になっていることを確認します。 ない場合を右クリックして**TwoWayAckReceiveLocation**、 をクリックし、**を有効にする**します。  

   進みます[手順 7: を作成し、送信元パーティを構成する](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)します。