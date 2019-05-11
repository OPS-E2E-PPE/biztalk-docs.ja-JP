---
title: 医療保険システム統合の必要性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- health care organizations
ms.assetid: e747b633-c898-473c-be7d-ba00bfdbdc21
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afc078ff4d72dffc9717464934a46c1a9b314f98
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286532"
---
# <a name="the-need-for-health-care-systems-integration"></a>医療保険システム統合の必要性
Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]医療プロバイダーをソリューションで、アプリケーションの統合とビジネス プロセス オートメーションのニーズが提供されます。 このトピックで説明、ビジネス上の課題の一部、医療の組織が直面してどのように Microsoft を組み込んだシステム[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]これら組織がこれらの課題に対応できます。 サンプル ビジネス シナリオを示す一般的なシナリオを見ても[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]します。  
  
## <a name="health-care-business-challenge"></a>医療のビジネスの課題

医療の組織は、多くのも、接続されている部分を持つ複雑なビジネス エンティティです。 病院では、これらの部門は受付、labs、看護ステーション、医師にとっては、課金を含めることができます。 これらの部門のすべてを生成し、データを使用します。 データは、患者、請求、プロシージャ、および投薬に関する情報を含めることができます。 多くの場合、組織では、多くの部門間でこのデータが必要です。 医療の組織の共通の課題は、部門間のデータ交換を効率的に処理する方法を示します。  
  
 次の図は、複雑なシステムを作成する、相互通信が方法の多くの部門を示しています。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-no-btahl7.gif "hl7_no_btahl7")  
  
 これらの部門の多くは、個別のビジネス プロセスもあります。 部門の担当者で作成、実装、および独自のプロセスを保持する可能性があります。 これらのプロセスが他の部門に変わる可能性がありますが、担当者が設計いないに、その他の部門に注意してください。  
  
 医療の多くの組織にとって問題では、組織のすべての範囲の間でプロセスをより細かく制御を得るです。  
  
## <a name="health-care-business-solution"></a>医療のビジネス ソリューション

テクノロジは、ビジネス プロセスおよびデータに関連する問題の解決に役立ちます。 情報技術 (IT) システム、医療の組織から統合から切断されている、互換性のないプロセスでは、その内部の操作を変換できます標準化されました。  
  
### <a name="integration"></a>統合  
 医療の組織の別々 の部分のプロセスに本質的に互換性がない場合でも、それらを統合できます。 (図のように、医療保険のビジネスの課題 (このトピックでは) のハブとスポークの配置に基づくいずれかに次の図に示すようにポイント ツー ポイント接続によって分類システムを変換するテクノロジと共に、それらを関連付けることができます。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-yes-btahl7.gif "hl7_yes_btahl7")  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] 別の部門または、エンティティごとに接続して、プロセスをバインドするメカニズムを提供することでそれらの相違点を解決するには、この統合を実現します。 また、ビジネス プロセスは、最小限のユーザー操作を実行できるようにデータの交換を自動化します。  
  
### <a name="standardization"></a>標準化  
 ビジネス プロセスを接続した後、プロセスは、データを交換できます。 ただし、別個の部門で保持されるデータが別の形式で転送すると、別のデータ プロトコル、データの交換によってシステムの設計とカスタマイズにかなりの労力が必要です。 形式と、データ交換に使用されるプロトコルを標準化の各部門を接続している場合は、このプロセスの効率が大幅に強化できます。  
  
 これは、HL7 組織が行ったです。 フラット ファイル スキーマの形式で作成した医療のデータの一般的な形式です。 それぞれの作業は非常に成功すると、大規模な病院の割合が高いが、標準を採用してポイントにされました。  
  
### <a name="solutions-specific-to-the-health-care-industry"></a>医療業界に固有のソリューション  
 統合の IT システムと標準化されたデータ交換が用意基盤の正常性をより効率的なケア プロセス。 医療システムの本当に効果的な IT ソリューションは、1 つは、その業界での問題について説明し、機能、機能、および医療の組織のニーズに対処するためのツールを提供します。  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] そのソリューションを提供します。 インストールする[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]の上に[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]します。 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] スキーマとの連携が作成され、HL7 組織によって管理されます。 さらに、機能や医療アプリケーション用にデザインされたツールを提供します。 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] データの検証、受信確認をバッチ処理できるように、監査とログ記録は、医療の組織で必要です。  
  
## <a name="next"></a>Next
読み取り、[サンプル ビジネス シナリオ](../../adapters-and-accelerators/accelerator-hl7/sample-business-scenario.md)します。
