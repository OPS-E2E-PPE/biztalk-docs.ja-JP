---
title: MLLP アダプターの既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MLLP adapters, known issues
- known issues, MLLP adapters
ms.assetid: 66af8fcc-981a-4a77-80b7-84824bfae608
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb90c62baebb8fc73b939c0a3ea20eb85e9b0e28
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970835"
---
# <a name="mllp-adapter-known-issues"></a>MLLP アダプターの既知の問題
このセクションには、最小限の下位レイヤー プロトコル (MLLP) アダプターのエラーを回避するために役立つ有用な情報が含まれています。  
  
## <a name="two-way-mllp-adapter-might-not-detect-a-problem-with-an-ack"></a>双方向の MLLP アダプターでは、ACK に問題が検出されない可能性も  
 ときに Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]) 受信確認 (ACK) の受信アダプターを双方向の MLLP アダプター上には、有効性を確認で軽量の検証を実行します。 有効にすることが見つかると MSA1 フィールドが抽出され、その値に応じて、アダプター再試行、中断、または、ACK が応答していた元のメッセージを削除します。 ただし、アダプターによって実行される検証は完全な検証ではないためには、アダプターが ACK に問題を検出できません。 たとえば、アダプターでは、ACK が有効ですをパイプラインは、ACK が整形式でされなかったことを確認し、確認メッセージを中断する一方、元のメッセージを削除することを決定でした。  
  
## <a name="mllp-performance-counters-do-not-count-acks"></a>MLLP パフォーマンス カウンターには Ack はカウントされません。  
 パフォーマンスの 1 つのメジャーは、MLLP パフォーマンス カウンターが示すとおり、MLLP アダプターによって処理されるメッセージの数です。 この数は、受信または送信されるメッセージの数を測定します。 ただし、カウントの Ack を受信または送信の数を計測しません。  
  
## <a name="mllp-adapter-connection-names-are-not-guaranteed-to-be-unique"></a>MLLP アダプターの接続名は一意であることは保証されません。  
 [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] MLLP アダプターのプロパティ ページに入力された接続名の一意性は保証されません。 この必須のフィールド名を入力したそのわかりやすい名前と関連する接続を確認します。 基幹業務アプリケーションを表す接続名を使用するは、接続の動作を理解しようとするときに役立ちます。 たとえば、PerfMon カウンターは、接続名を使用します。  
  
> [!NOTE]
>  一意性を確保は BTAHL7 受信場所または送信ポートの名前。  
  
## <a name="two-way-mllp-adapters-do-not-send-commit-acks-for-all-messages-in-a-batch"></a>双方向の MLLP アダプターはすべてのメッセージ バッチのコミットの確認を送信しません。  
 コミットの確認を生成するバッチ内の各メッセージを構成すると、システムにバッチを送信する双方向の MLLP 受信アダプター、アダプターはバッチの最初のメッセージに対応するコミットの確認のみを送信します。  
  
> [!NOTE]
>  バッチをトランスポートする一方向の MLLP アダプターを使用することをお勧めします。  
  
## <a name="nak-generated-by-two-way-mllp-adapter"></a>双方向の MLLP アダプターによって生成された NAK  
 双方向の MLLP アダプターでは、すべてのメッセージを中断、MLLP アダプターは NAK (否定受信確認応答) が生成され、メッセージ ボックス データベースに配置します。 これにより、予期しない動作可能性があります。 メッセージ ボックス データベースから、NAK を削除するか、別のメッセージにマップすることがあります。  
  
## <a name="two-way-mllp-adapter-only-supports-the-2x-message-format"></a>双方向の MLLP アダプターは、2.X のメッセージ形式のみサポートしています。  
 双方向の MLLP アダプターでは、2.X のメッセージ形式のみがサポートされています。  
  
## <a name="two-way-mllp-adapter-does-not-support-static-acknowledgments"></a>双方向の MLLP アダプターが静的受信確認をサポートしていません  
 双方向の送信アダプタが静的受信確認の処理をサポートしていません。  
  
## <a name="see-also"></a>参照  
 [既知の問題](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)