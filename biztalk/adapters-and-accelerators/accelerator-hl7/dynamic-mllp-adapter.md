---
title: 動的 MLLP アダプター |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e22fabb-0edf-4931-b8b2-74a5daccee4a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf7d1d7046135de1dc1837d1fb8961ef440b5009
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204730"
---
# <a name="dynamic-mllp-adapter"></a>動的 MLLP アダプター
以降で[!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)]、一方向または双方向 (要求-応答) の送信ポートを使用して実行時に MLLP アダプターのプロパティを構成することができます。  
  
## <a name="dynamic-properties"></a>動的プロパティ  
 次のプロパティが、 **GlobalPropertySchemas**名前空間。  
  
|プロパティ|Description|  
|--------------|-----------------|  
|メッセージ (MLLP.acceptableACKCodes) =「すべての確認コード」です。|値は次のとおりです。<br /><br /> -すべての確認コード<br />-AA と CA<br />-AA、カナダ、AE および CE<br />-AA、カナダ、AR、CR<br /><br /> 似ています、**受容 ACK コード**静的 MLLP 送信ポートのプロパティです。|  
|メッセージ (MLLP です。キャリッジ リターン) ="0 d"です。|ASCII 文字|  
|メッセージ (MLLP.endBlockDelimiter) ="1 c"です。|終了ブロックの ASCII 文字|  
|メッセージ (MLLP.startBlockDelimiter) ="0b"です。|開始ブロック文字の ASCII|  
|メッセージ (MLLP.timeout) =「60000」です。|BTAHL7 サーバーがタイムアウトに非アクティブなどの送信ソケットの後にピリオド (0 はタイムアウトなし)|  
|SendPortName(Microsoft.XLANGs.BaseTypes.Address) =「127.0.0.1:11000」です。|メッセージのルーティングのアドレスとポート|  
|SendPortName(Microsoft.XLANGs.BaseTypes.TransportType) ="MLLP"です。|アダプター (MLLP) の種類|  
  
## <a name="additional"></a>追加情報  
  
-   HL7 のオーケストレーションでマルチパート メッセージを作成する、ときにメッセージ部分で作成この順序に従うとします。  
  
    1.  MSH セグメント  
  
    2.  BodySegments  
  
    3.  ZSegments  
  
     異なる順序でメッセージ部分を指定する場合は、次のエラーが発生します。  
  
     WrongBodyPartException  
  
-   動的ルーティングをサポートするために、オーケストレーションでは、アダプターのルートのプロパティを指定できます。  
  
## <a name="see-also"></a>参照  
 [構成パラメーターを送信および受信アダプター](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md)   
 [MLLP の受信アダプターの処理](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md)   
 [MLLP 送信アダプターの処理](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md)   
 [MLLP でエンコードされたメッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)