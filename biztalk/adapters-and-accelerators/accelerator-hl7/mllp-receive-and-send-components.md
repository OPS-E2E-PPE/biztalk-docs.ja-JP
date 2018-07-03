---
title: MLLP 受信および送信コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send components
- Minimal Lower Layer Protocol (MLLP)
- MLLP adapters
- MLLP adapters, wrappers
- wrappers [MLLP adapters]
- receive components
ms.assetid: 2f1c4099-8f52-437a-bdc1-efe707fbf347
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0eebc51d23c66fb9dd7047f29982fbcc05a8215f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971803"
---
# <a name="mllp-receive-and-send-components"></a>MLLP 受信および送信コンポーネント
Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) すべての Microsoft のサポート[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ファイル、HTTP、SQL では、FTP などのネイティブ アダプターの種類。 HL7 でエンコードされたメッセージの受信と送信、ただし、通常使用する MLLP アダプター。 このアダプターは、最小限下位レイヤー プロトコル (MLLP) を使用する TCP/IP ソケット アダプターです。 このプロトコルは、双方向のメッセージのサポートとエンド ツー エンドの医療のアプリケーション統合を提供します。  
  
 MLLP を構成する受信アダプターのアダプターを双方向または一方向のアダプターのいずれかとして。 MLLP 送信アダプターは、双方向の送信請求-応答送信アダプター、一方向の送信アダプターが、同じソケット接続で受信確認 (Ack) を受信するように構成または一方向の送信メッセージを返さないアダプターとして構成できます。 双方向を使用する場合は、送信請求-応答送信の MLLP アダプター、Ack または応答メッセージのいずれかを返す受信ポートを構成することができます。 MLLP の例では、送信および受信アダプターを参照してください。 [Interrogative チュートリアル](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)します。  
  
 メッセージの[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]受信または MLLP アダプターの送信には、次のラッパーが必要とします。  
  
- \<SB\>ブロックの開始文字  
  
- \<EB\>ブロックの終了文字  
  
- \<CR\>復帰返すバイト (省略可能)  
  
  MLLP アダプターがエラーで不足している処理を行う\<SB\>または\<EB\>ラッパー、接続が切断、またはタイムアウトします。 MLLP アダプターでは、接続の数に制限を構成できます。 MLLP アダプターでは、多種多様な受信確認を使用できます。  
  
## <a name="see-also"></a>参照  
 [MLLP でエンコードされたメッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [BizTalk Accelerator for HL7 コンポーネント](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)