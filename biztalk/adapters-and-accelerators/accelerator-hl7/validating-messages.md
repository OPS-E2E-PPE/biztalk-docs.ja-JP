---
title: メッセージの検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, acknowledgements
- messages, acknowledgements
- acknowledgements, validating
- validating, messages
- acknowledgements, messages
- messages, validating
ms.assetid: 7dba0f40-5e19-4598-82cb-22c71e9536c6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fde2a092499f3e5c4c90d16af4043b532131de47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286337"
---
# <a name="validating-messages"></a>メッセージの検証
Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) エンコードされた ACK メッセージの受信メッセージの受信確認 (ACK) をアプリケーションから送信または取引先、HL7 への変換が必要な HL7 XML メッセージの形式でサポートしています。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 通常、関連する受信 (取引先パートナー形式) ドキュメントの仕様に対する受信メッセージを確認した後は、受信確認を生成します。 すべてのセグメントの検証に合格すると[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]アプリケーションへの同意を示す受信確認を返します。 それ以外の場合、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エラーまたは障害/拒否を示す確認メッセージが生成されます。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ACK の送信が HL7 標準に対する構文と概略のエラーを報告します。 検証が失敗した場合、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ドキュメントを保留中のメッセージ キューに配置し、拒否の詳細を示す確認メッセージを返します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パーサーは、データ型、構文、およびスキーマの検証チェックを含む検証を実行します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 受信場所の詳細と共に解析中に発生したエラーについて概略を記録します。  
  
 時間を構成、作成する必要がある、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ACK に対応するために必要なアーティファクト [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パーサーが HL7 正規 ACK XML インスタンスを作成します。 BizTalk では、これを適切な BizTalk マップで必要なバージョン形式に変換し、変換先の形式を検証します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]シリアライザーは、HL7 でエンコードされたインスタンスにメッセージを変換します。  
  
> [!NOTE]
>  受信メッセージの区切り記号の間に競合があるしで指定された場合、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成し、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ACK メッセージを受信メッセージの同じ区切り記号を使用し、構成を上書きを生成します。設定。  
  
## <a name="see-also"></a>参照  
 [作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)   
 [ACK メッセージ モード](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)