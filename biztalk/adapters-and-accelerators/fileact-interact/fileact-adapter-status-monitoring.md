---
title: FileAct アダプターの状態の監視 |Microsoft Docs
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
ms.openlocfilehash: 1701e68b592e7f6eab012d14b1a14d6143c09da9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367154"
---
# <a name="fileact-adapter-status-monitoring"></a>FileAct アダプターの状態の監視
ファイル転送、およびこれらの状態遷移の状態は、次の図に示します。  
  
 ![FileAct アダプター ファイル転送状態](../../adapters-and-accelerators/fileact-interact/media/2e01feaa-6b68-49a2-a47d-6359be1f4034.gif "2e01feaa-6b68-49a2-a47d-6359be1f4034")  
  
 ファイル転送の状態は次のとおりです。  
  
-   **開始**– クライアントは、サーバーに、ネゴシエーション メッセージが送信しますが、まだ応答を受け取っていません。 サーバーは、ネゴシエーションの要求を受け取りましたが、まだ応答は送信されません。  
  
-   **受け入れられる**転送が進行中 – と、サーバーが要求を受け入れるし、応答メッセージで、TransferAnswer が送信されます。  
  
-   **拒否**– サーバー要求を拒否しましたが、応答メッセージには、TransferAnswer および転送が終了します。  
  
-   **継続的な**: 転送が進行中とは (定期的に更新上記として) 続行されます。  
  
-   **完了した**– ダイジェスト値の比較を含む、転送の側がに関する限り、ファイル転送が正常に完了します。  
  
-   **失敗**– ファイルの転送が、データ アクセスのため通信またはタイムアウトの例外の処理が失敗しました。 (注。SWIFTNet リンクでタイムアウトが適用され、値によって決定されます SWIFT)。  
  
-   **中止**– ファイルの転送が中止されました (いずれかの側面、中止問題)。  
  
-   **不明なと重複している**– この状態は、タイミングのためのみに発生します。 場合は、送信側、ファイルがあります再送信 (PDIndicator) を重複している可能性があるとしてマークされています。 場合は、受信側、PDIndicator 意味のあるファイルが既に送信されて、FileAct アダプターは確認、重複の場合に見つかりましたでは、TransferAnswer の重複している現在の試行が終了するのに戻ります。  
  
## <a name="see-also"></a>参照  
 [FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [FileAct アダプターのリアルタイム エンド ツー エンド プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [FileAct アダプターのリアルタイム ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [FileAct アダプターのストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [FileAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [FileAct アダプター ファイルおよび転送 Id](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [FileAct アダプターのサポート情報の転送](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [FileAct アダプターの配信通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)