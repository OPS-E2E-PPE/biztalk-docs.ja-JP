---
title: 確認の設定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, configuring
- acknowledgements, acknowledgement types
- configuring, acknowledgements
ms.assetid: 99ab8caa-8788-4438-96db-8001a6523cc8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34eda8a977de0dadbad974268b46e4d580cc1f33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204362"
---
# <a name="acknowledgment-settings"></a>確認の設定
使用する、**受信確認**のタブ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー (、高レベルの下で**パーティ** タブ) 確認 (ACK) の設定を構成します。  
  
 次の受信確認の種類を使用できます。  
  
-   **None**。 受信確認を構成したくない場合は、このオプションを選択します。  
  
-   **元**です。 構成するのには、このオプションを選択**MSH1 – フィールド区切り文字**、 **MSH2 – 文字のエンコード**、および**MSH8 – セキュリティ**オプションのみです。  
  
-   **強化された**です。 すべての受信確認の使用可能なオプションを構成するには、このオプションを選択します。  
  
-   **遅延**です。 構成するのには、このオプションを選択**MSH1 – フィールド区切り文字**、 **MSH2 – 文字のエンコード**、および**MSH8 – セキュリティ**オプションのみです。  
  
-   **静的**です。 構成するのには、このオプションを選択、**成功**と**エラー発生時に**受信確認のオプションです。  
  
 受信確認の種類を設定すると、受信確認の種類に応じて、ヘッダー フィールドと、受信確認の値を設定できます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [確認の構成の設定](../../adapters-and-accelerators/accelerator-hl7/ack-configuration-settings.md)  
  
-   [メッセージの受信確認を構成します。](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md)