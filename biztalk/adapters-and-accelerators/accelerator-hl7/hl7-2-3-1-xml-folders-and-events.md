---
title: HL7 2.3.1 XML フォルダーとイベント |Microsoft ドキュメント
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
ms.openlocfilehash: 79b25e0563f404d0f8b0600829398729a6c80e65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204322"
---
# <a name="hl7-231-xml-folders-and-events"></a>HL7 2.3.1 XML フォルダーとイベント
次の表では、HL7 version 2.3.1 フォルダー内の XML でエンコードされたメッセージのセットアップ ウィザードによって作成されるサブフォルダーが一覧表示します。 これらのサブフォルダーがによって使用されるスキーマを含む[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を検証、解析、およびこのテーブルの [イベント] 列に示されているイベントをシリアル化します。 サブフォルダー名では、これらのスキーマをサポートするイベントの種類について説明します。  
  
|サブフォルダー|イベント|  
|---------------|------------|  
|患者の管理|A01 A51|  
|注文エントリ|O01 O02、Q06、R0R、RAR、RDR、RER、RGR V01 V04|  
|Query|CNQ、Q01 Q03、Q05、Q07 Q09、R07、R08、R09|  
|財務管理|P01 P06|  
|監視レポート|C01 C12 P06、P07、P09、R01 R06、W01 W02|  
|Master ファイル|M01 M11 の MFA|  
|医療レコード/Information Management|T01 T12 が同時|  
|スケジュール|S01 S26|  
|患者の紹介|I01 I15|  
|治療|PC1 PCH、PCJ、問題、PCL|  
|ネットワークの管理|N01、N02|  
  
## <a name="see-also"></a>参照  
 [HL7 2. XML スキーマを使用します。](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)