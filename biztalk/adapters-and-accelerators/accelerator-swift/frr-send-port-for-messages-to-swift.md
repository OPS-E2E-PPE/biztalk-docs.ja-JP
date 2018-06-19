---
title: SWIFT メッセージの送信ポートを FRR |Microsoft ドキュメント
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
ms.openlocfilehash: 6a442b45f57009b839b4e184ef9662b253ba32b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209362"
---
# <a name="frr-send-port-for-messages-to-swift"></a>SWIFT メッセージの送信ポートを FRR
FIN 対応調整 (FRR) を有効にするには、MQSeries の SAA BizTalk アダプターを経由するメッセージを送信する FRR 送信ポートを設定する必要があります。 この送信ポート ルート カスタム FRR 経由でメッセージの送信パイプライン コンポーネントを次のパイプライン コンポーネントを作成する必要があります。  
  
-   アセンブル ステージに SWIFT アセンブラー  
  
-   エンコード ステージに SWIFTAsmFrrMQSeriesHelper パイプライン コンポーネント  
  
 SWIFTAsmFrrMQSeriesHelper パイプライン コンポーネントでは、FRRCorrelationToken プロパティの値を送信メッセージの MQMD_MsgID プロパティを設定します。 また、によって割り当てられ、値がパイプラインのデザイン時に設定された以降"MQ"で必要なコンテキスト プロパティを昇格させます。 送信パイプラインには、構成可能なプロパティとして MQSeries に対して定義されている各プロパティが含まれています。 各値は、「不使用」既定値です。  
  
 送信ポートがメッセージを処理する[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed = = False と[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND = = True です。 トランスポート機構では、BizTalk Adapter for MQSeries がします。 フラグメント化サイズなどのトランスポートのプロパティに関する情報は、MQSeries のマニュアルを参照してください。