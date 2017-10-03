---
title: "競合回避モジュールの Web サービス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 236cff15-562a-41d5-bfdc-d250186fb616
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 916181431686ca729c0751d9362570afb7dddeee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-resolver-web-service"></a>競合回避モジュールの Web サービス
競合回避モジュールの Web サービスは、ゲートウェイ ESB 動的解決メカニズムに。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このサービスの 2 つのバージョンが含まれています: ASP.NET (ASMX) バージョンと Windows Communication Foundation (WCF) バージョン。 サービス名は**ESB です。ResolverServices**と**ESB です。ResolverServices.WCF**、それぞれ、およびサービスは、次のメソッドを公開します。  
  
-   **解決します。** このメソッドは、1 つのパラメーターとして受け取り、**文字列**登録されている競合回避モジュールのなどの標準的な接続文字列に準拠した要求の競合回避モジュールの接続文字列を格納している**静的、BRE、UDDI、XPATH、行程、行程静的、BRI、**または**LDAP です。**  
  
-   **ResolveMessage です。** このメソッドが最初のパラメーターとして登録されている競合回避モジュールのなどの標準的な接続文字列に準拠した要求の競合回避モジュールの接続文字列を含む文字列を受け取る**静的、BRE、UDDI、XPATH、行程、行程静的、BRI、**または**LDAP**です。 さらに、このメソッドと省略可能な 2 番目のパラメーターを受け取ります、**文字列**の解決を支援するために、サービスが省略可能なファクトとして使用できる XML メッセージ ドキュメントを含むですたとえば、BRE の競合回避モジュールがメッセージ本文を必要があります。ファクトをカプセル化します。  
  
 競合回避モジュールと ResolverDictionary クラスとその使用方法の詳細については、次を参照してください。[ヘルパー クラスを使用して](../esb-toolkit/using-the-helper-classes.md)です。  
  
## <a name="resolver-connection-strings"></a>競合回避モジュールの接続文字列  
 ESB 動的解決メカニズムでは、前に実行する解決策の種類を示すモニカーで接続文字列を使用します。 サポートされているモニカーを含める**静的、BRE、UDDI、UDDI3、XPATH、行程、行程静的、BRI、**と**LDAP**です。 次の接続文字列の例を示しています、 **UDDI**モニカー。  
  
```  
  
//UDDI  
UDDI:\\serverUrl=http://localhost/uddi;serviceName=PurchaseOrder;serviceProvider=Microsoft.Practices.ESB  
```  
  
 動的解決メカニズムによってサポートされている接続文字列の種類については、次を参照してください。[動的解決の使用とルーティング](../esb-toolkit/using-dynamic-resolution-and-routing.md)です。  
  
> [!NOTE]
>  いずれかの Windows 統合セキュリティを使用して、組み込みの NETWORK SERVICE アカウントで実行するこのサービスを構成する必要があります。  
>   
>  既定では、競合回避モジュールの Web サービスは (SSL) クライアントによってアクセスされたときに要求するように構成されていません。 クライアント アクセス用の SSL が要求されるようにサービスを構成し、インターネット インフォメーション サービス (IIS) Web サービスのホスト コンピューターとネットワーク レベルの IPSec および適切なファイル レベルのアクセスを使用して、BizTalk Server 間の接続を保護する必要があります。リスト (ACL) のアクセス許可を制御します。 セキュリティ上のリスクを避けるためには、信頼できるサブシステムの境界の外側には、このサービスを公開することは推奨されません。