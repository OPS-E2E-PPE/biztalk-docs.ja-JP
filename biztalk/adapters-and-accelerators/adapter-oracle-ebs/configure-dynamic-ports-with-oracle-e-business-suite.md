---
title: "Oracle E-business Suite での動的ポートの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75a150ea-d957-4a37-81cf-c043a0a7d5cb
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b02dc0cd4a4cf1d031acaf6d5a0e1c905ee225b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-dynamic-ports-with-oracle-e-business-suite"></a>Oracle E-business Suite で動的ポートを構成します。
[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の動的ポートを構成することができます、[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]です。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] WCF ベース アダプターでは、用のポートを動的に構成することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]メッセージ コンテキスト プロパティを使用しています。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、URI、アクション、およびバインドのプロパティを受信メッセージから決定されで指定して可能性があります、**式**図形を次の例で示すようにします。  
  
```  
Request2=Request1;  
Request2(WCF.Action)="InterfaceTables/Insert/OFA/FA/FA_BOOKS";  
Request2(WCF.BindingType)="oracleEBSBinding";  
Request2(WCF.UserName)="myuser";  
Request2(WCF.Password)="mypass";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="oracleebs://ebs_instance";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
```  
  
> [!NOTE]
>  Wcf-oracleebs アダプターを使用しているかどうかは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、指定することも、トランスポートの種類として`SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="OracleEBSAdapter"`ここで、 **OracleEBSAdapter**で Wcf-oracleebs アダプターを追加する名前を指定します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
 この例では、  
  
-   Request1 メッセージから Request2 メッセージを作成しています。 両方のメッセージが操作を使用して生成されるスキーマ、マップ、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
-   送信ポートは、BizTalk オーケストレーションの論理送信ポートの名前です。  
  
 **式**図形は、BizTalk オーケストレーションの一部です。 オーケストレーションを展開すると、Wcf-custom 送信ポートも作成されます。  
  
 動的ポートを構成する方法の詳細については、次を参照してください。[動的送信ポートを使用して WCF アダプター コンテキスト プロパティの構成](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)です。
  
## <a name="see-also"></a>参照  
[Oracle E-business Suite アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)