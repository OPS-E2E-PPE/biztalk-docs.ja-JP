---
title: HL7 2.4 XML のフォルダーとイベント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- events, HL7 2.XML versions
- HL7, default sub-folders
- HL7, events
ms.assetid: bc6c5d75-66c7-4269-bfb9-59cab5999a73
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2122e1f3f4e6f583c3ce796695d87d1b0c46170
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268969"
---
# <a name="hl7-24-xml-folders-and-events"></a>HL7 2.4 XML のフォルダーとイベント
次の表は、XML エンコード メッセージの HL7 バージョン 2.4 のフォルダー内のセットアップ ウィザードによって作成されるサブフォルダーを一覧表示します。 これらのサブフォルダーは、Microsoft BizTalk Accelerator for HL7 のために使用するスキーマを含めることが ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を検証する、解析し、このテーブルの [イベント] 列に表示されるイベントをシリアル化します。 サブフォルダー名には、これらのスキーマをサポートするイベントの種類について説明します。  
  
|サブ フォルダー|イベント|  
|----------------|------------|  
|患者の管理|A01 A62、K21、K22、K23、K24、Q21 Q24|  
|注文エントリ|O01 O22、Q06、Q26 Q30、RAR、RDR、RER、RGR、権限が必要です、V01 V04、Z73、Z74|  
|Query|J01、J02、K11、K13、K15、Q01 Q05、Q07 Q09、Q11、Q13、Q15 Q17、R07 R09、Z75 Z99|  
|財務管理|P01 ~ P06、P10|  
|監視レポート|C01 C12、P07、P08、P09、R01、R02、R04、R21、W01、W02|  
|Master ファイル|M01 M12 の MFA|  
|医療記録の管理|T01 T12|  
|スケジューリング|S01 S26|  
|患者の紹介|I01 I15|  
|患者のケア|PC1 PCH PCJ、問題、PCL|  
|臨床試験の自動化|U01 U13|  
|アプリケーションの管理|N01,N02|  
|人事管理|B01 B06 K25、Q25|  
  
## <a name="see-also"></a>参照  
 [HL7 2. XML スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)