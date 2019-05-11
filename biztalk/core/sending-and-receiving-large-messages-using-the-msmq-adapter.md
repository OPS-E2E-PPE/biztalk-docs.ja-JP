---
title: MSMQ アダプターを使用してサイズの大きいメッセージの送受信 |Microsoft Docs
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
ms.openlocfilehash: 8b5a1267aa0ee1ffc2d44326ad8922d6fac16a1c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399028"
---
# <a name="sending-and-receiving-large-messages-using-the-msmq-adapter"></a>MSMQ アダプターを使用してサイズの大きいメッセージを送受信します。
MSMQ アダプターの既定のメッセージ処理、部分的に異なります、メッセージのサイズ。 メッセージが 4 メガバイト (4 MB) の場合は、MSMQ アダプターは、.NET Framework クラス ライブラリを使用します。 Microsoft では、サイズの大きいメッセージの拡張機能を使用して、それ以外の場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
 アプリケーションは一貫して受信またはサイズの大きいメッセージを送信、アダプターが使用するメモリの量を制御する必要があります。 メモリの節約の詳細については、次を参照してください。 [MSMQ アダプターのパフォーマンスの最適化](../core/optimizing-performance-of-the-msmq-adapter.md)します。  
  
## <a name="see-also"></a>参照  
 [MSMQ アダプターのパフォーマンスを最適化します。](../core/optimizing-performance-of-the-msmq-adapter.md)   
 [MSMQ アダプターの構成](../core/configuring-the-msmq-adapter.md)