---
title: "HL7 2.4 フォルダーとイベント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HL7, default sub-folders
- events, 2.X versions
- HL7, events
ms.assetid: c8855311-40c7-4338-ba07-5112c253fafd
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9196b0b69eb3730de8ad3ef383a1cde8564e5002
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="hl7-24-folders-and-events"></a>HL7 2.4 フォルダーとイベント
次の表は、HL7 でエンコードされたメッセージ HL7 バージョン 2.4 フォルダー内のセットアップ ウィザードによって作成されるサブフォルダーを一覧表示します。 これらのサブフォルダーがによって使用されるスキーマを含む[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を検証、解析、およびこのテーブルの [イベント] 列に示されているイベントをシリアル化します。 サブフォルダー名では、これらのスキーマをサポートするイベントの種類について説明します。  
  
|サブフォルダー|イベント|  
|---------------|------------|  
|患者の管理|A01 A62、K21 K24、Q21 Q24|  
|人事管理|B01 B06、K25、Q25|  
|監視レポート|C01 C12、P07 P09、R01 R02、R04、R21、W01 W02|  
|患者の紹介|I01 I15|  
|Query|J01 J02、K11、K13、K15、Q01 Q05、Q07 Q09、Q11、Q13、Q15 Q17、R07 R09 Z75 Z99|  
|Master ファイル|M01 M12 の MFA|  
|注文エントリ|O01 O22 Q06、Q26 Q30、RAR、RDR、RER、RGR、権限が必要です、V01 V04 Z73 Z74|  
|アプリケーション管理|N01 N02|  
|財務管理|P01 P06、P10|  
|治療|PC1 PCH、PCJ PCL|  
|スケジューリング|S01 S26|  
|医療レコード/Information Management|T01 T12 が同時|  
|医療研究所のオートメーション|U01 U13|  
  
## <a name="see-also"></a>参照  
 [HL7 2.X サブフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md)   
 [HL7 2.1 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md)   
 [HL7 2.2 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md)   
 [HL7 2.3 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md)   
 [HL7 2.3.1 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md)   
 [HL7 2.5 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)