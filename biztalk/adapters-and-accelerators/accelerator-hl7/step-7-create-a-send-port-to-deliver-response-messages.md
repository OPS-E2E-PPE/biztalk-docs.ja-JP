---
title: '手順 7: 応答メッセージを配信する送信ポートの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, send ports
ms.assetid: 5edaefb6-72f2-4317-9477-f3a0d0027e0c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4139e07c5ca503a8cb58b1aa88fe8e602a92ee07
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987827"
---
# <a name="step-7-create-a-send-port-to-deliver-response-messages"></a>手順 7: 応答メッセージを配信する送信ポートを作成します。
この手順で入学、放電、および転送 (ADT) へのクエリ応答を配信する送信ポートを作成するシステムです。  

### <a name="to-create-the-adtsend-send-port"></a>ADT_Send 送信ポートを作成するには  

1. 右クリックし、BizTalk Server 管理コンソールで**送信ポート**、] をポイント**新規**、し、[**静的な一方向送信ポート**します。  

2. [送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。  


   |      プロパティ      |                        目的                        |
   |--------------------|----------------------------------------------------------|
   |      **名前**      |                    型**ADT_Send**します。                    |
   | **トランスポートの種類** |                     選択**MLLP**します。                     |
   |   **構成**    | をクリックして、**構成**ボタンの右側に**型**します。 |


3. MLLP トランスポートのプロパティ ダイアログ ボックスで、次の情報を入力し、クリックして**OK**します。  


   |      プロパティ       |       目的       |
   |---------------------|------------------------|
   | **接続名** | 型**ADT_SendMLLP**します。 |
   |      **ホスト**       |  型**localhost**します。   |
   |      **[ポート]**       |    型**25000**します。     |


4. 送信ポートのプロパティ ダイアログ ボックスでの**送信パイプライン**、 **BTAHL72XPipelines.BTAHL72XSendPipeline**します。  

5. コンソール ツリーで、クリックして**フィルター**、し、次の操作を行います。  


   |   プロパティ   |                                        目的                                        |
   |--------------|------------------------------------------------------------------------------------------|
   | **プロパティ** |                               選択**BTS します。MessageType**します。                                |
   | **[演算子]** |                          選択**==** ドロップダウン リストから。                          |
   |  **[値]**   |          型 **<http://microsoft.com/HealthCare/HL7/2X#DSR_Q01_24_GLO_DEF>** します。           |
   | **グループ化** |                         選択**AND**ドロップダウン リストから。                          |
   | **プロパティ** | 最初のプロパティの下の空のボックスをクリックし、 **BTAHL7Schemas.MSH5_1**します。 |
   | **[演算子]** |                          選択**==** ドロップダウン リストから。                          |
   |  **[値]**   |                                      型**ADT**します。                                       |

   > [!NOTE]
   >  最初のフィルターは、送信ポートのみ DSR に準拠したメッセージを選択することを指定します ^ 手順 3 a. で作成した Q01 スキーマ。 2 番目のフィルターが先を指定します、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジンはこれらのメッセージを送信します。  

6. **[OK]** をクリックします。  

7. 管理コンソールで、**送信ポート**を右クリックして**ADT_Send**、順にクリックします**開始**します。  

   続行する[手順 8: パーティ情報の構成](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information-hl7-main.md)します。