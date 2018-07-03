---
title: 取引先パートナーとビジネス プロファイル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cbeac421-c319-4a60-a188-28f7268888fc
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 639b6057c6c0c7e139737b8fc78ce780baae719a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024008"
---
# <a name="trading-partners-and-business-profiles"></a>取引先パートナーとビジネス プロファイル

## <a name="overview"></a>概要
取引関係のある個々の組織が取引先です。 取引先は、"取引先パーティ" または "パーティ" とも呼ばれ、取引先ソリューションのルート レベルにあり、その基盤を形成します。 取引先は、現在進行中の取引関係にある 2 つ以上の参加者のうちの 1 つです。 また、他の取引先との間でメッセージを送受信できる単一のビジネス エンティティです。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポートの関連付けとパーティの id を検証するために使用する証明書の送信など、TPM ソリューションは、モデル化して、取引の情報を格納するために使用できます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 受信したメッセージと送信されるメッセージを処理するためには、この情報を使用します。 ホーム組織を含めて、取引関係に参加している各組織 (を実行しているローカル ホスト組織、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト)、取引先パートナーとして表されます。
  
 ![パーティを取引先](../core/media/tradingparties.gif "TradingParties")  
  
 たとえば、2 つの組織: Fabrikam と Contoso です。 Fabrikam を使用して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 Contoso との間で交わされるすべてのビジネス データを管理するために [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用するには、Fabrikam は自社と Contoso について 1 つずつ、合わせて 2 つの取引先を作成する必要があります。 パーティを作成するときに名前、パートナーなどの特定の詳細を提供します。  
 
## <a name="business-profiles"></a>ビジネス プロファイル

取引先のビジネス プロファイル (ビジネス プロファイルとも呼ばれます) は、組織のビジネスの概要を示すものです。 TPM ソリューションでは、組織内の各事業部が異なる組織の異なる事業部と取引を行う場合、1 つのビジネス プロファイルとして示されます。 ビジネス プロファイルには、事業部、事業単位、または事業システムに固有の B2B メッセージング パラメーターを定義するすべての特性が取り込まれます。 たとえば、Fabrikam が 2 つの事業部:「支払い」と"Shipping"。 Contoso には、事業部門「請求書」。 使用して、fabrikam [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、それを作成する必要があります。  
  
- 取引先 Fabrikam の元で、"支払い" と "出荷 " に各 1 つずつ、2 つのビジネス プロファイルを作成します。  
  
- 取引先 Contoso の元で、"請求書" の 1 つのビジネス プロファイルを作成します。  
  
  次の図に、TPM ソリューションでのパートナーとビジネス プロファイルの管理方法を示します。  
  
  ![パートナーのビジネス プロファイルを取引先](../core/media/businessprofile.gif "BusinessProfile")  
  
  ビジネス プロファイルが定義されると、各事業部は、B2B メッセージの送受信中にその事業部が使用するメッセージ エンコード形式とトランスポートを定義することができます。 これらのビジネス プロファイル間の通信パターンは、後ほど[プロトコル設定](../core/protocol-settings.md)します。  
  
### <a name="why-do-i-need-business-profiles"></a>ビジネス プロファイルが必要な理由  
 ビジネス プロファイルにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のユーザーは、TPM ソリューションに各自のビジネス モデルを効果的に示すことができます。 企業に複数の事業部がある場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で個別に表すことができます。 さらに重要なのは、このモデルにより各ビジネス プロファイルに特性を設定し、他のビジネス プロファイル間との取引の方法を定義できることです。 たとえば、ある企業の事業部が米国とヨーロッパにあるとします。 米国の事業部は EDI メッセージだけで X12 標準、ヨーロッパの事業部は EDI メッセージだけで EDIFACT 標準中。 パーティを作成すると、企業はプロファイル レベル、および同時メッセージのプロパティを使用して、パートナー レベルで既に設定されているプロパティの右側を設定できます。 ビジネス プロファイル、なし、企業は、すべての事業部用の取引先パートナーを作成し、それらの取引先間で多数のプロパティをレプリケートする必要があります。  
  
 また、ビジネス プロファイルにビジネス ID を関連付けることで、一意の ID を作成できます。 これらのビジネス ID は、標準機関によって提供されたものか、相互の同意に基づくビジネス ID のどちらかになります。  
  
> [!IMPORTANT]
>  同じ組織内の 2 つの事業部が組織内で取引する場合には、個別の取引先として作成する必要があります。 2 つのプロファイルが同じパートナーに属している場合、相互に取引はできません。取引先関係は異なるパートナー間で管理されるためです。  
  
## <a name="learn-next"></a>次に説明します。

[プロトコル設定](../core/protocol-settings.md)  
[取引先契約](../core/trading-partner-agreement.md)  
[まとめ: 取引先管理ソリューションを定義する](../core/putting-it-all-together-defining-a-trading-partner-management-solution.md)
 
## <a name="see-also"></a>参照  
 [取引先管理ソリューションの構成要素](../core/building-blocks-of-a-trading-partner-management-solution.md)