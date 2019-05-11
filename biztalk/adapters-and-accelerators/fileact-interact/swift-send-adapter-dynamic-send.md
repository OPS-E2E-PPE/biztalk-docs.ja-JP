---
title: SWIFT 送信アダプターの動的送信 |Microsoft Docs
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
ms.openlocfilehash: 5161c47011a5239435739d08783e3da6f2547aaf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364191"
---
# <a name="swift-send-adapter-dynamic-send"></a>SWIFT 送信アダプターの動的送信
送信アダプターの動的な送信モードでは、キューからメッセージをプルします。 動的送信のための URI です。  
  
```  
SWIFT://<queue name>/<Force Acquire>/<Session Mode>/<Order By>/<Recovery mode>  
```  
  
 オーケストレーションまたはパイプラインを使用すると、URI を構築します。  
  
## <a name="see-also"></a>参照  
 [SWIFT 送信アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md)   
 [SWIFT 送信アダプターの URI](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-uri.md)   
 [SWIFT 送信アダプターの初期化](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-initialization.md)   
 [SWIFT 送信アダプター同期モード](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-synchronous-mode.md)   
 [SWIFT 送信アダプターの終了](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-termination.md)