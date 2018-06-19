---
title: パブリック プロセス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public processes, orchestrations
- business processes, public processes
- public processes, trading partners
- BTARN, public processes
- orchestrations, public-process orchestrations
- public processes
- trading partners, public processes
- public processes, about public processes
ms.assetid: 5ccc7449-5741-4d49-beb6-567bcd93f679
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6634a5d5871deac48fad1defbd79fae8f5f384ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210026"
---
# <a name="public-processes"></a>パブリック プロセス
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]をパブリック プロセスとして取引先との統合を伴うビジネス プロセスを実装します。 組織内部のビジネス プロセスは、プライベート プロセスとして実装されます。 パブリック プロセスとプライベート プロセスを使用することで、RNIF (RosettaNet Implementation Framework) の処理 (パブリック プロセス内) は、Service Content 処理とバックエンドの統合 (プライベート プロセス内) から独立します。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] では、長期にわたって実行される BizTalk オーケストレーションとして、パブリック プロセスを実装しています。 1 つのパブリック プロセスのオーケストレーションは開始側で実行され、もう 1 つのオーケストレーションは応答側で実行されます。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] セットアップ プログラムからは、RNIF 1.1 および RNIF 2.01 用の開始側パブリック プロセス オーケストレーションと応答側パブリック プロセス オーケストレーションの各バージョンが提供されます。  
  
 これらのパブリック プロセス オーケストレーションにより、すべての RNIF プロセスが実装されます。 パブリック プロセスでは、RNIF の複雑な部分はコンポーネントの他の部分からは見えないようになっています。 パブリック プロセスは RNIF 準拠のメッセージの流れをスムーズにするだけでなく、既定の追跡設定を指定し、実行時にプロセス状態に関する情報を提供します。 メッセージの Service Content は処理されません。 これは、プライベート プロセスが行います。  
  
 各取引先アグリーメントは単一のパブリック プロセスを参照して、PIP (Partner Interface Process) アクションを開始するか、アクションに応答します。 ただし、パブリック プロセスでは PIP は認識されません。  
  
 パブリック プロセスのデザインは、RosettaNet の仕様によって決定されます。 パブリック プロセスは変更しないことを推奨します。 パブリック プロセス オーケストレーションは、バージョン管理され、署名されています。 パブリック プロセスを変更すると、RNIF に準拠しなくなります。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [開始側パブリック プロセス](../../adapters-and-accelerators/accelerator-rosettanet/initiator-public-process.md)  
  
-   [応答側パブリック プロセス](../../adapters-and-accelerators/accelerator-rosettanet/responder-public-process.md)