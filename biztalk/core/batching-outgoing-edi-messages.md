---
title: "送信 EDI メッセージをバッチ処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93a2bd68-4974-4927-938a-8eaf8f007566
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f95ed755dcc709084d52c6fb8b207e9bbd9e866d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="batching-outgoing-edi-messages"></a>送信 EDI メッセージのバッチ処理
受信側のビジネス パートナーに関連するアグリーメントに対してバッチ処理が有効になっている場合、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では EDI トランザクション セットがバッチ処理されます。 アグリーメントに関する EDI プロパティを設定すると、以下を行うことができます。  
  
-   複数の送信バッチの定義  
  
-   インターチェンジの定義  
  
-   インターチェンジ内のグループの定義  
  
-   バッチ リリース条件の設定  
  
-   バッチ アクティベーション条件の設定  
  
 Microsoft [!INCLUDE[prague](../includes/prague-md.md)] EDI および AS2 を使用すると、EDI インターチェンジの以下の処理が可能になります。  
  
-   EDI インターチェンジにトランザクション セットや受信確認を含めることができます。  
  
-   EDI 受信パイプラインは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] による後続処理のためにインターチェンジを XML トランザクション セットに分割するか、インターチェンジを維持して、その受信フォームで [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を通過させることができます。  
  
-   EDI ルーティング オーケストレーションにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、単一のトランザクション セットをバッチ処理して、複数の送信インターチェンジに分割できます。  
  
-   EDI バッチ処理オーケストレーションは、XML トランザクション セットを EDI インターチェンジにアセンブルして、アグリーメントの EDI プロパティに基づいてインターチェンジを検証し、配布します。  
  
 インターチェンジと呼ばれる EDI バッチには、メッセージ グループが含まれ、メッセージ グループには、個々のメッセージが含まれます。 送信バッチには、複数のグループを含めることができますが、ドキュメントの種類ごとに含められるグループは 1 つだけです。 グループには、複数のトランザクション セットを含めることができますが、各トランザクション セットのドキュメントの種類が同じである必要があります。 メッセージ エンベロープは、個々のトランザクション セット、個々のグループ、およびインターチェンジ全体をラップするために使用されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [送信バッチの構成](../core/configuring-an-outgoing-batch.md)  
  
-   [バッチ EDI インターチェンジをアセンブル](../core/assembling-a-batched-edi-interchange.md)  
  
-   [保存されたバッチ インターチェンジを送信します。](../core/sending-a-preserved-batch-interchange.md)