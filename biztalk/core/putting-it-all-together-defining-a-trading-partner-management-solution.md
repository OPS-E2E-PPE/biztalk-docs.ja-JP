---
title: "まとめ: 取引先管理ソリューションを定義する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4219312a-c4b5-45f3-b77b-d5cc4f1a1ca4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea32fba8e9e57d7a0549a680b06e08d5bf8e087f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="putting-it-all-together-defining-a-trading-partner-management-solution"></a>まとめ: 取引先管理ソリューションを定義する
TPM ソリューションの構築で使用するさまざまなコンポーネントについて理解できたので、次に標準的な TPM ソリューションの流れと、さまざまな構成要素の連携について説明します。 ここでは、TPM ソリューションのモデリングのベスト プラクティスも示します。  
  
 TPM ソリューションの作成の標準的な手順は以下のとおりです。  
  
1.  商取引に関係するすべての組織を表すパートナーを作成します。 たとえば、商取引に 2 つの組織が関係する場合は、それぞれについて取引先を作成する必要があります。 取引先を作成する方法の手順については、次を参照してください[全般的なパーティ プロパティを構成する](../core/configuring-general-party-properties.md)または[一般的なパーティ プロパティの構成 (AS2)。](../core/configuring-general-party-properties-as2.md)  
  
2.  組織内の部署ごとに、それを表すプロファイルをパートナー内に作成します。 たとえば、組織に "購買" と "資材" という部署がある場合は、各部署を [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のビジネス プロファイルとして表す必要があります。 また、自分の組織を表すパートナーのビジネス プロファイルだけではなく、取引先のパートナーも作成する必要があります。 ビジネス プロファイルを作成する方法については、次を参照してください。[ビジネス プロファイル プロパティを設定する](../core/configuring-business-profile-properties.md)です。  
  
3.  ビジネス プロファイルごとに、メッセージ エンコードの設定とメッセージ プロトコルの設定を含む B2B プロトコル設定を定義します。 これらの設定では、B2B メッセージのエンコード方法および 2 つのビジネス プロファイル間での伝送方法を定義します。  
  
    > [!NOTE]
    >  この段階では、プロトコル設定の指定は省略できます。 取引先アグリーメントの一部として、プロトコルの設定を直接追加できます。  
  
4.  2 つのビジネス プロファイルがメッセージ交換の間に使用することを合意したエンコードとメッセージ プロトコルを定義する取引先アグリーメント (TPA) を、ビジネス プロファイルの間に作成します。 アグリーメントを作成する方法については、次を参照してください[X12 に固有のアグリーメント プロパティの構成](../core/configuring-x12-specific-agreement-properties.md)、 [EDIFACT に固有のアグリーメントのプロパティを構成する](../core/configuring-edifact-specific-agreement-properties.md)、または[AS2 を構成します。。アグリーメントのプロパティ](../core/configuring-as2-agreement-properties.md)です。  
  
 以上の作業を実行することで、取引先と B2B メッセージを交換するための TPM ソリューションが作成されます。  
  
## <a name="where-do-i-start"></a>開始方法  
 以下に従って開始することができます。  
  
-   X12 固有のチュートリアル「[チュートリアル 2: EDI インターフェイス開発チュートリアル](../core/tutorial-2-edi-interface-developer-tutorial.md)です。  
  
-   AS2 固有のチュートリアル「[チュートリアル 3: AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)です。  
  
-   X12-および EDIFACT に固有のチュートリアル [を開発し、BizTalk Server EDI ソリューションを構成する](../core/developing-and-configuring-biztalk-server-edi-solutions.md)です。  
  
-   AS2 固有のチュートリアル[を開発し、BizTalk Server AS2 ソリューションの構成](../core/developing-and-configuring-biztalk-server-as2-solutions.md)です。  
  
-   パーティ、プロファイル、および X12 と EDIFACT での手順に従ってメッセージのアグリーメントを作成する[EDI プロパティを設定する](../core/configuring-edi-properties.md)です。  
  
-   パーティ、プロファイル、およびメッセージングでの手順に従って、AS2 のアグリーメントを作成する[AS2 プロパティを設定する](../core/configuring-as2-properties.md)です。  
  
## <a name="see-also"></a>参照  
 [取引先管理ソリューションのビルド ブロック](../core/building-blocks-of-a-trading-partner-management-solution.md)