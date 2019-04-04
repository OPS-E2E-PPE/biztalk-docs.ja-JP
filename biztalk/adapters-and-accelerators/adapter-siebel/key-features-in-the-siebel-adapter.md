---
title: キーの Siebel アダプターの機能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- features, performance-related
- adapter features, new
- features, technology-related
- features, metadata-related
- adapter features, operations-related
- adapter features, performance-related
- features, new
- features, operations-related
- adapter features, metadata-related
ms.assetid: 4612c9ab-810e-4c69-9168-a25c58682e71
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4896256555ea6b721d917c992c9c41fd3737f101
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018329"
---
# <a name="key-features-in-the-siebel-adapter"></a>Siebel アダプターの主要な機能
このセクションでは、新機能を示します[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]します。  
  
> [!NOTE]
>  このトピックでは、以前のバージョンから使用されています[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]ヘルプします。  
  
## <a name="new-features-in-the-siebel-adapter"></a>Siebel アダプターの新機能  
 このリリースで導入された新機能を次に、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
### <a name="technology-related-features"></a>テクノロジ関連の機能  
  
|                                                                    機能                                                                     |                                                                                                               解説                                                                                                               |
|------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 使用するためのサポート、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]と Microsoft Office SharePoint Server (MOSS) | アダプターを使用すると、MOSS ポータルには、Siebel システムからデータを表示します。 詳細については、[Siebel アダプターを使用して、Microsoft Office SharePoint Server と](https://msdn.microsoft.com/library/dd788017.aspx)を参照してください。 |
  
### <a name="operations-related-features"></a>操作に関連の機能  
  
|機能|解説|  
|-------------|-------------|  
|ビジネス コンポーネントに関連付ける操作のサポート|アダプター クライアントには、親の検索式を指定してレコードと子レコードを関連付けることができます。 これは、複数値を持つグループ (MVG) フィールドでビジネス コンポーネントにのみ適用できます。 検索式が、親と子ビジネス コンポーネントの 1 つのレコードをフィルターする必要がありますに注意してください。|  
|ビジネス コンポーネントに対する関連付け解除操作のサポート|アダプター クライアントには、親の検索式を指定してレコードと子レコードを切り離すこともできます。 これは、複数値を持つグループ (MVG) フィールドでビジネス コンポーネントにのみ適用できます。 検索式が、親と子ビジネス コンポーネントの 1 つのレコードをフィルターする必要がありますに注意してください。|  
|複数値リンク クエリのサポート|アダプター クライアントは、親レコードと複数値フィールドの名前を指定することで、親レコードに関連付けられている子レコードを照会できます。 これは、複数値を持つグループ (MVG) フィールドでビジネス コンポーネントにのみ適用できます。|  
  
### <a name="other-features"></a>その他の機能  
  
|                                                        機能                                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  解説                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|-----------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| アダプターを使用する新しい方法 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] | [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Biztalk WCF カスタム ポートまたは Wcf-siebel ポートとして使用できます。 使用する場合、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] WCF カスタム ポートには WCF カスタム ポートを追加する必要はありません、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールに、WCF カスタム ポートが追加されるため、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]既定では、管理コンソール。 ただし、使用する場合、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Wcf-siebel ポートを経由する Wcf-siebel アダプターを最初に追加する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 詳細については、[Siebel アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)を参照してください。 |
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Siebel eBusiness Applications について](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)