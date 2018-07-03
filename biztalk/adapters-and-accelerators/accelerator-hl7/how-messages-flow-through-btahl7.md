---
title: BTAHL7 内のメッセージのフロー方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, message processing
- messages, message flow
- BTAHL7, message flow
ms.assetid: dd4599af-500d-4e52-85b2-8b6a28fd3f0a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6bddae0d685d63772b5fd76f70ba19e0628cab5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000107"
---
# <a name="how-messages-flow-through-btahl7"></a>Btahl7 のメッセージのフロー
Microsoft BizTalk Accelerator for HL7 にインストールするときに ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を追加する MicrosoftBizTalk のサーバー上に[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]コンポーネントを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アーキテクチャ。 次の図は、結合されたシステムのアーキテクチャの概要を提供する[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/bcd-hl7-sys-archc.gif "bcd_hl7_sys_archc")  
  
## <a name="message-processing-flow"></a>メッセージの処理フロー  
 基幹業務アプリケーションがメッセージを送信すると、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]システムでは、次のようにします。  
  
1. 場合、メッセージは、HL7 メッセージ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]アダプター (通常は MLLP アダプター) を受信します。 XML メッセージである場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]アダプター (通常は HTTP アダプター) を受信します。  
  
   > [!NOTE]
   >  すべてのアダプター経由で 2.X と 2.xml の両方の XML メッセージを転送できます。ただし、V2 は、通常、トランスポートはします。MLLP アダプターとする X メッセージは、HTTP アダプターを介して 2. XML メッセージをトランスポートは、通常は。  
  
2. メッセージは、逆アセンブラー、および検証による解析のため、受信パイプラインを介してルーティングされます。  
  
   1. 受信メッセージが HL7 メッセージで、フラット ファイル逆アセンブラー (逆アセンブラー) により XML にアセンブルします。 受信メッセージが XML メッセージの場合、XML 逆アセンブラーが逆アセンブルします。  
  
   2. 受信メッセージがバッチ メッセージの場合は、個別のメッセージに、逆アセンブラーが逆アセンブルします。 (詳細については、次を参照してください[バッチ メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md)と[メッセージのバッチ処理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)。)。  
  
   3. 逆アセンブラーは、メッセージを検証します。  
  
   4. 双方向を使用する場合 MLLP 受信アダプター、逆アセンブラーは、メッセージを検証した場合と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]を元のメッセージを受信した同じアダプターでメッセージの元の送信者に受信確認 (ACK) を送信します。 ない場合は、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]否定受信確認応答 (NAK) を送信します。 (この手順を実行する方法、ACK の構成に依存します。 詳細については、次を参照してください[ACK メッセージ モード](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)。)。  
  
   5. 双方向を使わない場合 MLLP 受信アダプターが、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ACK または Ack または NAK (NAKs) を生成し、により、メッセージ ボックス データベースにします。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] (MLLP) だけでなく他のアダプターのいずれかを使用できる送信ポートの構成に基づいて適切なパーティにルーティングします。  
  
      プロセスのより完全な一覧は、XML 逆アセンブラーとフラット ファイルの実行を参照してください。 [BizTalk Accelerator for HL7 コンポーネント](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)します。  
  
3. メッセージは、アダプターと受信パイプラインを通過したら[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージ ボックス データベースにメッセージを渡します。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 次に、メッセージの送信先を決定します。 メッセージがオーケストレーションの一部である場合は、オーケストレーション エンジンにメッセージを送信します。  
  
4. オーケストレーション エンジンは、メッセージを処理します。  
  
   1. マップは、メッセージに影響する場合、マップは、その規則に従ってメッセージを変換します。  
  
   2. ビジネス ルールを設定している場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]外のパイプライン、オーケストレーション エンジンで可能性のあるビジネス ルール エンジン (BRE) を呼び出します。  
  
   3. オーケストレーション エンジンは、メッセージをメッセージ ボックス データベースに送信し、オーケストレーションの処理が続行されます。  
  
5. サブスクリプションの場合、に基づいて[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージの送信ポートにルーティングされます。  
  
6. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] (該当する) 場合、次を処理するため、送信パイプラインでメッセージをルーティングします。 アセンブリおよび検証します。  
  
   1. メッセージでは、HL7 場合 2.X メッセージ、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] XML からフラット ファイル アセンブラー (ASM) が HL7 にメッセージをアセンブルします。 受信メッセージが XML メッセージの場合、XML 逆アセンブラーによってアセンブルします。  
  
   2. メッセージは、バッチ メッセージの一部になる場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチ メッセージに各メッセージをアセンブルします。 (詳細については、次を参照してください[バッチ メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md)と[メッセージのバッチ処理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)。)。  
  
   3. ASM (送信パーティの構成設定を使用して有効になっている) 場合、メッセージを検証します。  
  
      プロセスのより完全な一覧は、フラット ファイルと XML アセンブラーで実行を参照してください[BizTalk Accelerator for HL7 コンポーネント](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)します。  
  
7. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] アダプターでメッセージを送信します。  
  
   > [!NOTE]
   >  アダプターの数を 2.X メッセージや 2. XML メッセージを転送することができます。ただし、ほとんどのシステムは、2.X MLLP アダプターでは、メッセージと HTTP アダプターを介して 2. XML メッセージを転送します。  
  
## <a name="see-also"></a>参照  
 [BTAHL7 によるメッセージのルーティング方法](../../adapters-and-accelerators/accelerator-hl7/how-btahl7-routes-messages.md)