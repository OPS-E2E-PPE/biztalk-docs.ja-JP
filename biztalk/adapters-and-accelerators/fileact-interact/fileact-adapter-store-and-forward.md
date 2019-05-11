---
title: FileAct アダプターのストア アンド フォワード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50110bf0-75c2-426c-9833-65c3117224b2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6971d1b65f32018b15bf8ae022ca6d64d23701da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367172"
---
# <a name="fileact-adapter-store-and-forward"></a>FileAct アダプターのストア アンド フォワード
ストアに順方向 (SnF) モードでは、ファイルに配信し、送信時にキューに登録し、変換先にキューから取得されます。 中間の応答は、ファイルが先に安全に配信されるまでに、SWIFTNet によって送信者に返されます。  
  
## <a name="sending-using-snf"></a>SnF を使用して送信します。  
 一方向の送信ポートを作成する場合、アダプターは SnF モードで動作し、キューにメッセージを送信します。  
  
## <a name="receiving-using-snf"></a>SnF を使用して受信  
 SnF FileAct はプッシュ モードで動作します。 これは、実行時オプションです。  
  
 キューからメッセージを取得できないようにするには、前に SWIFTNet SnF はキューを取得する要求を受信する必要があります。 これは、アウト プロセス COM + コンポーネントを呼び出して、受信アダプターによって実現されます。 成功した acquire では、セッションが作成されます。 キューは、要求で指定されたモードで、開けません。 要求を発行した物理ノードに、すべてのメッセージが返されます。  
  
 指定された順序 (InterAct および FileAct の送信の混在、および優先度別に並べ替えることに注意) でメッセージが配信されます。ただし、メッセージのシーケンス処理は、格納されているかの時間に依存します。 FileAct の場合、開始時ではなく、file storage が完了した時間です。  
  
### <a name="push-a-file-from-the-queue"></a>キューからファイルをプッシュします。  
 FileAct アダプター (サーバー) では、キュー、セッション、およびシーケンスの情報を含む SWIFTNet から、HandleFileRequest を受信します。 サーバーは、HandleFileResponse で応答します。  
  
 サーバーが、FetchFileRequest を発行し、ファイルがサーバーに配信します。  
  
## <a name="see-also"></a>参照  
 [FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [FileAct アダプターのリアルタイム エンド ツー エンド プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [FileAct アダプターのリアルタイム ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [FileAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [FileAct アダプター ファイルおよび転送 Id](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [FileAct アダプターのサポート情報の転送](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [FileAct アダプターの配信通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [FileAct アダプターの状態監視](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)