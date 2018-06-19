---
title: SWIFT 送信アダプターの動的な送信 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 105972fe-9dc0-480a-a4d1-2ec682fa7ad9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75d63df8f38346e4f77e2b7bfa8e3effc93f2fce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222986"
---
# <a name="swift-send-adapter-dynamic-send"></a>SWIFT 送信アダプターの動的送信
送信アダプターの動的な送信モードでは、キューからメッセージをプルします。 動的送信のための URI です。  
  
```  
SWIFT://<queue name>/<Force Acquire>/<Session Mode>/<Order By>/<Recovery mode>  
```  
  
 URI を構築するために、オーケストレーションまたはパイプラインを使用することができます。  
  
## <a name="see-also"></a>参照  
 [SWIFT 送信アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md)   
 [SWIFT 送信アダプター URI](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-uri.md)   
 [SWIFT 送信アダプターの初期化](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-initialization.md)   
 [SWIFT 送信アダプター同期モード](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-synchronous-mode.md)   
 [SWIFT 送信アダプターの終了](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-termination.md)