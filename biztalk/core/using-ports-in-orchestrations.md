---
title: オーケストレーションでポートを使用して |Microsoft ドキュメント
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
ms.openlocfilehash: f7f48c1c070e3a3a3e7ebe7e86618a4fd9ebc90d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287418"
---
# <a name="using-ports-in-orchestrations"></a>オーケストレーションでのポートの使用
ポートを使用して、オーケストレーションでの、他のビジネス プロセスを対象としたメッセージの送受信方法を指定します。 各ポートは、種類、方向、バインドを保持しています。これらの組み合わせによって、通信方向、通信方式、メッセージの送信先場所と送信元場所、および通信の実行方法が決まります。  
  
> [!NOTE]
>  ポートとポートの種類は異なります。 ポートは、ポートの種類のインスタンスです。このため、複数の異なるポートが同じポートの種類を保持する場合もあります。  
  
 これらの要素に応じて、ポートは、URI (物理的な場所)、トランスポート (FILE、HTTP、SOAP、SMTP、または BizTalk メッセージ キュー)、送信用のメッセージを準備する (たとえば、他の操作のアセンブル、暗号化、圧縮、または実行を行う) 送信パイプライン、および処理用の受信メッセージを準備する (たとえば、メッセージの逆アセンブル、復号化、または圧縮解除を行う) 受信パイプラインと関連付けられます。  
  
 コントロールを Web フォームまたは Windows フォームに追加する場合と同じ方法で、ポートをオーケストレーションに追加します。 [オーケストレーションの種類] ウィンドウで、ポートを追加することもできます。  
  
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
 [オーケストレーションでロール リンクの使用](../core/using-role-links-in-orchestrations.md)