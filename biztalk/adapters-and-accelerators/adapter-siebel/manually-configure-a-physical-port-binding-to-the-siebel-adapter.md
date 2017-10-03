---
title: "Siebel アダプターを物理ポートのバインドを手動で構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- physical port binding, manually configuring
- how to, manually configure adapters for sending messages to a Siebel system
ms.assetid: a1445b8a-440f-45e8-96e9-a13142ca87c6
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed94ca9f6a44919684d36a1be931cbb33f746377
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="manually-configure-a-physical-port-binding-to-the-siebel-adapter"></a>Siebel アダプターを物理ポートのバインドを手動で構成します。
このセクションの構成に関する情報を提供する、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]を使用して WCF カスタム バインドとして、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 アダプターを展開したらことができますを使用しての Siebel システムからメッセージを送受信する、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 アダプタの展開の手順の間の通信の方向によって異なる[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。 送信ポートまたは送信受信ポートを構成することができます。 選択項目は次のとおりです。  
  
|ポートの方向|通信方式|選択への通信方向|  
|---|---|---|  
|Send|一方向|常にこのポートでメッセージを送信します。|  
|送信 - 受信|要求 - 応答|要求の送信と応答の受信をされます。|  
  
 詳細については、次を参照してください。[の作成および構成する送信ポート](../../core/creating-and-configuring-send-ports.md)です。
  
> [!NOTE]
>  受信ポートがあるためにサポートされていません、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel システムの受信操作を有効にしません。  
  
> [!NOTE]
>  によって作成されるバインディングの構成ファイルをインポートして、Wcf-custom 送信ポートを構成することも、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部として。 このバインド ファイルを使用するポートを構成する方法の詳細については、次を参照してください。 [Siebel するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)です。
  
 
  
## <a name="see-also"></a>参照  
[Siebel アダプターと BizTalk アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)