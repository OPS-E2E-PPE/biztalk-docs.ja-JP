---
title: Siebel アダプターを物理ポートのバインドを手動で構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- physical port binding, manually configuring
- how to, manually configure adapters for sending messages to a Siebel system
ms.assetid: a1445b8a-440f-45e8-96e9-a13142ca87c6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25afdeaf544cddb67440d050690ca8ca08df4547
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020034"
---
# <a name="manually-configure-a-physical-port-binding-to-the-siebel-adapter"></a>Siebel アダプターを物理ポートのバインドを手動で構成します。
このセクションでは、構成に関する情報を提供、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]を使用して WCF カスタム バインドとして、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 アダプタの展開後にすることを使用しての Siebel システムからメッセージを送受信、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 アダプタの展開の手順の間の通信の方向によって異なります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。 送信または送受信ポートを構成することができます。 選択項目は次のとおりです。  
  
|ポートの方向|通信方式|選択する通信の方向|  
|---|---|---|  
|Send|一方向|常にこのポートでメッセージを送信します。|  
|送信 - 受信|要求 - 応答|要求の送信と応答の受信をされます。|  
  
 詳細については、次を参照してください。[構成する送信ポートの作成と](../../core/creating-and-configuring-send-ports.md)します。
  
> [!NOTE]
>  受信ポートはため、サポートされていません、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel システムからの受信操作を有効にしません。  
> 
> [!NOTE]
>  によって作成されるバインド構成ファイルをインポートすることで、Wcf-custom 送信ポートを構成することも、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部として。 このバインド ファイルを使用してポートを構成する方法の詳細については、次を参照してください。 [Siebel にポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)します。
  
 
  
## <a name="see-also"></a>参照  
[Siebel アダプターを使用した BizTalk アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)