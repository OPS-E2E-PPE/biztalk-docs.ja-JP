---
title: SQL アダプターで動的ポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c98b66ed-0bf7-4b24-9d16-9792d033b818
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c4f9cba33b8e26287fa7be424c0376a60333bf7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369954"
---
# <a name="configure-dynamic-ports-in-the-sql-adapter"></a>SQL アダプターで動的ポートを構成します。
[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の動的ポートを構成することができます、[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]します。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF ベース アダプターでは、用のポートを動的に構成することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]メッセージ コンテキスト プロパティを使用しています。  

## <a name="use-an-expression-shape"></a>式図形を使用します。  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、URI、アクション、およびバインド、受信メッセージのプロパティから決定されで指定された可能性があります、**式**図形、次の例に示すようにします。  
  
```  
Request2=Request1;  
Request2(WCF.Action)="TableOp/Insert/dbo/CustomerTable";  
Request2(WCF.BindingType)="sqlBinding";  
Request2(WCF.UserName)="myuser";  
Request2(WCF.Password)="mypass";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="mssql://sql_server/my_instance/my_database";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
  
```  
  
> [!NOTE]
>  WCF-SQL アダプターを使用しているかどうか[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、トランスポートの種類としても指定できます`SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SQLAdapter"`ここで、 **SQLAdapter**の WCF-SQL アダプターを追加する名前を指定します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
 前の例では、  
  
- Request1 メッセージから Request2 メッセージを作成しています。 両方のメッセージが操作を使用して生成されるスキーマ、マップ、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。  
  
- 送信ポートは、BizTalk オーケストレーションの論理送信ポートの名前です。  
  
  **式**図形は、BizTalk オーケストレーションの一部です。 オーケストレーションを展開すると、Wcf-custom 送信ポートも作成します。  
  
  動的ポートを構成する方法の詳細については、次を参照してください。[動的送信ポートを使用して WCF アダプター コンテキスト プロパティの構成](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)します。
  
## <a name="see-also"></a>参照  
[SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)