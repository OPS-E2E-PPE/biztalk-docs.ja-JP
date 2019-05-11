---
title: SWIFT 受信アダプター セキュリティ コンテキスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3db2b534-db9d-4075-aaad-0974b024dc71
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1ce4136efb28c8535b01b86cb55e84456e7773a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364471"
---
# <a name="swift-receive-adapter-security-context"></a>SWIFT 受信アダプター セキュリティ コンテキスト
送信アダプターとは異なり、受信アダプターは SWIFTNet リンク (SNL/RA) コマンド プロンプト (SWIFTNet 開始) から起動します。 実行可能ファイル受信アダプターは、RA SNL/構成ファイル (paramconfig) で構成されます。 起動時にアダプターでは、コマンド ライン パラメーターに基づく SNL ライブラリを初期化します。 後で使用するには、構成値がキャッシュされます。  
  
 次の図は、受信アダプター セキュリティ コンテキストの構成を示します。  
  
 ![SWIFT 受信アダプター セキュリティ コンテキスト](../../adapters-and-accelerators/fileact-interact/media/f48c7cd1-b162-45ea-9ec3-7936f61563c2.gif "f48c7cd1-b162-45ea-9ec3-7936f61563c2")  
  
## <a name="see-also"></a>参照  
 [SWIFT 受信アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)   
 [SWIFT 受信アダプターの URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md)   
 [SWIFT 受信アダプターの初期化](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md)   
 [SWIFT 受信アダプターの同期および遅延モード](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md)   
 [SWIFT 受信アダプターのストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)