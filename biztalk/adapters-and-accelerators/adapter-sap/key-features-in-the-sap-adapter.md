---
title: "SAP アダプターの機能のキー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, deprecated features
- features, technology-related
- adapters, new features
- features, deprecated
- features, metadata-related
- librfc32u.dll
- tRFC server
- features, new
- adapters, new and deprecated features
- queued tRFC client calls
- features, operations-related
- RFC server
ms.assetid: 30e3140c-447f-42ba-a3b0-13ae66e78b0c
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b34a695e34f617f6444b728e92cb544f91448c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="key-features-in-the-sap-adapter"></a>SAP アダプターの主要な機能
このセクションに一覧表示、非推奨の新機能と[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]です。  
  
> [!NOTE]
>  このトピックの内容が以前のバージョンから使用された[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]ヘルプします。  
  
## <a name="features-in-the-sap-adapter"></a>SAP アダプターの機能  
 以前のリリースで導入された機能は、次のとおり、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
### <a name="technology-related-features"></a>テクノロジに関連する機能  
  
|機能|解説|  
|-------------|-------------|  
|使用して、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]と SQL Server Reporting Services (SSRS)。|クライアント プログラムを使用できるようになりました、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SSRS プロジェクトに SAP バックエンドからデータをインポートし、データを使用してレポートを生成します。 使用する方法の詳細について、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]で、SSRS では、次を参照してください。 [SSRS と SAP 用データ プロバイダーを使用して](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssrs.md)です。 SSRS の詳細については、次を参照してください。 [SQL Server Reporting Services](https://msdn.microsoft.com/library/ms159106.aspx)です。|  
|SAP システムで定義されているクエリを呼び出すためのサポート|[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]操作を公開する、EXECQUERY、SAP システムで定義されているクエリを実行するために使用できます。 EXECQUERY 機能を使用する方法の詳細については、[SAP クエリの実行のサポートを参照してください。

](https://msdn.microsoft.com/library/dd788118.aspx).|  
|使用するためのサポート、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]と Microsoft Office SharePoint Server (MOSS) |アダプターを使用して、MOSS ポータルに SAP システムからデータを表示することができます。 詳細については、次を参照してください[SAP アダプターを使用して、SharePoint と](../../adapters-and-accelerators/adapter-sap/use-the-sap-adapter-with-sharepoint.md)。 |。  
  
### <a name="metadata-related-features"></a>メタデータに関連する機能  
  
|機能|解説|  
|-------------|-------------|  
|**DataTypesBehavior**プロパティのバインド|[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]付属[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]複合バインディング プロパティを提供**DataTypesBehavior**、SAP システム内の特殊な値が発生したときに、アダプターの動作を制御するアダプターのクライアントを有効にします。 このバインディングのプロパティに関する詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。|  
  
### <a name="operations-related-features"></a>操作に関連する機能  
  
|機能|解説|  
|-------------|-------------|  
|RFC で必要な外部のプログラムを起動するためのサポート|[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインド プロパティを提供**RfcAllowStartProgram** 、必要な特定の RFC で場合は、外部プログラムを呼び出すために RFC クライアント ライブラリを有効にするを設定することができます。 このバインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。|  
|1 回の呼び出しで複数の Idoc を送信するためのサポート|SAP アダプターは、1 つのアダプターの呼び出しで同じ種類の複数の Idoc を送信できるようになりました。|  
  
### <a name="other-features"></a>その他の機能  
  
|機能|解説|  
|-------------|-------------|  
|アダプターを使用する新しい方法[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]|[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で BizTalk WCF カスタム ポートまたは WCF SAP ポートとして使用できます。 使用する場合、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF カスタム ポートを経由は WCF カスタム ポートを追加する必要はありません、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールに、WCF カスタム ポートが追加されるため、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]既定では管理コンソールです。 ただし、使用する場合、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF SAP ポートを介してへの WCF SAP アダプターを追加する必要があります最初、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 詳細については、次を参照してください。 [SAP アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)です。|  
  
## <a name="deprecated-features-in-the-sap-adapter"></a>SAP アダプターの非推奨機能  
 次のセクションでは、アダプターの以前のバージョンをサポートされていましたが、これは、現在のバージョンのサポートされていません機能の一覧、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
### <a name="enablebusinessobjects-binding-property-deprecated"></a>非推奨 EnableBusinessObjects バインディング プロパティ  
 このバインドのプロパティは推奨されなくなりました[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]付属[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 このバインドのプロパティが使用中にメタデータを生成するときに、BAPI ノードを表示するかどうかを決定に使用された[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]です。  
  
## <a name="see-also"></a>参照  
 [MySAP Business Suite の BizTalk アダプターを理解します。](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)