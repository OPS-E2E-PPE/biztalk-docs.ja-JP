---
title: HL7 2.3 フォルダーとイベント |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HL7, default sub-folders
- events, 2.X versions
- HL7, events
ms.assetid: 555a8620-a714-4102-80ba-1424d60387bf
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a396fca582defb8601bdda23280f92d0acbd90be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205210"
---
# <a name="hl7-23-folders-and-events"></a>HL7 2.3 フォルダーとイベント
次の表は、HL7 でエンコードされたメッセージ HL7 バージョン 2.3 フォルダー内のセットアップ ウィザードによって作成されるサブフォルダーを一覧表示します。 これらのサブフォルダーがによって使用されるスキーマを含む[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を検証、解析、およびこのテーブルの [イベント] 列に示されているイベントをシリアル化します。 サブフォルダー名では、これらのスキーマをサポートするイベントの種類について説明します。  
  
|サブフォルダー|イベント|  
|---------------|------------|  
|患者の管理|A01 A51|  
|監視レポート|C01 C12、P07 P09、R01-R06、W01 W02|  
|患者の紹介|I01 I15|  
|Master ファイル|M01 M11|  
|注文エントリ|O01 O02、Q06、RAR、RDR、RER、RGR、権限が必要です、V01 V04|  
|財務管理|P01 P06|  
|治療|PC1 PCH、PCJ PCL|  
|Query|CNQ、Q01 Q03、Q05|  
|スケジューリング|S01 S26|  
|医療記録および情報の管理|T01 T12 が同時|  
  
## <a name="see-also"></a>参照  
 [HL7 2.X サブフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md)   
 [HL7 2.1 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md)   
 [HL7 2.2 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md)   
 [HL7 2.3.1 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md)   
 [HL7 2.4 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md)   
 [HL7 2.5 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)