---
title: Siebel アダプターの機能のキー |Microsoft ドキュメント
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
ms.openlocfilehash: 295ff8b13358109a5d4737fb5f9325b3c9caa0f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222130"
---
# <a name="key-features-in-the-siebel-adapter"></a>Siebel アダプターの主要な機能
このセクションでは、の新機能を示します[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]です。  
  
> [!NOTE]
>  このトピックの内容が以前のバージョンから使用された[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]ヘルプします。  
  
## <a name="new-features-in-the-siebel-adapter"></a>Siebel アダプターの新機能  
 このリリースで導入された新機能は、次のとおり、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
### <a name="technology-related-features"></a>テクノロジに関連する機能  
  
|機能|解説|  
|-------------|-------------|  
|使用するためのサポート、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]と Microsoft Office SharePoint Server (MOSS)|アダプターを使用すると、MOSS ポータルに Siebel システムからデータを表示します。 詳細については、次を参照してください。[の Microsoft Office SharePoint Server と Siebel アダプターを使用して](https://msdn.microsoft.com/library/dd788017.aspx)です。|  
  
### <a name="operations-related-features"></a>操作に関連する機能  
  
|機能|解説|  
|-------------|-------------|  
|ビジネス コンポーネントに関連付ける操作のサポート|アダプターのクライアントには、親の検索式を指定することによってレコードと子レコードを関連付けることができます。 これは、複数値を持つグループ (MVG) フィールドでビジネス コンポーネントに対してのみ適用されます。 検索式が親と子の両方のビジネス コンポーネントの 1 つのレコードをフィルターする必要がありますに注意してください。|  
|ビジネス コンポーネントに関連付け解除操作のサポート|アダプターのクライアントには、親の検索式を指定することによってレコードと子レコードを切り離すこともできます。 これは、複数値を持つグループ (MVG) フィールドでビジネス コンポーネントに対してのみ適用されます。 検索式が親と子の両方のビジネス コンポーネントの 1 つのレコードをフィルターする必要がありますに注意してください。|  
|複数値リンク クエリのサポート|アダプターのクライアントは、親レコードとフィールドに複数の名前を指定して、親レコードに関連付けられている子レコードを照会できます。 これは、複数値を持つグループ (MVG) フィールドでビジネス コンポーネントに対してのみ適用されます。|  
  
### <a name="other-features"></a>その他の機能  
  
|機能|解説|  
|-------------|-------------|  
|アダプターを使用する新しい方法[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]|[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]で BizTalk WCF カスタム ポートまたは Wcf-siebel ポートとして使用できます。 使用する場合、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] WCF カスタム ポートを経由は WCF カスタム ポートを追加する必要はありません、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールに、WCF カスタム ポートが追加されるため、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]既定では管理コンソールです。 ただし、使用する場合、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Wcf-siebel ポートを介して、Wcf-siebel アダプターを追加する必要があります最初、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 詳細については、次を参照してください。 [Siebel アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)です。|  
  
## <a name="see-also"></a>参照  
 [Siebel eBusiness Applications の BizTalk アダプターを理解します。](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)