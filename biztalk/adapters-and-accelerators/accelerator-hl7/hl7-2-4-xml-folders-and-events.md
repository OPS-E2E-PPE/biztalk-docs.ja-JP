---
title: "HL7 2.4 XML フォルダーとイベント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events, HL7 2.XML versions
- HL7, default sub-folders
- HL7, events
ms.assetid: bc6c5d75-66c7-4269-bfb9-59cab5999a73
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10c9445a1d5c7978b526fd0347dc6defa3214640
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="hl7-24-xml-folders-and-events"></a>HL7 2.4 XML フォルダーとイベント
次の表では、HL7 バージョン 2.4 フォルダー内の XML でエンコードされたメッセージのセットアップ ウィザードによって作成されるサブフォルダーが一覧表示します。 これらのサブフォルダーがによって使用されるスキーマを含む[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を検証、解析、およびこのテーブルの [イベント] 列に示されているイベントをシリアル化します。 サブフォルダー名では、これらのスキーマをサポートするイベントの種類について説明します。  
  
|サブ フォルダー|イベント|  
|----------------|------------|  
|患者の管理|A01 A62 K21、K22、K23、K24 Q21 Q24|  
|注文エントリ|O01 O22 Q06、Q26 Q30、RAR、RDR、RER、RGR、権限が必要です、V01 V04、Z73 Z74|  
|Query|J01 J02、K11、K13、K15、Q01 Q05、Q07 Q09、Q11、Q13、Q15 Q17、R07 R09 Z75 Z99|  
|財務管理|P01 ~ P06、P10|  
|監視レポート|C01 C12 P07、P08、P09、R01、R02、R04、R21、W01 W02|  
|Master ファイル|M01 M12 の MFA|  
|医療レコード/Information Management|T01 T12 が同時|  
|スケジューリング|S01 S26|  
|患者の紹介|I01 I15|  
|治療|PC1 PCH、PCJ、問題、PCL|  
|医療研究所のオートメーション|U01 U13|  
|アプリケーション管理|N01、N02|  
|人事管理|B01 B06、K25、Q25|  
  
## <a name="see-also"></a>参照  
 [HL7 2. XML スキーマを使用します。](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)