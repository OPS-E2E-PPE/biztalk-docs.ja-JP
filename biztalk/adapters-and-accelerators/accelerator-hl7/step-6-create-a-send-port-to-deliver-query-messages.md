---
title: '手順 6: クエリ メッセージを配信する送信ポートの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, send ports
ms.assetid: a3cfa2aa-888d-4a82-9eb3-2e9cc29ee582
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24e65ec7bc4e04850907609fc6d1d63e6f166593
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004051"
---
# <a name="step-6-create-a-send-port-to-deliver-query-messages"></a>手順 6: クエリ メッセージを配信する送信ポートを作成します。
この手順で受信クエリを配信する送信ポートを作成する (QRY ^ Q01 メッセージ) 病院情報システム (HIS) にします。  

### <a name="to-create-the-hissend-send-port"></a>HIS_Send 送信ポートを作成するには  

1. 右クリックし、BizTalk Server 管理コンソールで**送信ポート**、] をポイント**新規**、し、[**静的な一方向送信ポート**します。  

2. [送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。  


   |      プロパティ      |                        目的                        |
   |--------------------|----------------------------------------------------------|
   |      **名前**      |                    型**HIS_Send**します。                    |
   | **トランスポートの種類** |                     選択**MLLP**します。                     |
   |   **構成**    | をクリックして、**構成**ボタンの右側に**型**します。 |


3. MLLP トランスポートのプロパティ ダイアログ ボックスで、次の情報を入力し、クリックして**OK**します。  


   |      プロパティ       |       目的       |
   |---------------------|------------------------|
   | **接続名** | 型**HIS_SendMLLP**します。 |
   |      **ホスト**       |  型**localhost**します。   |
   |      **[ポート]**       |    型**24000**します。     |


4. 送信ポートのプロパティ ダイアログ ボックスでの**送信パイプライン**、 **BTAHL72XPipelines.BTAHL72XSendPipeline**します。  

5. コンソール ツリーで、クリックして**フィルター**、し、次の操作を行います。  


   |   プロパティ   |                              目的                               |
   |--------------|-----------------------------------------------------------------------|
   | **プロパティ** |             **プロパティ**、 **BTS します。MessageType**します。             |
   | **[演算子]** |                選択**==** ドロップダウン リストから。                 |
   |  **[値]**   | 型 **<http://microsoft.com/HealthCare/HL7/2X#QRY_Q01_24_GLO_DEF>** します。 |
   | **グループ化** |                選択**AND**ドロップダウン リストから。                |
   | **プロパティ** | **プロパティ**2 行目で、次のように選択します。 **BTAHL7Schemas.MSH5_1**します。 |
   | **[演算子]** |                選択**==** ドロップダウン リストから。                 |
   |  **[値]**   |                             型**HIS**します。                             |

   > [!NOTE]
   >  最初のフィルターは、送信ポートのみ、クエリに準拠したメッセージを選択することを指定します ^ 手順 3 a. で作成した Q01 スキーマ。 2 番目のフィルターが先を指定します、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジンはこれらのメッセージを送信します。  

6. **[OK]** をクリックします。  

7. 管理コンソールで、[**送信ポート**を右クリックして**HIS_Send**、] をクリックし、**開始**。  

   続行する[手順 7: 応答メッセージを配信する送信ポートを作成](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md)です。