---
title: FileAct アダプター状態の監視 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 15833004-4276-4975-a0e7-8fff3c82576b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c5b717a02631d47b864cc9180cba2fba673c5da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223042"
---
# <a name="fileact-adapter-status-monitoring"></a>FileAct アダプター状態の監視
ファイル転送およびそれらの状態間の遷移の状態は、次の図に示します。  
  
 ![FileAct アダプター ファイル転送状態](../../adapters-and-accelerators/fileact-interact/media/2e01feaa-6b68-49a2-a47d-6359be1f4034.gif "2e01feaa-6b68-49a2-a47d-6359be1f4034")  
  
 ファイル転送の状態は次のとおりです。  
  
-   **開始**– クライアントがサーバーに、ネゴシエーション メッセージが送信するが、まだ応答を受け取っていません。 サーバーは、ネゴシエーション要求を受け取りましたが、応答を送信されていません。  
  
-   **受け入れ**転送が進行中 – と、サーバーが、要求が承認され、応答メッセージで、TransferAnswer を受信しました。  
  
-   **拒否**– サーバーは要求を拒否しました、TransferAnswer が応答メッセージ、および転送が終了します。  
  
-   **継続的な**– 転送中は、(前述のように定期的に更新された) 処理を続行します。  
  
-   **完了**– 限り転送の指定された側は、ダイジェスト値の比較を含む、ファイル転送が正常に完了します。  
  
-   **失敗**– ファイルの転送処理に失敗しました、データ アクセスのため、通信するか、タイムアウト例外。 (注: SWIFTNet リンクによってタイムアウトが適用され、値は SWIFT によって決まります)。  
  
-   **中止**– ファイルの転送が中止されました (いずれか該当の問題、中止の側面)。  
  
-   **不明なと重複している**– タイミングのためだけにこの状態が発生します。 場合は、送信側ファイルすることは再送信 (PDIndicator) の重複する可能性のあるとしてマークされています。 場合は、受信するとき、PDIndicator 意味こと、ファイルが既に送信されて、FileAct アダプターは確認、重複の場合に検出されたは、TransferAnswer が重複している現在の試行を終了するを返します。  
  
## <a name="see-also"></a>参照  
 [FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [FileAct アダプター リアルタイム エンド ツー エンド プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [FileAct アダプターのリアルタイム ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [FileAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [FileAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [FileAct アダプター ファイルおよび転送の識別](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [FileAct アダプターをサポートする情報の転送](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [FileAct アダプター配信通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)