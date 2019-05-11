---
title: 主要な SAP アダプターの機能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c227fa80a7152ade8bcc6f745d6c5fb2f760715
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373276"
---
# <a name="key-features-in-the-sap-adapter"></a>SAP アダプターの主な機能
このセクションでは、新しいと非推奨の機能を示します[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]します。  
  
> [!NOTE]
>  このトピックでは、以前のバージョンから使用されています[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]ヘルプします。  
  
## <a name="features-in-the-sap-adapter"></a>SAP アダプターの機能  
 以前のリリースで導入された機能を次に、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
### <a name="technology-related-features"></a>テクノロジ関連の機能  
  
|                                                            機能                                                             |                                                                                                                                                                                                                                                                                              解説                                                                                                                                                                                                                                                                                               |
|--------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 使用して、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]と SQL Server Reporting Services (SSRS)。 | クライアント プログラムが使用できるようになりました、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SSRS プロジェクトに SAP バックエンドからデータをインポートし、データからレポートを生成します。 使用方法の詳細については、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] ssrs では、次を参照してください。 [for SAP を SSRS と一緒にデータ プロバイダーを使用して](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssrs.md)します。 SSRS の詳細については、次を参照してください。 [SQL Server Reporting Services](https://msdn.microsoft.com/library/ms159106.aspx)します。 |
|                                     SAP システムで定義されているクエリを呼び出すためのサポート                                      |                                                                                                                                                           [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]する操作では、SAP システムで定義されているクエリを実行するために使用するには、EXECQUERY を公開します。 EXECQUERY 機能を使用する方法の詳細については、[SAP クエリの実行のサポートを参照してください。                                                                                                                                                            |

](https://msdn.microsoft.com/library/dd788118.aspx).|  
|使用するためのサポート、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]と Microsoft Office SharePoint Server (MOSS) |アダプターを使用して、MOSS ポータル上に SAP システムからデータを表示することができます。 詳細については、次を参照してください[SharePoint で SAP アダプターを使用する](../../adapters-and-accelerators/adapter-sap/use-the-sap-adapter-with-sharepoint.md)。 |。  
  
### <a name="metadata-related-features"></a>メタデータに関連する機能  
  
|                機能                 |                                                                                                                                                                                                                                                                                                   解説                                                                                                                                                                                                                                                                                                    |
|----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **DataTypesBehavior**プロパティのバインド | [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]付属[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]複合バインディングのプロパティを提供します。 **DataTypesBehavior**、特殊な値が SAP システムで発生した場合に、アダプターの動作を制御するアダプターのクライアントを有効にします。 このバインドのプロパティに関する詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。 |
  
### <a name="operations-related-features"></a>操作に関連の機能  
  
|                          機能                          |                                                                                                                                                                                                                                                 解説                                                                                                                                                                                                                                                  |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RFC で必要な外部のプログラムを呼び出すためのサポート | [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインドのプロパティを提供します。 **RfcAllowStartProgram**特定 RFC に必要な場合は、外部のプログラムを呼び出す RFC クライアント ライブラリを有効に設定できます。 このバインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。 |
|    1 回の呼び出しで複数の Idoc を送信するためのサポート    |                                                                                                                                                                                                      SAP アダプターは、アダプターが 1 つの呼び出しで同じ種類の複数の Idoc を送信できるようになりました。                                                                                                                                                                                                      |
  
### <a name="other-features"></a>その他の機能  
  
|                                                        機能                                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                解説                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|-----------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| アダプターを使用する新しい方法 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] | [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Biztalk WCF カスタム ポートまたは WCF SAP ポートとして使用できます。 使用する場合、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF カスタム ポートには WCF カスタム ポートを追加する必要はありません、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールに、WCF カスタム ポートが追加されるため、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]既定では、管理コンソール。 ただし、使用する場合、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF-SAP ポートを通じて、WCF-SAP アダプターを追加する必要があります最初、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 詳細については、次を参照してください。 [SAP アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)します。 |
  
## <a name="deprecated-features-in-the-sap-adapter"></a>SAP アダプターの非推奨の機能  
 次のセクションでは、アダプターの以前のバージョンがサポートされていましたの現在のバージョンでサポートされていません、機能の一覧、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
### <a name="enablebusinessobjects-binding-property-deprecated"></a>非推奨とされます EnableBusinessObjects バインディング プロパティ  
 このバインドのプロパティで非推奨とされた[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]付属[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 このバインドのプロパティは、BAPI ノードが使用中にメタデータを生成するときに表示されるかどうかを決定に使用された[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for mySAP Business Suite について](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)