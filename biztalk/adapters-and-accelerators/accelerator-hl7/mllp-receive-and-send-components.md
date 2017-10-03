---
title: "MLLP の受信し、送信コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send components
- Minimal Lower Layer Protocol (MLLP)
- MLLP adapters
- MLLP adapters, wrappers
- wrappers [MLLP adapters]
- receive components
ms.assetid: 2f1c4099-8f52-437a-bdc1-efe707fbf347
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab82aa317b205d62b8bd05aff513e80d406b658b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="mllp-receive-and-send-components"></a>MLLP の受信し、送信コンポーネント
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) すべてサポート[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ネイティブ アダプターの種類、ファイル、HTTP、SQL では、FTP などです。 HL7 でエンコードされたメッセージの受信と送信、ただし、通常使用する MLLP アダプター。 このアダプターは、最小下位層プロトコル (MLLP) を使用する TCP/IP ソケット アダプターです。 このプロトコルは、双方向メッセージのサポートおよびエンド ツー エンドの医療アプリケーション統合を提供します。  
  
 MLLP を構成することができます、アダプターを双方向または一方向のアダプターのいずれかとしてアダプターを受信します。 双方向の送信請求-応答送信アダプター、一方向の送信アダプターが同じソケット接続で受信確認 (Ack) を受信するように構成または一方向の送信アダプターでメッセージが返されないよう、MLLP 送信アダプターを構成できます。 送信請求-応答が MLLP アダプターを送信、双方向を使用する場合は、Ack または応答メッセージのいずれかを返す受信ポートを構成することができます。 MLLP の例では、送信し、受信アダプターを参照してください[Interrogative チュートリアル](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)です。  
  
 メッセージの[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]受信または MLLP アダプターの送信には、次のラッパーが必要とします。  
  
-   \<SB > ブロックの開始文字  
  
-   \<EB > ブロックの終了文字  
  
-   \<CR > 復帰返すバイト (省略可能)  
  
 MLLP アダプターは、エラーのない処理を行う\<SB > または\<EB > ラッパー、接続の切断、またはタイムアウトです。 MLLP アダプターでは、接続の数に制限を構成できます。 MLLP アダプターでは、多種多様な受信確認を使用できます。  
  
## <a name="see-also"></a>参照  
 [MLLP でエンコードされたメッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [BizTalk Accelerator for HL7 コンポーネント](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)