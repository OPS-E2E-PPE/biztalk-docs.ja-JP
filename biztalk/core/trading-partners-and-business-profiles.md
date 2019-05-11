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
ms.openlocfilehash: 194388ddbd4fe2b39987e11a45e4bf87d71dfcff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313357"
---
# <a name="trading-partners-and-business-profiles"></a>取引先パートナーとビジネス プロファイル

## <a name="overview"></a>概要
取引関係に参加している各組織は、取引先パートナーです。 取引先パートナーは、「取引先パーティ」または「パーティ」とも呼ばれますがルート レベルで、取引先パートナー ソリューションのベースになります。 取引先パートナーでは、ビジネスの継続的なリレーションシップ内で 2 つ以上の参加要素の 1 つです。 取引先パートナーには、送信したりする、またはその他のすべてのパートナーからメッセージを受信する 1 つのビジネス エンティティです。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポートの関連付けとパーティの id を検証するために使用する証明書の送信など、TPM ソリューションは、モデル化して、取引の情報を格納するために使用できます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 受信したメッセージと送信されるメッセージを処理するためには、この情報を使用します。 ホーム組織を含めて、取引関係に参加している各組織 (を実行しているローカル ホスト組織、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト)、取引先パートナーとして表されます。
  
 ![パーティを取引先](../core/media/tradingparties.gif "TradingParties")  
  
 たとえば、2 つの組織があるとします。Fabrikam および Contoso。 Fabrikam を使用して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 使用する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Fabrikam が自身と Contoso 用の 2 つの取引を作成する必要があります Contoso でインターチェンジのすべてのビジネス データを管理します場合。 パーティを作成するときに名前、パートナーなどの特定の詳細を提供します。  
 
## <a name="business-profiles"></a>ビジネス プロファイル

取引先のビジネス プロファイル、ビジネス プロファイルとも呼ばれますが、組織のビジネス面です。 各事業部が別の組織内の別のビジネス部門と取引のある組織では、TPM ソリューションでビジネス プロファイルとして表されます。 ビジネス部門、ビジネス ユニット、またはビジネス システムに固有の B2B メッセージング パラメーターを定義するすべてのプロパティは、そのビジネス プロファイルにキャプチャされます。 たとえば、Fabrikam に 2 つの事業部があるとします。「支払い」と"Shipping"。 Contoso には、事業部門「請求書」。 使用して、fabrikam [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、それを作成する必要があります。  
  
- ビジネス プロファイルが 2 つ支払い"と"Fabrikam を取引先のパートナーでは、出荷に対して 1 つずつです。  
  
- 取引先パートナー、Contoso の下の請求書の 1 つのビジネス プロファイル。  
  
  次の図は、TPM ソリューションで、パートナーとビジネス プロファイルを管理する方法を示しています。  
  
  ![パートナーのビジネス プロファイルを取引先](../core/media/businessprofile.gif "BusinessProfile")  
  
  事業部には、ビジネス プロファイルを定義した後、メッセージ エンコード形式とビジネス部門が B2B メッセージの送受信中に準拠しているトランスポートを定義できます。 これらのビジネス プロファイル間の通信パターンは、後ほど[プロトコル設定](../core/protocol-settings.md)します。  
  
### <a name="why-do-i-need-business-profiles"></a>ビジネス プロファイルを必要な理由  
 ビジネス プロファイルを有効にする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]より優れたユーザーが TPM ソリューションに各自のビジネス モデルを表します。 エンタープライズで複数の事業部で個別に表すことができます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 さらに、このモデルにより、ユーザーが他のプロファイルとビジネス プロファイルの特性を定義する各ビジネス プロファイルのプロパティを設定します。 たとえば、米国とヨーロッパでの除算のある企業を検討してください。 米国の事業部は EDI メッセージだけで X12 標準、ヨーロッパの事業部は EDI メッセージだけで EDIFACT 標準中。 パーティを作成すると、企業はプロファイル レベル、および同時メッセージのプロパティを使用して、パートナー レベルで既に設定されているプロパティの右側を設定できます。 ビジネス プロファイル、なし、企業は、すべての事業部用の取引先パートナーを作成し、それらの取引先間で多数のプロパティをレプリケートする必要があります。  
  
 一意の id を使用してビジネス プロファイルを使用したビジネス id を関連付けることもできます。 これらのビジネス id が、標準機関によって提供されることができますか、または相互に合意したことができますにビジネス id。  
  
> [!IMPORTANT]
>  同じ組織内の 2 つの事業部は、内で取引する場合に、必要があります作成する必要が、個別の取引です。 同じパートナーの下の 2 つのプロファイルは、取引先は異なるパートナー間のリレーションシップが管理されている相互 transact ことはできません。  
  
## <a name="learn-next"></a>次に説明します。

[プロトコル設定](../core/protocol-settings.md)  
[取引先契約](../core/trading-partner-agreement.md)  
[まとめ。取引先パートナー管理ソリューションを定義します。](../core/putting-it-all-together-defining-a-trading-partner-management-solution.md)
 
## <a name="see-also"></a>参照  
 [取引先管理ソリューションの構成要素](../core/building-blocks-of-a-trading-partner-management-solution.md)