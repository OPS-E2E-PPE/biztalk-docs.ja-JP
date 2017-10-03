---
title: "Siebel アダプターと動的ポートの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dynamic ports, configuring
- configuring, dynamic ports
ms.assetid: a3516c2c-d40e-426b-bf3f-f9dc3de105ef
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b036bf772e3e9580c84616f74786d4908aca7515
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-dynamic-ports-with-the-siebel-adapter"></a>Siebel アダプターと動的ポートを構成します。
[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の動的ポートを構成することができます、[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]です。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] WCF ベース アダプターでは、用のポートを動的に構成することができます、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]メッセージ コンテキスト プロパティを使用しています。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]、URI、アクション、およびバインドのプロパティを受信メッセージから決定されで指定して可能性があります、**式**図形を次の例で示すようにします。  
  
```  
Request2=Request1;  
Request2(WCF.Action)="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert";  
Request2(WCF.BindingType)="siebelBinding";  
Request2(WCF.UserName)="YourUserName";  
Request2(WCF.Password)="YourPassword";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="siebel://mySiebelServer:1234?SiebelObjectManager=SSEObjMgr&SiebelEnterpriseServer=myEnterpriseServer&Language=enu";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
  
```  
  
> [!NOTE]
>  Wcf-siebel アダプターを使用しているかどうかは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、指定することも、トランスポートの種類として`SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SiebelAdapter"`ここで、 **SiebelAdapter** のWcf-siebelアダプターを追加する名前を指定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
 前の例。  
  
-   Request1 メッセージから Request2 メッセージを作成しています。 どちらのメッセージが操作を使用して生成されるスキーマ、マップ、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]です。  
  
-   送信ポートは、BizTalk オーケストレーションの論理送信ポートの名前です。  
  
 式図形は、BizTalk オーケストレーションの一部です。 オーケストレーションを展開するときに、Wcf-custom 送信ポートも作成されます。  
  
 動的ポートの構成の詳細については、次を参照してください。[動的送信ポートを使用して WCF アダプター コンテキスト プロパティの構成](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)です。
  
## <a name="see-also"></a>参照  
[Siebel アダプターと BizTalk アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)