---
title: Oracle データベース アダプターの動的ポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- dynamic ports, configuring
ms.assetid: c4f67707-76a0-4d72-913f-03219b412e2a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b6a0dc67f764ad8e87d1a2c0d6965f5f5b437c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999059"
---
# <a name="configure-dynamic-ports-in-the-oracle-database-adapter"></a>Oracle データベース アダプターの動的ポートを構成します。
[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の動的ポートを構成することができます、[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF ベース アダプターでは、用のポートを動的に構成することができます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]メッセージ コンテキスト プロパティを使用しています。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、URI、アクション、およびバインド、受信メッセージのプロパティから決定されで指定された可能性があります、**式**図形、次の例に示すようにします。  
  
```  
Request2=Request1;  
Request2(WCF.Action)="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select";  
Request2(WCF.BindingType)="oracleDBBinding";  
Request2(WCF.UserName)="SCOTT";  
Request2(WCF.Password)="TIGER";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="oracledb://adapdoc/";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
  
```  
  
> [!NOTE]
>  Wcf-oracledb アダプターを使用しているかどうかは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、トランスポートの種類としても指定できます`SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="OracleDatabaseAdapter"`ここで、 **OracleDatabaseAdapter**の Wcf-oracledb アダプターを追加する名前を指定します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
 上記の例では、  
  
- Request1 メッセージから Request2 メッセージを作成しています。 どちらのメッセージが操作を使用して生成されるスキーマ、マップ、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]します。  
  
- 送信ポートは、BizTalk オーケストレーションの論理送信ポートの名前です。  
  
  **式**図形は、BizTalk オーケストレーションの一部です。 オーケストレーションを展開するときに、wcf-custom 送信ポートも作成されます。  
  
  動的ポートの構成の詳細については、[動的送信ポートを使用して WCF アダプター コンテキスト プロパティの構成](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)を参照してください。
  
## <a name="see-also"></a>参照  
[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)