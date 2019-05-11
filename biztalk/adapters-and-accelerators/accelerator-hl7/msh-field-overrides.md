---
title: MSH フィールドの上書き |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- headers, overriding
- MSH Map tab [Configuration Explorer]
- headers, MSH Map tab
- messages, message headers
ms.assetid: f5b2c820-57e7-4a56-9d9f-713563bd7335
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8d0168aff76d5c0f7f408840a79b8311f2061cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290192"
---
# <a name="msh-field-overrides"></a>MSH フィールドの上書き
すべての HL7 メッセージでは、メッセージ ヘッダーがあります。 使用して[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]ビジネスのニーズに基づいて、メッセージ ヘッダーの値をオーバーライドすることができます。 使用する、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー **MSH マップ**手動で無効化がメッセージ ヘッダー値のマッピングまたはオーケストレーションを使用せずにタブ。  
  
## <a name="configuring-msh-field-overrides"></a>MSH フィールドの構成よりも優先されます。  
 使用する、 **MSH マップ**] タブの [[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー (高レベルの下で**パーティ** タブ) MSH フィールドの上書きを構成します。 このタブには、その値の上書きを使用して、MSH フィールドの値を入力する場合は、既存の送信の HL7 MSH 値メッセージ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]選択したパーティに送信します。 多くの MSH フィールドの新しい値を入力または MSH15 および MSH16 のフィールドのドロップダウン リストから値を選択できます。  
  
 次に示します、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー **MSH マップ**タブ。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-msh.gif "hl7_ops_msh")  
  
 次の手順を使用して開きます[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーおよび MSH フィールドの上書きを構成します。  
  
#### <a name="to-open-btahl7-configuration-explorer"></a>BTAHL7 構成エクスプ ローラーを開く  
  
-   をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft BizTalk\<バージョン\>Accelerator for HL7**、 をクリックし、 **BTAHL7 構成エクスプ ローラー**します。  
  
#### <a name="to-configure-msh-field-overrides"></a>MSH フィールドの上書きを構成するには  
  
1.  BTAHL7 構成エクスプ ローラーでの**MSH マップ** タブで、次の操作を行います。  
  
    > [!NOTE]
    >  Null には、既存の値を上書きするには、入力 **\\**します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**MSH.3**|メッセージの種類のフィールドは、このメッセージ ヘッダーの上書きします。|  
    |**MSH.4**|メッセージの種類のフィールドは、このメッセージ ヘッダーの上書きします。|  
    |**MSH.5**|メッセージの種類のフィールドは、このメッセージ ヘッダーの上書きします。|  
    |**MSH.6**|メッセージの種類のフィールドは、このメッセージ ヘッダーの上書きします。|  
    |**MSH.8**|メッセージの種類のフィールドは、このメッセージ ヘッダーの上書きします。|  
    |**MSH.9**|メッセージ フィールドの型がこのメッセージ ヘッダーの上書き|  
    |**MSH.12**|メッセージの種類のフィールドは、このメッセージ ヘッダーの上書きします。|  
    |**MSH.15**|Accept 受信確認の種類の受信確認オーバーライドの次のオプションから選択します。<br /><br /> -   **AL**です。 常に送信する場合、このオプションを選択して受信確認をそのまま使用します。<br />-   **NE**です。 送信しない場合は、このオプションを選択受信確認をそのまま使用します。<br />-   **SU**です。 送信する場合は、このオプションを選択して、メッセージの転送が成功した後に受信確認をそのまま使用します。<br />-   **ER**です。 送信する場合は、このオプションを選択して、エラーが発生した場合のみ肯定応答をそのまま使用します。|  
    |**MSH.16**|アプリケーションの受信確認の種類の受信確認オーバーライドの次のオプションから選択します。<br /><br /> -   **AL**です。 常にアプリケーションの受信確認を送信する場合は、このオプションを選択します。<br />-   **NE**です。 アプリケーションの受信確認を送信しない場合は、このオプションを選択します。<br />-   **SU**です。 メッセージの転送が成功した後にアプリケーションの受信確認を送信する場合は、このオプションを選択します。<br />-   **ER**です。 エラーが発生した場合のみアプリケーションの受信確認を送信する場合は、このオプションを選択します。|  
  
2.  **[保存]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [ログの構成](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)   
 [メッセージのバッチ処理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)   
[操作ログ記録、メッセージのバッチ処理、検証および受信確認の設定](../../adapters-and-accelerators/accelerator-hl7/operational-logging-message-batching-validation-and-asknowledgment-settings.md)