---
title: "検証の設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validating, configuring
- configuring, validating
ms.assetid: ee08acac-99f9-4403-b2ae-01b80378aa58
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 574e4a27342680ef4a37f6b12059cbf97bd9584a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="validation-settings"></a>検証の設定
使用して[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]、HL7 標準に対して、メッセージを検証することができます。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]送信または受信するメッセージが、HL7 標準に準拠しているメッセージの構造と本文セグメントを持ちます。 HL7 がサポートされているカスタム データ型を検証し、末尾の区切り記号を許可することができます。 使用する、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー**検証**検証を構成するには、タブ。  
  
## <a name="configuring-validation-settings"></a>検証の設定を構成します。  
 使用する、**検証**のタブ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー (下で、高度な**パーティ** タブ) 検証の設定を構成します。 次の種類の検証を選択します。  
  
-   構文、構造、およびメッセージ スキーマに基づく、本文のセグメントの概略図の検証  
  
-   HL7 (DT、TS、TM、および TN) にカスタム データ型の標準の検証  
  
-   フィールドの区切り記号 (末尾の区切り記号は許可されている) の検証  
  
 このタブを使用して、このパーティに対して、メッセージの検証に使用するスキーマの名前空間を設定することもできます。  
  
 次の図に示しています、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー**検証**タブです。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-val.gif "hl7_ops_val")  
BTAHL7 構成エクスプ ローラーの検証 タブ  
  
 次の手順を使用すると、検証の設定を構成できます。  
  
#### <a name="to-open-btahl7-configuration-explorer"></a>BTAHL7 構成エクスプ ローラーを開く  
  
-   をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**、クリックして**BTAHL7 構成エクスプ ローラー**です。  
  
#### <a name="to-configure-validation-settings"></a>検証の設定を構成するには  
  
1.  BTAHL7 構成エクスプ ローラーで、**検証** タブで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**本文のセグメントを検証します。**|構文、構造、およびスキーマの検証を実行するには、このオプションを選択します。|  
    |**カスタム データ型を検証します。**|DT、TS、TM、および TN のカスタム データ型で HL7 標準の検証を実行するには、このオプションを選択します。|  
    |**末尾の区切り記号 (区切り記号) を許可します。**|メッセージ インスタンスの末尾のフィールド区切り記号を有効にするには、このオプションを選択します。|  
    |**スキーマ Namespace**|スキーマ名前空間の場所を入力します。 既定値は、http://microsoft.com/HealthCare/HL7/2X です。|  
  
2.  **[保存]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [ログの構成](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)   
 [確認の設定](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md)   
[操作ログ記録、メッセージのバッチ処理、検証および受信確認の設定](../../adapters-and-accelerators/accelerator-hl7/operational-logging-message-batching-validation-and-asknowledgment-settings.md)