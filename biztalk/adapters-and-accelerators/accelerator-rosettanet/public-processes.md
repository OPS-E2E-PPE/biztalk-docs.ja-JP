---
title: パブリック プロセス |Microsoft Docs
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
ms.openlocfilehash: 426884dd700ad5b7862b5c191339b8ca49388232
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282611"
---
# <a name="public-processes"></a>パブリック プロセス
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]パブリック プロセスとして取引先との統合に関係するビジネス プロセスを実装します。 プライベート プロセスとして、組織の内部ビジネス プロセスを実装します。 パブリックおよびプライベート プロセスを使用して、service content 処理とバックエンド統合 (プライベート プロセス) 内から Framework RNIF (RosettaNet Implementation) (パブリック プロセス) 内の処理を分離します。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] パブリック プロセスは、長時間実行される BizTalk オーケストレーションとして実装します。 1 つのパブリック プロセス オーケストレーションは、発信側と応答側のいずれかで実行されます。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]セットアップ プログラムは、イニシエーターとレスポンダーのバージョンの RNIF 1.1 および RNIF 2.01 用のパブリック プロセス オーケストレーションを提供します。  
  
 これらのパブリック プロセス オーケストレーションは、すべての RNIF プロセスを実装します。 パブリック プロセスには、残りのコンポーネントから RNIF の複雑さが非表示にします。 RNIF 準拠のメッセージ フローをするだけでなく、パブリック プロセスも既定の追跡設定を決定し、実行時にプロセス状態に関する情報を提供します。 メッセージの service content は処理されません。 プライベート プロセスで行われます。  
  
 各取引先アグリーメントは、1 つのパブリック プロセスを開始またはプロセス PIP (Partner Interface) の操作に対する応答を参照します。 ただし、パブリック プロセスでは PIP は認識されません。  
  
 RosettaNet の仕様では、パブリック プロセスの設計を決定します。 パブリック プロセスを変更しないことをお勧めします。 パブリック プロセス オーケストレーションとは、バージョン管理され、署名付きです。 パブリック プロセスを変更することと、RNIF 準拠ができなくなります。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [イニシエーター パブリック プロセス](../../adapters-and-accelerators/accelerator-rosettanet/initiator-public-process.md)  
  
-   [レスポンダー パブリック プロセス](../../adapters-and-accelerators/accelerator-rosettanet/responder-public-process.md)