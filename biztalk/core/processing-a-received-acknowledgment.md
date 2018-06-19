---
title: 受信した確認の処理 |Microsoft ドキュメント
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
ms.openlocfilehash: 1205c7cec5a013fef89eac49e6b953cf5f752626
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971184"
---
# <a name="processing-a-received-acknowledgment"></a>受信した確認の処理
アグリーメントの中で関連するプロパティが指定されている場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、技術確認を必要とします。 これは、x12 の場合、 **TA1 が必要**プロパティに、**受信確認**一方向アグリーメントのページ、**アグリーメントのプロパティ** ダイアログ ボックスまたはフォールバック アグリーメントからプロパティ。 これは、edifact の場合、**メッセージの受信 (CONTRL が必要です)** プロパティに、**受信確認**一方向アグリーメントのページ、**アグリーメントのプロパティ** ダイアログボックスか、フォールバック アグリーメントのプロパティです。 受信アグリーメントでは、受信したメッセージを処理するときに、メッセージ内の ISA14 値または UNB9 値の結果として技術確認を生成します。  
  
 アグリーメントの中で関連するプロパティが指定されている場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、X12 エンコードまたは EDIFACT エンコードの機能確認を必要とします。 X12 の場合、このプロパティは、 **997 が必要**で、**受信確認**一方向アグリーメントのページ、**アグリーメントのプロパティ** ダイアログ ボックスまたはフォールバック アグリーメントからプロパティ。 Edifact の場合、このプロパティは、**確認 (CONTRL) が必要です**プロパティに、**受信確認**一方向アグリーメントのページ、**アグリーメントのプロパティ**ダイアログ ボックスか、フォールバック アグリーメントのプロパティです。 受信アグリーメントでは、受信したメッセージを処理するときに、メッセージ内の ISA14 値または UNB9 値の結果として技術確認を生成します。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、EDI メッセージに対する確認を受信すると、確認管理スキーマを使用して確認を検証します。 これらのスキーマは x12 _\<バージョン番号\>>_997.xsd または X12\_\<バージョン番号\>x12、EFACT >_ta1.xsd\_\<バージョン番号\>>_contrl.xsdEDIFACT、および HIPAA 5010 では X12_00501_997.xsd です。  
  
 受信した確認を処理するときに受信パイプラインでは、この確認を、送信された EDI インターチェンジと関連付けます。 次に、確認をメッセージ ボックスにドロップします。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、これ以上は確認を処理しません。 確認を処理するためのメカニズムを設定しない限り、確認は中断されます。 確認を処理するには、確認をサブスクライブするための送信ポートを設定し、この送信ポートを、確認が定期的に削除されるフォルダーにドロップします。  
  
## <a name="see-also"></a>参照  
 [EDI 受信確認構造](../core/edi-acknowledgment-structure.md)   
 [EDI 受信確認の送信](../core/sending-an-edi-acknowledgment.md)