---
title: HL7 2.3 のフォルダーとイベント |Microsoft Docs
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
ms.openlocfilehash: 6f5df624fa1de08844fb1076adbc5e6d2ff08720
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992051"
---
# <a name="hl7-23-folders-and-events"></a>HL7 2.3 のフォルダーとイベント
次の表は、HL7 でエンコードされたメッセージの HL7 バージョン 2.3 のフォルダー内のセットアップ ウィザードによって作成されるサブフォルダーを一覧表示します。 これらのサブフォルダーは、Microsoft BizTalk Accelerator for HL7 のために使用するスキーマを含めることが ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を検証する、解析し、このテーブルの [イベント] 列に表示されるイベントをシリアル化します。 サブフォルダー名には、これらのスキーマをサポートするイベントの種類について説明します。  
  
|サブフォルダー|イベント|  
|---------------|------------|  
|患者の管理|A01 A51|  
|監視レポート|C01 C12 P07 P09、R01-R06、W01 W02|  
|患者の紹介|I01 I15|  
|Master ファイル|M01 M11|  
|注文エントリ|O01 O02、Q06、RAR、RDR、RER、RGR、権限が必要です、V01 V04|  
|財務管理|P01 P06|  
|患者のケア|PC1 PCH PCJ PCL|  
|Query|CNQ、Q01 Q03、Q05|  
|スケジューリング|S01 S26|  
|医療記録、および情報の管理|T01 T12|  
  
## <a name="see-also"></a>参照  
 [HL7 2.X のサブフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md)   
 [HL7 2.1 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md)   
 [HL7 2.2 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md)   
 [HL7 2.3.1 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md)   
 [HL7 2.4 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md)   
 [HL7 2.5 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)