---
title: 健康保険システム統合の必要性 |Microsoft ドキュメント
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
ms.openlocfilehash: b7674cff1c9c1e787c0ab9638e0abad407adafea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207234"
---
# <a name="the-need-for-health-care-systems-integration"></a>健康保険システム統合の必要性
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]のアプリケーション統合とビジネス プロセス オートメーション ニーズを満たすソリューションと医療プロバイダーを提供します。 このトピックの説明、ビジネスの課題医療組織が直面する、およびどのように組み込んだシステム[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]これらの組織がそれらの課題に役立ちます。 サンプル ビジネス シナリオを示す一般的なシナリオを見ても[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]します。  
  
## <a name="health-care-business-challenge"></a>医療ビジネスの課題

医療組織は、多くの異なりますが、接続されている部分を持つ複雑なビジネス エンティティです。 病院ではのこれらの部門は、受付、ラボ、看護ステーション、医師、および請求を含めることができます。 これらの部門のすべてを生成し、データを使用します。 データは、患者、請求、プロシージャ、および薬に関する情報を含めることができます。 多くの場合、組織では、さまざまな部門間でこのデータが必要です。 医療組織用の一般的な課題は、部門間でデータの交換を効率的に処理する方法を示します。  
  
 次の図は、複雑なシステムを作成するが、相互通信が方法多くの部門を示します。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-no-btahl7.gif "hl7_no_btahl7")  
  
 これらの部門の多くは、個別のビジネス プロセスのことにもします。 部門の担当者は、作成、実装されると、および独自のプロセスを維持が可能性があります。 これらのプロセスが他の部門では、影響を受けますは、担当者可能性がありますが設計いませんに点の他の部門にします。  
  
 医療多くの組織にとって問題は、組織のすべての範囲の間でプロセスをより細かく制御を獲得します。  
  
## <a name="health-care-business-solution"></a>医療ビジネス ソリューション

テクノロジには、ビジネス プロセスとデータに関連するビジネスの課題を解決するのに役立ちます。 情報技術 (IT) システム、医療の組織から統合、切断されている、互換性のないプロセスから内部の運用を変換できますを標準化されたものです。  
  
### <a name="integration"></a>統合  
 医療組織の別々 の部分のプロセスが本質的に互換性がない場合でも、それらを統合できます。 (図のように、医療保険のビジネスの課題 (」を参照) を 1 つのハブとスポークの配置では、次の図に示すようにポイント ツー ポイント接続によって特徴付けられた、システムを変換するテクノロジと共にそれらを結合することができます。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-yes-btahl7.gif "hl7_yes_btahl7")  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]各部門別、またはエンティティに接続して、プロセスをバインドするメカニズムを提供することでそれらの相違点を解決するには、この統合を実現します。 また、ビジネス プロセスは、ユーザーが介入の最小限に抑えて実行できるようにデータ交換を自動化します。  
  
### <a name="standardization"></a>標準化  
 ビジネス プロセスを接続した後、プロセスは、データを交換できます。 ただし、別の形式では、データを別個の部門で管理システムのトランスポートにもさまざまなデータ プロトコル場合は、データ交換はシステムの設計とカスタマイズに大幅な労力を要求できます。 形式と、データ交換に使用されるプロトコルを標準化の各部門接続されている場合は、このプロセスの効率性が大幅に強化できます。  
  
 これは、HL7 組織が行ったです。 それが、フラット ファイル スキーマの形式で、医療のデータの一般的な形式を作成します。 それぞれの作業が非常に成功すると、大規模な病院の割合が高いが、標準を採用していること、ポイントにされました。  
  
### <a name="solutions-specific-to-the-health-care-industry"></a>医療業界に固有のソリューション  
 IT システムを統合し、標準化されたデータ交換が用意基盤のより効率的なヘルスの注意プロセスです。 医療システムに本当に効果的な IT ソリューションは、その業界では、この問題に焦点を当てており、機能、機能、および医療組織のニーズに対応するツールを提供する 1 つです。  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]そのソリューションを提供します。 インストールする[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]の上に[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]です。 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]スキーマとの連携が作成され、HL7 組織が維持されます。 さらに、機能や医療アプリケーション向けに設計されたツールを提供します。 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]データの検証、受信確認をバッチ処理できるように、監査とログ記録は、医療組織で必要です。  
  
## <a name="next"></a>Next
読み取り、[サンプル ビジネス シナリオ](../../adapters-and-accelerators/accelerator-hl7/sample-business-scenario.md)です。
