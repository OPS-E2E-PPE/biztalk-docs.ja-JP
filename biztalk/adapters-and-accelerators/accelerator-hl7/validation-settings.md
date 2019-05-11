---
title: 検証の設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, configuring
- configuring, validating
ms.assetid: ee08acac-99f9-4403-b2ae-01b80378aa58
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92fa9c8106dd8d00b3d7090e05d65b7d2632d193
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65285347"
---
# <a name="validation-settings"></a>検証の設定
使用して[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]、HL7 標準に対してメッセージを検証することができます。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] HL7 標準に準拠しているメッセージの構造と本文セグメントを送信または受信するメッセージがあることをによりします。 HL7 がサポートされているカスタム データ型を検証し、末尾の区切り記号を許可できます。 使用する、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー**検証**検証を構成するには、タブ。  

## <a name="configuring-validation-settings"></a>検証の設定を構成します。  
 使用する、**検証**タブ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー (高レベルの下で**パーティ** タブ) 検証の設定を構成します。 次の種類の検証を選択できます。  

- 構文、構造、およびメッセージ スキーマに基づく、本文のセグメントの概略図を検証  

- カスタム データ型 (DT、TS、TM、および TN) の HL7 標準の検証  

- (末尾の区切り記号を許可する) フィールドの区切り記号の検証  

  このタブを使用して、このパーティに対するメッセージの検証に使用するスキーマ名前空間を設定することもできます。  

  次に示します、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー**検証**タブ。  

  ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-val.gif "hl7_ops_val")  
  BTAHL7 構成エクスプ ローラーの検証 タブ  

  検証の設定を構成するのにには、次の手順を使用します。  

#### <a name="to-open-btahl7-configuration-explorer"></a>BTAHL7 構成エクスプ ローラーを開く  

-   をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft BizTalk\<バージョン\>Accelerator for HL7**、 をクリックし、 **BTAHL7 構成エクスプ ローラー**します。  

#### <a name="to-configure-validation-settings"></a>検証の設定を構成するには  

1. BTAHL7 構成エクスプ ローラーで、**検証** タブで、次の操作を行います。  


   |                  プロパティ                  |                                            目的                                            |
   |--------------------------------------------|--------------------------------------------------------------------------------------------------|
   |         **本文のセグメントを検証します。**         |             構文、構造、およびスキーマ検証を実行するには、このオプションを選択します。              |
   |       **カスタム データ型を検証します。**        |  DT、TS、TM、TN、カスタム データ型で HL7 標準の検証を実行するには、このオプションを選択します。  |
   | **末尾の区切り記号 (区切り記号) を許可します。** |           メッセージ インスタンスで末尾のフィールド区切り記号を有効にするには、このオプションを選択します。           |
   |            **スキーマの Namespace**            | スキーマ名前空間の場所を入力します。 既定値は http://microsoft.com/HealthCare/HL7/2X です。 |


2. **[保存]** をクリックします。  

## <a name="see-also"></a>参照  
 [ログの構成](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)   
 [確認の設定](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md)   
[操作ログ記録、メッセージのバッチ処理、検証および受信確認の設定](../../adapters-and-accelerators/accelerator-hl7/operational-logging-message-batching-validation-and-asknowledgment-settings.md)