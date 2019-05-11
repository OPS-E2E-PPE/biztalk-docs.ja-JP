---
title: 手順 6:ADT を配信する送信ポートを作成 ^ A03 メッセージをファイル アダプターを使用して RX System |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, send ports
- creating, send ports
- send ports, creating
ms.assetid: 66c4b524-c8ff-43b5-9c44-6d7bc759ae2c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7674721e3c59ea9f7af0864b2c0790ebf9a1ab92
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288005"
---
# <a name="step-6-create-a-send-port-to-deliver-the-adta03-message-to-the-rx-system-using-the-file-adapter"></a>手順 6:ADT を配信する送信ポートを作成 ^ A03 メッセージをファイル アダプターを使用して RX System
この手順で、送信ポートの薬剤システム (RX)、ファイル アダプターを使用してを作成します。  

### <a name="to-create-the-tutorialsendmsgrx-send-port"></a>Tutorial_sendMsg_RX 送信ポートを作成するには  

1. 右クリックし、BizTalk Server 管理コンソールで**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**。  

2. **送信ポートのプロパティ** ダイアログ ボックスで、次の操作を実行し、順にクリックします**OK**します。  


   |      プロパティ      |                                目的                                 |
   |--------------------|---------------------------------------------------------------------------|
   |      **名前**      |                       型**Tutorial_sendMsg_RX**します。                       |
   | **トランスポートの種類** |                 選択**ファイル**ドロップダウン リストから。                  |
   |   **構成**    | クリックして**構成**を開く、 **File トランスポートのプロパティ** ダイアログ ボックス。 |


3. ファイル トランスポートのプロパティ ダイアログ ボックスで、次の操作を実行し、 **OK**します。  


   |        プロパティ        |                                                                     目的                                                                     |
   |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
   | **コピー先フォルダー** | 参照する**\<**<em>ドライブ</em>**:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンドのアクセラレータTutorial\Tutorial_sendMsg_RX**します。 |
   |     **[ファイル名]**      |                                   型 **%MessageID%.txt** (.txt 拡張子 .xml 拡張子を置き換えます)。                                   |


4. **送信ポートのプロパティ** ダイアログ ボックスの**送信パイプライン**を選択します**BTAHL72XPipelines.BTAHL72XSendPipeline**します。  

5. 左側のウィンドウで次のように選択します。**フィルター**、し、次の操作を実行します。 続行するには、 **[OK]** をクリックします。  


   |          プロパティ          |                                            目的                                            |
   |----------------------------|--------------------------------------------------------------------------------------------------|
   | **プロパティ**(1 行目)  |                       選択**BTS します。MessageType**ドロップダウン リストから。                        |
   |        **[演算子]**        |                              選択 **! =** ドロップダウン リストから。                              |
   |         **[値]**          |                型 **<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>** します。                 |
   |        **グループ化**        |                              選択**または**ドロップダウン リストから。                              |
   | **プロパティ**(2 行目) | 下のフィールドをクリックします。**プロパティ**、し、 **BTS します。MessageType**ドロップダウン リストから。 |
   |        **[演算子]**        |                              選択 **! =** ドロップダウン リストから。                              |
   |         **[値]**          |                型**<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>します。**                 |
   |        **グループ化**        |                             選択**AND**ドロップダウン リストから。                              |
   | **プロパティ**(3 行目)  |                                 選択**BTAHL7Schemas.MSH3_1**します。                                 |
   |        **[演算子]**        |                              選択**==** ドロップダウン リストから。                              |
   |         **[値]**          |                                   型**Tutorial_ADTSystem**します。                                   |

   > [!NOTE]
   >  最初のフィルターは、病院情報システム (HIS) が受信確認にいないメッセージにサブスクライブすることを意味します。 2 番目のフィルターは、ソースが入学放電と転送 (ADT) システムは、メッセージのサブスクライブ彼はことを意味します。  

   > [!NOTE]
   >  BTAHL7 ファイルの格納場所でメッセージをドロップする\<*ドライブ*\>: Program FilesMicrosoft BizTalk <version> HL7SDKEnd ツー エンド TutorialTutorial_sendMsg_RX のアクセラレータです。  

6. クリックして**適用**、順にクリックします**ok をクリックします。**  

7. 管理コンソールで、**送信ポート**を右クリックして**Tutorial_sendMsg_RX**、順にクリックします**開始**します。  

   続行する[手順 7。ADT を配信する送信ポートを作成 ^ A03 メッセージを MLLP アダプターを使用して HIS](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md)します。