---
title: "BTAHL7 内のメッセージのフロー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, message processing
- messages, message flow
- BTAHL7, message flow
ms.assetid: dd4599af-500d-4e52-85b2-8b6a28fd3f0a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33f06c896b58b2ba57c8c1bcee598d23f81b7700
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="how-messages-flow-through-btahl7"></a>BTAHL7 内のメッセージのフロー
インストールするときに[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) の上に[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]追加する BizTalk Server[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]コンポーネントを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アーキテクチャ。 次の図は、結合されたシステム、アーキテクチャの概要を説明[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]です。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/bcd-hl7-sys-archc.gif "bcd_hl7_sys_archc")  
  
## <a name="message-processing-flow"></a>メッセージの処理フロー  
 基幹業務アプリケーションがメッセージを送信すると、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]システムでは、次のようにします。  
  
1.  場合、メッセージは、HL7 メッセージ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]アダプター (通常は MLLP アダプター) を受信します。 XML メッセージである場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]アダプター (通常は HTTP アダプター) を受信します。  
  
    > [!NOTE]
    >  すべてのアダプター経由で 2.X と 2. の両方の XML メッセージを転送できます。ただし、V2 を通常トランスポートとします。MLLP アダプターでは、over X メッセージでは、HTTP アダプターを介して 2. XML メッセージをトランスポートが通常します。  
  
2.  メッセージは、逆アセンブラー、および検証によって解析するため、受信パイプラインを介してルーティングされます。  
  
    1.  HL7 メッセージを受信メッセージには、フラット ファイル逆アセンブラー (DASM) により XML に分解します。 受信メッセージが XML メッセージの場合は、XML 逆アセンブラーは、逆アセンブルします。  
  
    2.  受信メッセージがバッチ メッセージの場合は、個別のメッセージに逆アセンブラーが逆アセンブルします。 (詳細については、次を参照してください[バッチ メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md)と[メッセージのバッチ処理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)。)。  
  
    3.  逆アセンブラーは、メッセージを検証します。  
  
    4.  双方向を使用する場合 MLLP の受信アダプターが、逆アセンブラーが、メッセージを検証した場合と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]を元のメッセージを受信した同じアダプターでメッセージの元の送信者に確認 (ACK) を送信します。 ない場合は、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]否定受信確認応答 (NAK) を送信します。 (この手順を実行する方法によって異なります、ACK 構成。 詳細については、「 [ACK メッセージ モード](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)。)  
  
    5.  双方向を使わない場合 MLLP の受信アダプター、し、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ACK または Ack または NAK (NAKs) を生成し、MessageBox データベースに展開します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)](MLLP) だけでなく他のアダプターのいずれかを使用する送信ポートの構成に基づいて、適切なパーティにルーティングします。  
  
     プロセスのより完全な一覧は、XML 逆アセンブラーとフラット ファイルで実行されるを参照してください[BizTalk Accelerator for HL7 コンポーネント](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)です。  
  
3.  メッセージは、アダプターと受信パイプラインを通過した後[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]MessageBox データベースにメッセージを渡します。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]次に、メッセージを送信する場所を決定します。 メッセージがオーケストレーションの一部である場合は、オーケストレーション エンジンにメッセージを送信します。  
  
4.  オーケストレーション エンジンでは、メッセージを処理します。  
  
    1.  マップは、メッセージに影響する場合、マップは、規則に従ってメッセージを変換します。  
  
    2.  ビジネス ルールを設定した場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]パイプライン、オーケストレーション エンジンに可能性のある外部でビジネス ルール エンジン (BRE) を呼び出します。  
  
    3.  オーケストレーション エンジンは、メッセージをメッセージ ボックス データベースに送信し、オーケストレーションの処理が続行されます。  
  
5.  サブスクリプションの場合、に基づいて[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージの送信ポートにルーティングします。  
  
6.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)](該当する場合)、次を処理するため、送信パイプラインでメッセージをルーティングします。 アセンブリおよび検証します。  
  
    1.  メッセージは、HL7 なる場合 2.X メッセージ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]XML からフラット ファイル アセンブラー (ASM) で HL7 にメッセージをアセンブルします。 受信メッセージが XML メッセージの場合、XML 逆アセンブラーにアセンブルします。  
  
    2.  メッセージ バッチ メッセージの一部となる場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチ メッセージに各メッセージをアセンブルします。 (詳細については、次を参照してください[バッチ メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md)と[メッセージのバッチ処理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)。)。  
  
    3.  ASM では、(送信パーティの構成の設定で有効になっている) 場合にメッセージが検証されます。  
  
     プロセスのより完全な一覧は、XML アセンブラーとフラット ファイルで実行されるを参照してください[BizTalk Accelerator for HL7 コンポーネント](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)です。  
  
7.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]アダプターでメッセージを送信します。  
  
    > [!NOTE]
    >  アダプターの数を 2.X メッセージや 2. XML メッセージを転送することができます。ただし、ほとんどのシステムは、MLLP アダプターを経由 2.X メッセージと HTTP アダプターを介して 2. XML メッセージを転送します。  
  
## <a name="see-also"></a>参照  
 [BTAHL7 によるメッセージのルーティング方法](../../adapters-and-accelerators/accelerator-hl7/how-btahl7-routes-messages.md)