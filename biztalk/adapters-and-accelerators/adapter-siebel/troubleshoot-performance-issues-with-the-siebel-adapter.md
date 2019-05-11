---
title: Siebel アダプターを使用したパフォーマンスの問題のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, performance issues
- performance, troubleshooting
ms.assetid: fe413b15-f703-4148-99df-17b5be3c74c1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2c5ecd89cfe3ea284bdc3264e8db597f29fdde7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370409"
---
# <a name="troubleshoot-performance-issues-with-the-siebel-adapter"></a>Siebel アダプターを使用したパフォーマンスの問題をトラブルシューティングします。
このセクションを使用する場合に発生する可能性のあるパフォーマンスの問題を解決するのには、トラブルシューティングの手法を使用して説明します[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]します。  
  
## <a name="known-issues"></a>既知の問題  
  
###  <a name="slowdown-or-stall-in-throughput-when-using-the-adapter-with-biztalk-server"></a>速度低下またはスループットのアダプターを BizTalk Server を使用すると停止  
 **問題**  
  
 使用する場合、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、アダプターによって送信または受信メッセージの数が遅くなったり、停止します。  
  
 **原因**  
  
 **EnableBizTalkCompatibilityMode**プロパティのバインドが設定されておらず、Wcf-custom 送信ポートまたは受信ポートを BizTalk Server 管理コンソールでします。  
  
 **解決方法**  
  
 設定、 **EnableBizTalkCompatibilityMode**プロパティを True にバインドします。 このプロパティの詳細については、次を参照してください。 [Siebel のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)します。 バインドのプロパティを設定する方法については、次を参照してください。 [for Siebel のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md)します。  
  
## <a name="see-also"></a>参照  
[Siebel アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)