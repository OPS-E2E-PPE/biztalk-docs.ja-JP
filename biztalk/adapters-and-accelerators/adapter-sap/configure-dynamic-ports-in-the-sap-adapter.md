---
title: SAP アダプターの動的ポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- dynamic ports, configuring
- configuring, dynamic ports
ms.assetid: 4d6569f9-e513-47f3-b2c1-4c21bafb2bf2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de45553cfad2db19cfe16bbcd55420019b4971e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971507"
---
# <a name="configure-dynamic-ports-in-the-sap-adapter"></a>SAP アダプターの動的ポートを構成します。
## <a name="use-message-context-properties"></a>メッセージ コンテキスト プロパティを使用します。
[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の動的ポートを構成することができます、[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF ベース アダプターでは、用のポートを動的に構成することができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]メッセージ コンテキスト プロパティを使用しています。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]URI、アクション、およびバインドのプロパティを受信メッセージから決定され、式図形で指定されたし、次の例に示すように可能性があります。  
  
```  
Request2=Request1;  
Request2(WCF.Action)="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET";  
Request2(WCF.BindingType)="sapBinding";  
Request2(WCF.UserName)="YourUserName";  
Request2(WCF.Password)="YourPassword";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="sap://CLIENT=800;LANG=EN;@A/YourSAPHost/00";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
  
```  
  
> [!NOTE]
>  WCF-SAP アダプターを使用しているかどうかは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、指定することも、トランスポートの種類として`SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SAPAdapter"`ここで、 **SAPAdapter**の WCF-SAP アダプターを追加する名前を指定します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
 前の例。  
  
- Request1 メッセージから Request2 メッセージを作成しています。 どちらのメッセージが操作を使用して生成されるスキーマ、マップ、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]します。  
  
- 送信ポートは、BizTalk オーケストレーションの論理送信ポートの名前です。  
  
  式図形には、BizTalk オーケストレーションの一部です。 オーケストレーションを展開するときに、Wcf-custom 送信ポートも作成されます。  
  
  動的ポートの構成の詳細については、[動的送信ポートを使用して WCF アダプター コンテキスト プロパティの構成](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)を参照してください。
  
## <a name="see-also"></a>参照  
[SAP アプリケーションを作成するための構成要素](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)