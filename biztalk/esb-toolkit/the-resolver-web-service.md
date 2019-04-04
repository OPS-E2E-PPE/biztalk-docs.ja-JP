---
title: リゾルバー Web サービス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 236cff15-562a-41d5-bfdc-d250186fb616
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cd153a8ceeba983c71854d02854e37ed046e1bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987531"
---
# <a name="the-resolver-web-service"></a>リゾルバー Web サービス
リゾルバー Web サービスは、ESB の動的な解決メカニズムにゲートウェイです。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] このサービスの 2 つのバージョンが含まれています。 ASP.NET (ASMX) バージョンと Windows Communication Foundation (WCF) のバージョン。 サービス名は**ESB します。ResolverServices**と**ESB します。ResolverServices.WCF**、それぞれ、サービスは、次のメソッドを公開します。  
  
- **解決します。** このメソッドは、1 つのパラメーターとして、**文字列**競合回避モジュールの登録などの標準的な接続文字列に準拠した、要求に競合回避モジュールの接続文字列を格納している**静的、BRE、UDDI、XPATH、日程表、日程静的、BRI、** または**LDAP です。**  
  
- **ResolveMessage します。** このメソッドは最初のパラメーターとして、競合回避モジュールの登録などの標準的な接続文字列に準拠した要求に競合回避モジュールの接続文字列を含む文字列**静的、BRE、UDDI、XPATH、日程、静的、日程 BRI、** または**LDAP**します。 さらに、メソッドとして省略可能な 2 番目のパラメーターを受け取ります、**文字列**の解決を支援するために省略可能な事実として、サービスが使用できる XML メッセージ ドキュメントを格納しているたとえば、BRE の競合回避モジュールがメッセージ本文を必要があります。ファクトをカプセル化します。  
  
  競合回避モジュールと ResolverDictionary クラスとその用途の詳細については、[ヘルパー クラスを使用して](../esb-toolkit/using-the-helper-classes.md)を参照してください。  
  
## <a name="resolver-connection-strings"></a>競合回避モジュールの接続文字列  
 ESB 動的解決の機構では、前に実行する解決の種類を示すモニカーの接続文字列を使用します。 サポートされているモニカーが含まれます**静的、BRE、UDDI、UDDI3、XPATH、日程表、日程静的、BRI、** と**LDAP**します。 次の接続文字列の例を示しています、 **UDDI**モニカー。  
  
```  
  
//UDDI  
UDDI:\\serverUrl=http://localhost/uddi;serviceName=PurchaseOrder;serviceProvider=Microsoft.Practices.ESB  
```  
  
 動的解決の機構によってサポートされている接続文字列の種類については、[を使用して動的な解決とルーティング](../esb-toolkit/using-dynamic-resolution-and-routing.md)を参照してください。  
  
> [!NOTE]
>  いずれかの Windows 統合セキュリティを使用して、組み込みの NETWORK SERVICE アカウントで実行するこのサービスを構成する必要があります。  
>   
>  既定では、競合回避モジュールの Web サービスはセキュリティで保護の Sockets Layer (SSL) クライアントがアクセスするときに要求するように構成されていません。 クライアント アクセス用の SSL が要求されるように、サービスを構成し、インターネット インフォメーション サービス (IIS) Web サービスのホスト コンピューターとネットワーク レベルの IPSec と適切なファイル レベルのアクセスを使用して、BizTalk Server 間の接続を保護する必要があります。リスト (ACL) のアクセス許可を制御します。 セキュリティ上のリスクを回避するために、信頼できるサブシステムの境界の外側には、このサービスを公開することは推奨されません。