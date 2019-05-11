---
title: HL7 2.3.1 XML のフォルダーとイベント |Microsoft Docs
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
ms.assetid: b3598cc5-46d6-489a-84a7-266ee3c40276
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29b98dbc5b0b234d56984fc606d05dffcab7e6ce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271167"
---
# <a name="hl7-231-xml-folders-and-events"></a>HL7 2.3.1 XML のフォルダーとイベント
次の表は、XML エンコード メッセージの HL7 version 2.3.1 のフォルダー内のセットアップ ウィザードによって作成されるサブフォルダーを一覧表示します。 これらのサブフォルダーは、Microsoft BizTalk Accelerator for HL7 のために使用するスキーマを含めることが ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を検証する、解析し、このテーブルの [イベント] 列に表示されるイベントをシリアル化します。 サブフォルダー名には、これらのスキーマをサポートするイベントの種類について説明します。  
  
|サブフォルダー|イベント|  
|---------------|------------|  
|患者の管理|A01 A51|  
|注文エントリ|O01、O02、Q06、R0R、RAR、RDR、RER、RGR、V01 V04|  
|Query|CNQ、Q01 Q03、Q05、Q07 Q09、R07、R08、R09|  
|財務管理|P01 P06|  
|監視レポート|C01 C12、P06、P07、P09、R01 R06、W01、W02|  
|Master ファイル|M01 M11、MFA|  
|医療記録の管理|T01 T12|  
|[スケジュール]|S01 S26|  
|患者の紹介|I01 I15|  
|患者のケア|PC1 PCH PCJ、問題、PCL|  
|ネットワークの管理|N01,N02|  
  
## <a name="see-also"></a>参照  
 [HL7 2. XML スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)