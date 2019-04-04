---
title: ポートのバインド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ports, warnings
- ports, bindings
- bindings, Web ports
- bindings, design time
- Web ports, port bindings
- bindings, ports
- bindings, direct
- bindings, warnings
- bindings, deployment
- bindings, dynamic
ms.assetid: b61c725a-0082-42d3-b88a-533583161734
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f74e60db9b3a5994ff04f13fe2f242792cf2dcc7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972539"
---
# <a name="port-bindings"></a>ポートのバインド
ポートのバインドとは、メッセージを送受信する場所と方法を定義した構成情報です。 ポートのバインドの参照先は、物理的な場所、パイプライン、他のオーケストレーションなど、バインドの種類によって異なります。  
  
 メッセージを受信するポートのバインドには次の 3 種類があります。  
  
- 今指定します。  
  
- 後で指定します。  
  
- [直接]  
  
  メッセージを送信するポートのバインドには次の 4 種類があります。  
  
- 今指定します。  
  
- 後で指定します。  
  
- [直接]  
  
- 動的  
  
## <a name="binding-at-deployment-time"></a>展開時のバインド  
 ポートを受信場所または送信ポートにバインドできます。 すべての情報の物理的な場所を指定する必要がないと場合、選択、**後で指定する**のみをオーケストレーション デザイナーでポートのバインド オプションをポートをについて説明します。 ポートの種類を指定する必要があります。 アプリケーションを展開したら、BizTalk Server 管理コンソールを使用して場所に関する情報を指定できます。また、プログラムで場所情報を構成することもできます。  
  
## <a name="binding-at-design-time"></a>デザイン時のバインド  
 選択することができます、**今指定する**ポートのデザイン時に、トランスポートとパイプラインを指定するオーケストレーション デザイナーでバインド オプション。 受信メッセージのポートを指定する場合にドロップダウン リストから選択できるのは、HTTP、SOAP、および FILE の各トランスポートだけです。 送信メッセージのポートを指定する場合にドロップダウン リストから選択できるのは、HTTP、FILE、および SMTP の各トランスポートだけです。 このオプションは、メッセージの送信元または送信先があらかじめわかっている場合に使用すると便利です。  
  
## <a name="direct-binding"></a>直接バインド  
 直接バインド ポートは、物理ポートに明示的にバインドされているオーケストレーション内の一方向または双方向の論理ポートです。 直接バインド ポートを使用すると、サービス間で異なる通信方式を利用できます。 直接バインドを実装するには、選択、**直接**ポートのデザイン時にオーケストレーション デザイナーでバインド オプション。  
  
 直接バインド ポートには次の 3 種類があります。  
  
- メッセージ ボックスの直接バインド ポート  
  
- 自己関連付けを行う直接バインド ポート  
  
- パートナー オーケストレーションの直接バインド ポート  
  
  直接バインド ポートを操作する方法の詳細については、[オーケストレーションでの直接バインド ポートの操作](../core/working-with-direct-bound-ports-in-orchestrations.md)を参照してください。  
  
> [!NOTE]
>  直接バインドを使用する場合、1 つの要求 - 応答ポートと 2 つの一方向ポートの間でメッセージを交換することはできません。  
  
> [!NOTE]
>  直接バインドは、BPEL4WS (Business Process Engineering Language for Web Services) 標準に準拠していません。 BPEL4WS に準拠する必要がある場合は、他の種類のバインドを使用してください。  
  
## <a name="dynamic-binding"></a>動的バインド  
 実行時まで送信先がわからない場合は、送信ポートに対して動的バインドを使用できます。 場所可能性がありますなど、受信メッセージのプロパティから決定なりで指定し、**式**図形、次のコードに示すようにします。  
  
```  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="mailto:johnd@contoso.com";  
```  
  
 ポートに値を動的に割り当てる方法については、[動的ポートに値を割り当てる方法](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md)を参照してください。  
  
## <a name="web-ports"></a>Web ポート  
 プロジェクトに Web サービスへの参照が含まれる場合、オーケストレーション デザイナーで参照が検出されて、対応する Web ポートの種類が使用できるようになります。 Web ポートを作成するには、オーケストレーションにポートを追加して、既存の Web ポートの種類を割り当てます。 詳細については、[Web ポートの作成](../core/creating-web-ports.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [ポートの種類を操作する方法](../core/how-to-work-with-port-types.md)   
 [通信方式](../core/communication-pattern.md)   
 [通信方向](../core/communication-direction.md)   
 [オーケストレーションでポートを使用します。](../core/using-ports-in-orchestrations.md)   
 [ポート構成ウィザードを実行する方法](../core/how-to-run-the-port-configuration-wizard.md)   
 [Web サービスの利用](../core/consuming-web-services.md)