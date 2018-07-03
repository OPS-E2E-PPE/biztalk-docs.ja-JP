---
title: '手順 5: ファイル アダプターを使用して ADT System に受信確認を配信する送信ポートの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, send ports
- send ports, acknowledgements
- creating, send ports
- acknowledgements, send ports
- send ports, creating
ms.assetid: 565a2adf-fd86-46e3-8035-7e4748aefffc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1421b39ed4bbd15fb82cb16ed55b23e5781eead6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002099"
---
# <a name="step-5-create-a-send-port-to-deliver-acknowledgments-to-the-adt-system-using-the-file-adapter"></a>手順 5: ファイル アダプターを使用して ADT System に受信確認を配信する送信ポートを作成します。
この手順では、ファイル アダプターを使用して受信確認を生成する送信ポートを作成します。  

### <a name="to-create-the-tutorialsendackadt-send-port"></a>Tutorial_sendAck_ADT 送信ポートを作成するには  

1. 使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、作成、 \<*ドライブ*:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンド Tutorial\Tutorial_ のアクセラレータsendAck_ADT フォルダーです。  

2. 右クリックし、BizTalk Server 管理コンソールで**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**。  

3. [送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。  


   |      プロパティ      |                                目的                                 |
   |--------------------|---------------------------------------------------------------------------|
   |      **名前**      |                      型**Tutorial_sendAck_ADT**します。                       |
   | **トランスポートの種類** |                 選択**ファイル**ドロップダウン リストから。                  |
   |   **構成**    | クリックして**構成**を開く、 **File トランスポートのプロパティ** ダイアログ ボックス。 |


4. FILE トランスポートのプロパティ ダイアログ ボックスで、次の操作し、クリックして**OK**します。  


   |        プロパティ        |                                                                     目的                                                                      |
   |------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
   | **コピー先フォルダー** | 参照する**\<**<em>ドライブ</em>**:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンドのアクセラレータTutorial\Tutorial_sendAck_ADT**します。 |
   |     **[ファイル名]**      |                                   型 **%MessageID%.txt** (.txt 拡張子 .xml 拡張子を置き換えます)。                                    |


5. 送信ポートのプロパティ ダイアログ ボックスでの**送信パイプライン**、 **BTAHL72XPipelines.BTAHL72XSendPipeline**します。  

6. 左側のウィンドウで次のようにクリックします。**フィルター**、し、次の操作を行います。  

   > [!NOTE]
   >  最初のフィルターは、受信確認メッセージをサブスクライブしていることを意味します。 2 番目のフィルターは、パブリッシャー Tutorial_ADTSystem 送信先となる受信確認をサブスクライブしていることを意味します。  

    クリックして**OK**続行する準備ができたら。  


   |          プロパティ          |                                            目的                                            |
   |----------------------------|--------------------------------------------------------------------------------------------------|
   |        **プロパティ**        | 下のフィールドをクリックします。**プロパティ**、し、 **BTS します。MessageType**ドロップダウン リストから。 |
   |        **[演算子]**        |                              選択**==** ドロップダウン リストから。                              |
   |         **[値]**          |                型 **<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>** します。                 |
   |        **グループ化**        |                              選択**または**ドロップダウン リストから。                              |
   | **プロパティ (2 行目)** | 下のフィールドをクリックします。**プロパティ**、し、 **BTS します。MessageType**ドロップダウン リストから。 |
   |        **[演算子]**        |                              選択**==** ドロップダウン リストから。                              |
   |         **[値]**          |                型**<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>します。**                 |
   |        **グループ化**        |                             選択**AND**ドロップダウン リストから。                              |
   |        **プロパティ**        |     最初のプロパティの下の空のボックスをクリックし、 **BTAHL7Schemas.MSH5_1**します。     |
   |        **[演算子]**        |                              選択**==** ドロップダウン リストから。                              |
   |         **[値]**          |                                   型**Tutorial_ADTSystem**します。                                   |

   > [!NOTE]
   >  BTAHL7 Tutorial_sendAck_ADT 送信ポートのファイルの格納場所で、受信確認を削除します\<*ドライブ*\>: Program FilesMicrosoft BizTalk <version> HL7SDKEnd ツー エンドのアクセラレータTutorialTutorial_sendAck_ADT します。  

7. クリックして**適用**、順にクリックします**ok をクリックします。**  

8. 管理コンソールで、**送信ポート**を右クリックして**Tutorial_sendAck_ADT**、順にクリックします**開始**します。  

   続行する[手順 6: ADT を配信する送信ポートを作成 ^ A03 メッセージをファイル アダプターを使用して RX System](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md)します。