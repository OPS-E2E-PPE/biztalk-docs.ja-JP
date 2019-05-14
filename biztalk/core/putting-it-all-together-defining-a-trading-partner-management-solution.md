---
title: まとめ。取引先を定義するパートナーの管理ソリューション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4219312a-c4b5-45f3-b77b-d5cc4f1a1ca4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3b56ba4f5bf6918f9a2499135c25ad7526a90c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398334"
---
# <a name="putting-it-all-together-defining-a-trading-partner-management-solution"></a>まとめ。取引先パートナー管理ソリューションを定義します。
TPM ソリューションの構築で使用するさまざまなコンポーネントについて理解できたので、次に標準的な TPM ソリューションの流れと、さまざまな構成要素の連携について説明します。 ここでは、TPM ソリューションのモデリングのベスト プラクティスも示します。  
  
 TPM ソリューションの作成の標準的な手順は以下のとおりです。  
  
1. 商取引に関係するすべての組織を表すパートナーを作成します。 たとえば、商取引に 2 つの組織が関係する場合は、それぞれについて取引先を作成する必要があります。 取引先パートナーを作成する方法の詳細については、次を参照してください[全般的なパーティ プロパティを構成する](../core/configuring-general-party-properties.md)または[構成の全般的なパーティ プロパティ (AS2)。](../core/configuring-general-party-properties-as2.md)  
  
2. 組織内の部署ごとに、それを表すプロファイルをパートナー内に作成します。 たとえば、組織に "購買" と "資材" という部署がある場合は、各部署を [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のビジネス プロファイルとして表す必要があります。 また、自分の組織を表すパートナーのビジネス プロファイルだけではなく、取引先のパートナーも作成する必要があります。 ビジネス プロファイルを作成する方法の詳細については、次を参照してください。[ビジネス プロファイル プロパティを設定する](../core/configuring-business-profile-properties.md)します。  
  
3. ビジネス プロファイルごとに、メッセージ エンコードの設定とメッセージ プロトコルの設定を含む B2B プロトコル設定を定義します。 これらの設定では、B2B メッセージのエンコード方法および 2 つのビジネス プロファイル間での伝送方法を定義します。  
  
   > [!NOTE]
   >  この段階では、プロトコル設定の指定は省略できます。 取引先アグリーメントの一部として、プロトコルの設定を直接追加できます。  
  
4. 2 つのビジネス プロファイルがメッセージ交換の間に使用することを合意したエンコードとメッセージ プロトコルを定義する取引先アグリーメント (TPA) を、ビジネス プロファイルの間に作成します。 アグリーメントを作成する方法の詳細については、次を参照してください[X12 固有のアグリーメント プロパティの構成](../core/configuring-x12-specific-agreement-properties.md)、 [EDIFACT に固有のアグリーメントのプロパティを構成する](../core/configuring-edifact-specific-agreement-properties.md)、または[AS2 を構成します。アグリーメントのプロパティ](../core/configuring-as2-agreement-properties.md)します。  
  
   以上の作業を実行することで、取引先と B2B メッセージを交換するための TPM ソリューションが作成されます。  
  
## <a name="where-do-i-start"></a>開始方法  
 以下に従って開始することができます。  
  
-   X12 固有のチュートリアルは、[チュートリアル 2。EDI インターフェイス開発チュートリアル](../core/tutorial-2-edi-interface-developer-tutorial.md)します。  
  
-   AS2 固有のチュートリアルは、[チュートリアル 3。AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)します。  
  
-   X12-および EDIFACT のチュートリアル (ウォークスルー) 特定[を開発し、BizTalk Server EDI ソリューションの構成](../core/developing-and-configuring-biztalk-server-edi-solutions.md)します。  
  
-   チュートリアル (ウォークスルー) は、AS2 固有[を開発し、BizTalk Server AS2 ソリューションの構成](../core/developing-and-configuring-biztalk-server-as2-solutions.md)します。  
  
-   パーティ、プロファイル、および X12 と EDIFACT での手順に従って、メッセージのアグリーメントを作成する[EDI プロパティを設定する](../core/configuring-edi-properties.md)します。  
  
-   パーティ、プロファイル、およびメッセージングでの手順に従って、as2 アグリーメントを作成する[AS2 プロパティを設定する](../core/configuring-as2-properties.md)します。  
  
## <a name="see-also"></a>参照  
 [取引先管理ソリューションの構成要素](../core/building-blocks-of-a-trading-partner-management-solution.md)