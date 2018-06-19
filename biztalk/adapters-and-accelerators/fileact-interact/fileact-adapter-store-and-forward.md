---
title: FileAct アダプター ストア アンド フォワード |Microsoft ドキュメント
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
ms.openlocfilehash: 1201a5ab5cb45ceba2622aa1c269404acec910df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223570"
---
# <a name="fileact-adapter-store-and-forward"></a>FileAct アダプター ストア アンド フォワード
ストアで順方向 (SnF) モードでは、ファイルに配信されると送信時に queue され、変換先にキューから取得されます。 中間応答は、ファイルが変換先に安全に配信されるまでに、SWIFTNet によって送信者に返されます。  
  
## <a name="sending-using-snf"></a>SnF を使用して送信します。  
 一方向の送信ポートを作成する場合、アダプターは SnF モードで動作し、キューにメッセージを送信します。  
  
## <a name="receiving-using-snf"></a>SnF を使用して受信  
 SnF FileAct は、プッシュ モードで動作します。 これは、実行時オプションです。  
  
 キューからメッセージを取得できないようにするには、前に SWIFTNet SnF はキューを取得する要求を受信する必要があります。 これは、アウト オブ COM + コンポーネントを呼び出して、受信アダプターによって行います。 成功の取得後に、セッションが作成されます。 キューは、要求で指定されたモードで、開けません。 要求を発行した物理ノードに、すべてのメッセージが返されます。  
  
 (対話および FileAct 伝送の混在して、および優先度別に並べ替えることに注意)、指定された順序でメッセージが配信されます。ただし、メッセージのシーケンスが格納されている時間に左右されます。 FileAct の場合これは、開始時ではなく、ファイル ストレージが完了した時刻です。  
  
### <a name="push-a-file-from-the-queue"></a>ファイルをプッシュするキューから  
 FileAct アダプター (サーバー) では、キュー、セッション、およびシーケンスの情報を含む SWIFTNet から、HandleFileRequest を受信します。 サーバーは、HandleFileResponse で応答します。  
  
 FetchFileRequest は、サーバーから発行され、ファイルがサーバーに配信されます。  
  
## <a name="see-also"></a>参照  
 [FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [FileAct アダプター リアルタイム エンド ツー エンド プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [FileAct アダプターのリアルタイム ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [FileAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [FileAct アダプター ファイルおよび転送の識別](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [FileAct アダプターをサポートする情報の転送](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [FileAct アダプター配信通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [FileAct アダプター状態の監視](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)