---
title: 手順 7:ADT を配信する送信ポートを作成 ^ A03 メッセージを MLLP アダプターを使用して HIS |Microsoft Docs
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
ms.assetid: d9e7f281-3d25-4675-a13e-0e2057f5e69a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49d75da284ecbf0852d62e614cae2a787bc6dc52
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65287919"
---
# <a name="step-7-create-a-send-port-to-deliver-the-adta03-message-to-his-using-the-mllp-adapter"></a>手順 7:ADT を配信する送信ポートを作成 ^ A03 メッセージを MLLP アダプターを使用して HIS
この手順では、MLLP アダプターを使用して医療情報システム (HIS) にメッセージを送信する送信ポートを作成します。  

### <a name="to-create-the-tutorialmllpsend-send-port"></a>Tutorial_MllpSend 送信ポートを作成するには  

1. 右クリックし、BizTalk Server 管理コンソールで**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**。  

2. 送信ポートのプロパティ ダイアログ ボックスで、次の操作を行います。  


   |      プロパティ      |                                目的                                 |
   |--------------------|---------------------------------------------------------------------------|
   |      **名前**      |                        型**Tutorial_MllpSend**します。                        |
   | **トランスポートの種類** |                 選択**MLLP**ドロップダウン リストから。                  |
   |   **構成**    | クリックして**構成**を開く、 **MLLP トランスポート プロパティ** ダイアログ ボックス。 |


3. MLLP トランスポートのプロパティ ダイアログ ボックスで、次の操作を行ってをクリックして**OK**します。  


   |      プロパティ       |     目的      |
   |---------------------|---------------------|
   | **接続名** | 型**1WaySend**します。  |
   |      **ホスト**       | 型**localhost**します。 |
   |      **[ポート]**       |   型**14000**します。   |


4. 送信ポートのプロパティ ダイアログ ボックスでの**送信パイプライン**、 **BTAHL72XPipelines.BTAHL72XSendPipeline**します。  

5. 左側のウィンドウで次のように選択します。**フィルター**、し、次の操作を行います。  

   |プロパティ|目的|  
   |--------------|----------------|  
   |**プロパティ**|選択**BTS します。ReceivePortName**ドロップダウン リストから。|  
   |**[演算子]**|選択**==** ドロップダウン リストから。|  
   |**[値]**|型**Tutorial_1WayReceive**します。|  

   > [!NOTE]
   >  ポートのメッセージ 1WayReceive で指定されたポートをリッスンします。  

6. クリックして**適用**、順にクリックします**ok をクリックします。**  

7. 管理コンソールで、**送信ポート**を右クリックして**Tutorial_MllpSend**、順にクリックします**開始**します。  

   続行する[手順 8。パーティ情報の構成](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md)します。