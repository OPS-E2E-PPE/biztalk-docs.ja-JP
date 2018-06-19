---
title: SWIFT 受信アダプター セキュリティ コンテキスト |Microsoft ドキュメント
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
ms.openlocfilehash: b381ba9b4e0e1d53eca8e6cdd01b9770eb82372f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223826"
---
# <a name="swift-receive-adapter-security-context"></a>SWIFT 受信アダプター セキュリティ コンテキスト
送信アダプターとは異なり、受信アダプターは、SWIFTNet リンク (SNL/RA) コマンド プロンプトから起動 (SWIFTNet 開始)。 SNL/RA 構成ファイル (paramconfig) では、実行可能ファイルの受信アダプターを構成します。 スタートアップ時にアダプターでは、コマンド ライン パラメーターに基づく SNL ライブラリを初期化します。 後で使用するには、構成値がキャッシュされます。  
  
 次の図は、受信アダプター セキュリティ コンテキストの構成を示します。  
  
 ![SWIFT 受信アダプター セキュリティ コンテキスト](../../adapters-and-accelerators/fileact-interact/media/f48c7cd1-b162-45ea-9ec3-7936f61563c2.gif "f48c7cd1-b162-45ea-9ec3-7936f61563c2")  
  
## <a name="see-also"></a>参照  
 [SWIFT 受信アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)   
 [SWIFT 受信アダプター URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md)   
 [SWIFT 受信アダプターの初期化](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md)   
 [SWIFT 受信アダプターの同期および遅延モード](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md)   
 [SWIFT 受信アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)