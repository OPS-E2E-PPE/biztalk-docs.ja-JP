---
title: SWIFT へのメッセージの FRR 送信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, send ports
- send ports, FRR
ms.assetid: 905c69a3-dff3-4a60-803d-dd617ffb6896
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa0de25c96ec7d685fa68b1d2bd675d95dea0cda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378077"
---
# <a name="frr-send-port-for-messages-to-swift"></a>SWIFT へのメッセージの FRR 送信ポート
FIN 応答 reconciliation (FRR) を有効にするには、MQSeries の SAA BizTalk アダプターを経由するメッセージを送信する FRR 送信ポートを設定する必要があります。 この送信ポートのルート カスタム FRR 経由でメッセージの送信パイプライン コンポーネント、次のパイプライン コンポーネントを使用して作成する必要があります。  
  
- アセンブル ステージで SWIFT アセンブラー  
  
- エンコード段階で SWIFTAsmFrrMQSeriesHelper パイプライン コンポーネント  
  
  SWIFTAsmFrrMQSeriesHelper パイプライン コンポーネントは、FRRCorrelationToken プロパティの値を送信メッセージの MQMD_MsgID プロパティを設定します。 また、割り当てし、パイプラインのデザイン時に設定されている値"MQ"で始まるその他の必要なコンテキスト プロパティを昇格させます。 送信パイプラインには、構成可能なプロパティとして MQSeries に対して定義されている各プロパティが含まれています。 各値は「使われない」既定値です。  
  
  送信ポートを持つメッセージを処理する[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed False = = と[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND True = =。 トランスポート メカニズムでは、BizTalk Adapter for MQSeries です。 断片化のサイズなどのトランスポートのプロパティについては、MQSeries のドキュメントを参照してください。