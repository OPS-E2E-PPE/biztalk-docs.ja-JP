---
title: 開始側パブリック プロセス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public processes, initiator
- CIDX, 0A1 messages
- messages, 0A1 messages
- messages, message flow
- messages, public processes
- 0A1 messages
- public processes, message flow
ms.assetid: 371d0792-d346-405b-a8f4-2dfa64dd1566
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50506911108d21247f5da9cadc76cd505417a8d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283499"
---
# <a name="initiator-public-process"></a>開始側パブリック プロセス
このプロセスは、RosettaNet Implementation Framework (RNIF) が作成、RNIF ビジネス メッセージを送信することで、開始側システムでメッセージングを開始します。  
  
## <a name="message-flow-in-the-initiator-public-process"></a>開始側パブリック プロセスにおけるメッセージ フロー  
 開始側パブリック プロセスを経由するメッセージ フローは次のとおりです。  
  
1. 開始側パブリック プロセスは、サービス コンテンツ ポートを介してプライベート プロセスからの service content と添付ファイルを受け取ります。  
  
2. パブリック プロセスは、プライベートのプロセスへの応答を送信し、さらなる処理は行われません。  
  
3. マイクロソフトに通知を受信するパブリック プロセス場合、[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]メッセージ正常に送信して、パブリック プロセスとその状態、開始側プライベート プロセスに戻るを終了します。  
  
4. 場合は、パブリック プロセスは、通知を受信する[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]プロセス メッセージを正常に送信するには、(応答側のアクションを待つ) 待機状態になります。  
  
5. 次の操作には、待機状態を終了できます。  
  
   1.  パブリック プロセスは、応答側から受信確認シグナルを受信します。  
  
        場合は、シグナルの否認 (で設定されているプロセス構成設定)、必要なプロセス ダイジェスト、シグナルのダイジェストを関連付けて元のアクション メッセージのダイジェストを読み取って、シグナルを保存し。  
  
        パブリック プロセスは、ヘッダーと、シグナルの service content をプライベート プロセスに送信します。  
  
   2.  パブリック プロセスは、応答側からダブル アクション応答メッセージを受信します。  
  
        プロセスでは、service content とヘッダーを応答メッセージから抽出され、プライベート プロセスに送信されます。  
  
        アクティビティが同期の場合、プロセス (RNIF 2.01 の場合) の preamble、service header、および配信のヘッダーを使用して、service content メッセージ部をラップすることによって、RNIF シグナル メッセージを構築します。 Preamble とヘッダーの送信元と送信先のパーティとパーティ間の取引先のパートナー アグリーメントに格納されている PIP 変数に関する構成情報を使用して、プロセスを作成します。 次に、プロセスは応答側にシグナル メッセージを送信します。  
  
        アクティビティが非同期の場合、プロセスを終了します。  
  
   3.  パブリック プロセスは、応答側からエラー通知 (NoF) メッセージを受け取ります。 パブリック プロセスは、開始側プライベート プロセスに対応するステータス メッセージを送信します。 プライベート プロセスは、エラーを処理し、両方のプロセスを終了します。  
  
   4.  パブリック プロセスでは、時間内、応答側から受信確認シグナルは (プロセス構成設定で設定した) として確認期間に受信しません。 そうである場合、次のいずれかが発生します。  
  
        (プロセス構成設定で設定) と再試行の回数が 0 になっておらず、アクティビティが非同期場合は、パブリック プロセスは、メッセージをもう一度送信します。  
  
        (プロセス構成設定で設定) と再試行の回数が 0 になっていないと、動作が同期、パブリック プロセスは 0A1 メッセージを開始します。  
  
       > [!NOTE]
       >  CIDX は、0A1 メッセージをサポートしていません。  
  
        パブリック プロセスが、エラー メッセージを投稿する再試行の回数が正常に送信ゼロに達すると、これが CIDX でない場合、パブリック プロセスは 0A1 メッセージを送信します。  
  
        このアクティビティは、同期が CIDX でない場合は、パブリック プロセスは 0A1 メッセージを開始します。  
  
   5.  アクション内に行われない、時間、実行期間に、これが CIDX でない場合は、パブリック プロセスは 0A1 メッセージを送信します。  
  
## <a name="see-also"></a>参照  
 [パブリック プロセス](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md)   
 [レスポンダー パブリック プロセス](../../adapters-and-accelerators/accelerator-rosettanet/responder-public-process.md)