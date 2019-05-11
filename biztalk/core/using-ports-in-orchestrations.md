---
title: オーケストレーションでポートを使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, receiving
- ports, configuring manually
- send ports, messages
- ports, creating
- ports, messages
- creating, ports
- send ports, sending
- ports, operations
- configuring, ports
- ports, deleting
- deleting, ports
- orchestrations, ports
- Port Configuration Wizard [Orchestration Designer]
- ports
- ports, about ports
- ports, configuring
ms.assetid: 968b2d1b-e233-4eb0-8254-9ec6b7642cdf
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2204e5bb00cd6614c66f9325f043db131b402fbd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396576"
---
# <a name="using-ports-in-orchestrations"></a>オーケストレーションでポートを使用します。
ポートは、オーケストレーションはメッセージを送信し、他のビジネス プロセスからメッセージを受信する方法を指定します。 各ポートは、種類、方向、バインドを保持しています。これらの組み合わせによって、通信方向、通信方式、メッセージの送信先場所と送信元場所、および通信の実行方法が決まります。  
  
> [!NOTE]
>  ポートとポートの種類の間の違いがあります。 ポート、ポートの種類のインスタンスとは複数のポートと同じポートの種類があります。  
  
 これらの要因に応じて、ポートが関連付けられていると (たとえば、アセンブル、暗号化、圧縮を送信するため、メッセージを準備するには、URI (物理的な場所)、トランスポート (FILE、HTTP、SOAP、SMTP または BizTalk メッセージ キュー)、送信パイプラインまたは他の何らかのアクションを実行することで)、および受信パイプライン処理 (たとえば、逆アセンブル、復号化、または、展開で) 受信したメッセージを準備します。  
  
 ポートを追加でオーケストレーションを Web フォームまたは Windows フォーム コントロールを追加することと同じ方法。 オーケストレーションの種類 ウィンドウを使用してポートを追加することもできます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [通信方式](../core/communication-pattern.md)  
  
-   [通信方向](../core/communication-direction.md)  
  
-   [ポートのバインド](../core/port-bindings.md)  
  
-   [オーケストレーションでポートを使用する方法](../core/how-to-use-ports-in-orchestrations.md)  
  
-   [ポートの種類を操作する方法](../core/how-to-work-with-port-types.md)  
  
-   [ポート構成ウィザードを実行する方法](../core/how-to-run-the-port-configuration-wizard.md)  
  
-   [オーケストレーションでの直接バインド ポートの操作](../core/working-with-direct-bound-ports-in-orchestrations.md)  
  
## <a name="see-also"></a>参照  
 [ポート構成ウィザードを実行する方法](../core/how-to-run-the-port-configuration-wizard.md)   
 [オーケストレーションでのロール リンクの使用](../core/using-role-links-in-orchestrations.md)