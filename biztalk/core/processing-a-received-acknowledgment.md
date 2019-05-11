---
title: 受信確認の処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67f67a95-7368-40c2-a162-6ffc9de076fc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6facf54500f3ff28ddba25d03b8a1d96f9cf25d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396998"
---
# <a name="processing-a-received-acknowledgment"></a>受信した確認の処理
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 契約書に関連するプロパティが指定されている場合、技術確認を必要とします。 これは、x12 の場合、 **TA1 が必要**プロパティ、**受信確認**で一方向アグリーメントのページ、**アグリーメントのプロパティ** ダイアログ ボックスまたはフォールバック アグリーメントからプロパティ。 Edifact では、これは、**メッセージの受信 (CONTRL が必要です)** プロパティ、**受信確認**で一方向アグリーメントのページ、**アグリーメントのプロパティ**ダイアログボックスまたはフォールバック アグリーメントのプロパティ。 受信側アグリーメントは、受信したメッセージを処理するとき、メッセージで [isa14] または [unb9] の値の結果として技術確認が生成されます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] X12 または EDIFACT エンコード アグリーメントに関連するプロパティが指定されている場合のいずれかの機能確認が必要とします。 X12 の場合、このプロパティは、 **997 が必要**で、**受信確認**で一方向アグリーメントのページ、**アグリーメントのプロパティ** ダイアログ ボックスまたはフォールバック アグリーメントからプロパティ。 EDIFACT の場合、このプロパティは、**確認 (CONTRL) が必要です**プロパティ、**受信確認**で一方向アグリーメントのページ、**アグリーメントのプロパティ**ダイアログ ボックスまたはフォールバック アグリーメントのプロパティ。 受信側アグリーメントは、受信したメッセージを処理するとき、メッセージで [isa14] または [unb9] の値の結果として技術確認が生成されます。  
  
 ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信確認を受信 EDI メッセージを確認管理スキーマを使用して、受信確認を検証します。 これらのスキーマは x12 _\<バージョン番号\>*997. xsd または X12\\*\<バージョン番号\>*x12 の場合、EFACT TA1.xsd\\* \<バージョン番号\>>_contrl.xsd、EDIFACT、およびでは、HIPAA 5010 x12_00501_997.xsd です。  
  
 受信パイプラインに受信確認を処理するときは、送信された EDI インターチェンジの受信確認を関連付けます。 次に、パイプラインは、メッセージ ボックスに、受信確認を削除します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] さらに、受信確認を処理しません。 処理するためのメカニズムを設定していない場合、受信確認は中断されます。 受信確認を処理するには、それをサブスクライブし、受信確認を定期的に削除できる場所のフォルダーにドロップ 送信ポートを設定できます。  
  
## <a name="see-also"></a>参照  
 [EDI 受信確認構造](../core/edi-acknowledgment-structure.md)   
 [EDI 受信確認の送信](../core/sending-an-edi-acknowledgment.md)