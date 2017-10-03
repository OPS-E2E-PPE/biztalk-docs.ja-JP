---
title: "Siebel アダプターのパフォーマンスの問題のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting, performance issues
- performance, troubleshooting
ms.assetid: fe413b15-f703-4148-99df-17b5be3c74c1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6443dd8b96b19b3cf42f6444ba1ae6c16f2b4ee6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-performance-issues-with-the-siebel-adapter"></a>Siebel アダプターのパフォーマンスの問題をトラブルシューティングします。
このセクションで説明を使用する場合に発生する可能性があるパフォーマンスの問題を解決するのには、トラブルシューティングの手法を使用して[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]です。  
  
## <a name="known-issues"></a>既知の問題  
  
###  <a name="slowdown-or-stall-in-throughput-when-using-the-adapter-with-biztalk-server"></a>処理速度が低下またはスループットのアダプターを BizTalk Server を使用すると停止  
 **問題**  
  
 使用する場合、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、アダプターによって送信または受信メッセージの数が遅くなったり、stall にします。  
  
 **原因**  
  
 **EnableBizTalkCompatibilityMode** binding プロパティが設定されていない Wcf-custom 送信ポートまたは受信ポートを BizTalk Server 管理コンソールでします。  
  
 **解決策**  
  
 設定、 **EnableBizTalkCompatibilityMode**バインディング プロパティを True に設定します。 このプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Siebel のバインドのプロパティについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)です。 バインディング プロパティを設定する方法の手順については、次を参照してください。 [Siebel のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md)です。  
  
## <a name="see-also"></a>参照  
[Siebel アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)