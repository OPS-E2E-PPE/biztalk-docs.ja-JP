---
title: MLLP アダプターの既知の問題 |Microsoft ドキュメント
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
ms.openlocfilehash: 5cbae1bf4bf04e2ecf4e643ad5107b9e0fd70f70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206058"
---
# <a name="mllp-adapter-known-issues"></a>MLLP アダプターの既知の問題
このセクションには、最小限の下位層プロトコル (MLLP) アダプターのエラーを回避するために役立つ有用な情報が含まれています。  
  
## <a name="two-way-mllp-adapter-might-not-detect-a-problem-with-an-ack"></a>双方向の MLLP アダプターは、ACK に問題を検出できません可能性もあります。  
 ときに[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]) 確認 (ACK) の受信双方向の MLLP アダプターのアダプターがその有効性を決定する ACK の軽量な検証を実行します。 見つかった場合は有効である、MSA1 フィールドを抽出すると、およびその値に応じて、アダプター再試行、中断、または、ACK が応答していた元のメッセージを削除します。 ただし、アダプターによって実行される検証は完全な検証ではないため、可能であれば、アダプターでは、確認に問題は検出されません。 たとえば、アダプターには、ACK が有効であり、パイプラインは、ACK が整形式でできなかったことを確認および ACK メッセージが中断され、元のメッセージを削除でしたを決定します。  
  
## <a name="mllp-performance-counters-do-not-count-acks"></a>パフォーマンス カウンターの MLLP Ack はカウントされません。  
 パフォーマンスの 1 つのメジャーは、MLLP パフォーマンス カウンターによって示される、MLLP アダプターによって処理されるメッセージの数です。 この数は、受信または送信されたメッセージの数を計測します。 ただし、カウントは Ack を受信または送信の数を測定していません。  
  
## <a name="mllp-adapter-connection-names-are-not-guaranteed-to-be-unique"></a>MLLP アダプターの接続名が一意である保証はありません。  
 [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]MLLP アダプターのプロパティ ページに入力された接続名の一意性は保証されません。 この必須フィールドに名前が入力わかりやすい名前と関連する接続を確認します。 基幹業務アプリケーションを表す接続名を使用するは、接続の動作を把握しようとしているときに役立ちます。 たとえば、PerfMon カウンターは、接続名を使用します。  
  
> [!NOTE]
>  一意性を確保は BTAHL7 受信場所または送信ポートの名前。  
  
## <a name="two-way-mllp-adapters-do-not-send-commit-acks-for-all-messages-in-a-batch"></a>双方向の MLLP アダプターはバッチ内のすべてのメッセージのコミットの確認を送信しません。  
 コミットの確認の生成にバッチで各メッセージを構成すると、システムにバッチを送信する双方向の MLLP の受信アダプター、アダプターはバッチの最初のメッセージに対応するコミット ACK のみ送信します。  
  
> [!NOTE]
>  バッチをトランスポートには、一方向の MLLP アダプターを使用することをお勧めします。  
  
## <a name="nak-generated-by-two-way-mllp-adapter"></a>双方向の MLLP アダプターによって生成された NAK  
 双方向の MLLP アダプターは、すべてのメッセージを中断、ときに MLLP アダプターは NAK (否定受信確認) を生成し、メッセージ ボックス データベースに格納します。 予期しない動作があります。 メッセージ ボックス データベースから、NAK を削除するか、別のメッセージにマップすることがあります。  
  
## <a name="two-way-mllp-adapter-only-supports-the-2x-message-format"></a>双方向の MLLP アダプターのみ 2.X メッセージ形式をサポートしています  
 双方向の MLLP アダプターは、現在 2.X メッセージ形式のみをサポートします。  
  
## <a name="two-way-mllp-adapter-does-not-support-static-acknowledgments"></a>双方向の MLLP アダプターが静的な受信確認をサポートしていません  
 双方向の送信アダプタが静的な受信確認の処理をサポートしていません。  
  
## <a name="see-also"></a>参照  
 [既知の問題](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)