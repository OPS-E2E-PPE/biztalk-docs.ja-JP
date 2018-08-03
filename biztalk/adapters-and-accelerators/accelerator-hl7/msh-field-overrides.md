---
title: MSH オーバーライド |Microsoft ドキュメント
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
ms.openlocfilehash: 7303de4a8054cfe9f7140bd6eb548c228248777c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961025"
---
# <a name="msh-field-overrides"></a>MSH フィールドの上書き
各 HL7 メッセージでは、メッセージ ヘッダーがあります。 使用して[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]は、ビジネス ニーズに基づいて、メッセージ ヘッダーの値をオーバーライドすることができます。 使用する、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー **MSH マップ**手動で無効化がメッセージ ヘッダー値のマッピングやオーケストレーションを使用せずにタブです。  
  
## <a name="configuring-msh-field-overrides"></a>オーバーライド MSH フィールドを構成します。  
 使用する、 **MSH マップ** タブで[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー (下で、高度な**パーティ** タブ) MSH フィールドの上書きを構成します。 このタブには、そのオーバーライドの値を使用して MSH フィールドの値を入力する場合は、送信 HL7 の既存の MSH 値メッセージ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]選択したパーティに送信します。 多くの MSH フィールドの新しい値を入力したり、MSH15 および MSH16 フィールドのドロップダウン リストから値を選択できます。  
  
 次の図に示しています、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー **MSH マップ**タブです。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-msh.gif "hl7_ops_msh")  
  
 開くには、次の手順を使用して[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー MSH フィールドのオーバーライドを構成するとします。  
  
#### <a name="to-open-btahl7-configuration-explorer"></a>BTAHL7 構成エクスプ ローラーを開く  
  
-   をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**、クリックして**BTAHL7 構成エクスプ ローラー**です。  
  
#### <a name="to-configure-msh-field-overrides"></a>MSH フィールドの上書きを構成するには  
  
1.  BTAHL7 構成エクスプ ローラーで、上、 **MSH マップ** タブで、次の操作します。  
  
    > [!NOTE]
    >  Null には、既存の値を変更するには、入力 **\\**です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**MSH.3**|メッセージの種類のフィールドは、このメッセージ ヘッダーの上書きします。|  
    |**MSH.4**|メッセージの種類のフィールドは、このメッセージ ヘッダーの上書きします。|  
    |**MSH.5**|メッセージの種類のフィールドは、このメッセージ ヘッダーの上書きします。|  
    |**MSH.6**|メッセージの種類のフィールドは、このメッセージ ヘッダーの上書きします。|  
    |**MSH.8**|メッセージの種類のフィールドは、このメッセージ ヘッダーの上書きします。|  
    |**MSH.9**|このメッセージ ヘッダーの上書きをメッセージの種類フィールド|  
    |**MSH.12**|メッセージの種類のフィールドは、このメッセージ ヘッダーの上書きします。|  
    |**MSH.15**|Accept 受信確認の種類の受信確認オーバーライドの次のオプションから選択します。<br /><br /> -   **AL**です。 常に送信する場合、このオプションを選択して受信確認をそのまま使用します。<br />-   **NE**です。 送信しない場合は、このオプションを選択受信確認をそのまま使用します。<br />-   **SU**です。 送信する場合は、このオプションを選択して、メッセージの転送が成功した後に受信確認をそのまま使用します。<br />-   **ER**です。 送信する場合は、このオプションを選択して、エラーが発生した場合のみ肯定応答をそのまま使用します。|  
    |**MSH.16**|アプリケーションの受信確認の種類の受信確認オーバーライドの次のオプションから選択します。<br /><br /> -   **AL**です。 常にアプリケーションの受信確認を送信する場合は、このオプションを選択します。<br />-   **NE**です。 アプリケーションの受信確認を送信しない場合は、このオプションを選択します。<br />-   **SU**です。 メッセージの転送が成功した後にアプリケーションの受信確認を送信する場合は、このオプションを選択します。<br />-   **ER**です。 エラーが発生した場合のみアプリケーションの受信確認を送信する場合は、このオプションを選択します。|  
  
2.  **[保存]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [ログの構成](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)   
 [メッセージのバッチ処理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)   
[操作ログ記録、メッセージのバッチ処理、検証および受信確認の設定](../../adapters-and-accelerators/accelerator-hl7/operational-logging-message-batching-validation-and-asknowledgment-settings.md)