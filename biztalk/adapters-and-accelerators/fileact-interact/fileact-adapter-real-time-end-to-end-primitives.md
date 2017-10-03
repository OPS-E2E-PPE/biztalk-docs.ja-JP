---
title: "FileAct アダプター リアルタイム エンド ツー エンド プリミティブ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8591120-7259-49cb-90ac-954d8be226ed
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c95e52d4fbd5ec0df8ee580583f429ffe9e0f08d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="fileact-adapter-real-time-end-to-end-primitives"></a>FileAct アダプター リアルタイム エンド ツー エンド プリミティブ
SWIFTNet プリミティブが、アプリケーションと SWIFTNet リンク (SNL) の間で交換される XML ドキュメントのペアです。 各エンド ツー エンド プリミティブ型、そこに側のプリミティブ – クライアント (または送信) の横にあるいずれかと、サーバーで 1 つのバージョンの 2 つ (または受信)。 4 つのメッセージの合計が含まれます。 ファイルの配置のプリミティブ、ファイルの取得のプリミティブ型、およびそれぞれに対して配信通知を送信します。  
  
 FileAct エンド ツー エンド プリミティブを次の図に示します。  
  
 ![FileAct エンド &#45; へ (& a) #45; エンド プリミティブ](../../adapters-and-accelerators/fileact-interact/media/6e3520cc-9ec4-445c-9114-c7cb760c1068.gif "6e3520cc-9ec4-445c-9114-c7cb760c1068")  
  
## <a name="put-file"></a>ファイルを配置します。  
 アプリケーションでは、別の SWIFTNet ユーザーのファイル システムにファイルを送信するファイルの Put プリミティブを開始します。 エンド ツー エンド関数としては、クライアント側とサーバーの両方の側ファイルの Put プリミティブです。 これらが共同して、ファイル転送を正常に完了します。  
  
 このような各共同作業は、1 つのファイルを送信します。 複数のファイルの Put プリミティブは、並列で実行する場合があります。  
  
## <a name="get-file"></a>ファイルを取得します。  
 アプリケーションでは、別の SWIFTNet ユーザーのファイル システムからファイルを取得するファイルの取得プリミティブを開始します。 エンド ツー エンド関数としては、クライアント側とサーバー側の両方のファイルの取得プリミティブです。 これらが共同して、ファイル転送を正常に完了します。  
  
 このような各共同作業は、1 つのファイルを取得します。 複数のファイルの取得プリミティブは、並列で実行する場合があります。  
  
## <a name="send-delivery-notification"></a>配信通知を送信します。  
 配置のすべてのファイルとプリミティブのすべての Get ファイルを受信側は、ファイルの転送に関連する配信通知を返すファイル要求の送信側のオプションがあります。 ファイルの Put プリミティブは、要求メッセージには、配信通知の要求が含まれています。  
  
 ファイルの場合、取得プリミティブは、応答メッセージには、配信通知の要求が含まれています。  
  
 どちらの場合、(実行することによって、転送が完了状態になったことを確認する、状態のプリミティブのいずれか)、ファイルを全体が受信されたことと、ファイルを十分に安全にされたことを確認する (たとえば、バック オフィス システムの場合) に格納された後、受信側のアプリケーションでは、送信者への配信の正の値の確認を返す、配信通知プリミティブとは別に実行します。 エンド ツー エンド関数としては、クライアント側とサーバー側の両方の配信通知プリミティブがあります。 これらが共同して、ファイル配信通知を正常に完了します。  
  
 配信通知を設定し、送信側と受信側のファイルの間のプロトコルを適用サービス デザイナーが必要です。  
  
## <a name="see-also"></a>参照  
 [FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [FileAct アダプターのリアルタイム ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [FileAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [FileAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [FileAct アダプター ファイルおよび転送の識別](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [FileAct アダプターをサポートする情報の転送](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [FileAct アダプター配信通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [FileAct アダプター状態の監視](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)