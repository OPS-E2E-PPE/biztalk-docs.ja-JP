---
title: 送信 EDI メッセージをバッチ処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93a2bd68-4974-4927-938a-8eaf8f007566
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57eaeee848ae5c9ea316b9f0b5998805581faca1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358286"
---
# <a name="batching-outgoing-edi-messages"></a>送信 EDI メッセージのバッチ処理
受信側のビジネス パートナーに関連するアグリーメントに対してバッチ処理が有効になっている場合、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では EDI トランザクション セットがバッチ処理されます。 アグリーメントに関する EDI プロパティを設定すると、以下を行うことができます。  
  
- 複数の送信バッチの定義  
  
- インターチェンジの定義  
  
- インターチェンジ内のグループの定義  
  
- バッチ リリース条件の設定  
  
- バッチ アクティベーション条件の設定  
  
  Microsoft BizTalk Server の EDI および AS2 EDI インターチェンジの以下の処理を有効にします。  
  
- EDI インターチェンジにトランザクション セットや受信確認を含めることができます。  
  
- EDI 受信パイプラインは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] による後続処理のためにインターチェンジを XML トランザクション セットに分割するか、インターチェンジを維持して、その受信フォームで [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を通過させることができます。  
  
- EDI ルーティング オーケストレーションにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、単一のトランザクション セットをバッチ処理して、複数の送信インターチェンジに分割できます。  
  
- EDI バッチ処理オーケストレーションは、XML トランザクション セットを EDI インターチェンジにアセンブルして、アグリーメントの EDI プロパティに基づいてインターチェンジを検証し、配布します。  
  
  インターチェンジと呼ばれる EDI バッチには、メッセージ グループが含まれ、メッセージ グループには、個々のメッセージが含まれます。 送信バッチには、複数のグループを含めることができますが、ドキュメントの種類ごとに含められるグループは 1 つだけです。 グループには、複数のトランザクション セットを含めることができますが、各トランザクション セットのドキュメントの種類が同じである必要があります。 メッセージ エンベロープは、個々のトランザクション セット、個々のグループ、およびインターチェンジ全体をラップするために使用されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [送信バッチの構成](../core/configuring-an-outgoing-batch.md)  
  
-   [バッチ EDI インターチェンジのアセンブル](../core/assembling-a-batched-edi-interchange.md)  
  
-   [保存されたバッチ インターチェンジの送信](../core/sending-a-preserved-batch-interchange.md)