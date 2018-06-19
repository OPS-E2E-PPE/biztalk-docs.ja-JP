---
title: MSMQ アダプターを使用してサイズの大きいメッセージを送受信する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, large messages
- configuring [MSMQ adapters], large messages
- MSMQ adapters, large messages
ms.assetid: 208efbed-7b58-4da5-ba27-65a315c2713b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a23265be84f2767849e4d61c2e9a95bfc9ed4ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269530"
---
# <a name="sending-and-receiving-large-messages-using-the-msmq-adapter"></a>MSMQ アダプタを使用したサイズの大きいメッセージの送受信
MSMQ アダプタの既定のメッセージ処理には、メッセージのサイズに依存する部分があります。 メッセージのサイズが 4 MB 未満の場合、MSMQ アダプタで .NET Framework クラス ライブラリが使用されます。 4 MB 以上の場合は、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の、サイズの大きいメッセージ用拡張機能が使用されます。  
  
 アプリケーションで、常にサイズの大きいメッセージの送受信を行う場合、アダプタで使用するメモリ量の制御が必要になることがあります。 メモリの節約の詳細については、次を参照してください。 [MSMQ アダプターのパフォーマンスの最適化](../core/optimizing-performance-of-the-msmq-adapter.md)です。  
  
## <a name="see-also"></a>参照  
 [MSMQ アダプターのパフォーマンスを最適化します。](../core/optimizing-performance-of-the-msmq-adapter.md)   
 [MSMQ アダプターの構成](../core/configuring-the-msmq-adapter.md)