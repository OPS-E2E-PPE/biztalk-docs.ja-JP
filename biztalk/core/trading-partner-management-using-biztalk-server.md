---
title: 取引先管理の BizTalk Server の使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f31a5e49-ef19-41a3-9cf3-cf85d0685a59
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5a1ac3c072b21633c3b6f6226aa7cce20729077
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279122"
---
# <a name="trading-partner-management-using-biztalk-server"></a>BizTalk Server を使用した取引先管理
## <a name="introduction-to-tpm"></a>TPM の概要
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 取引先管理 (TPM) は、パートナーとそのビジネスに関する情報の管理方法と保存方法の基本的な概念を再構築するものです。 拡張 TPM ソリューションには、フィールドのビジネス エンティティとリレーションシップが反映されます。これにより組織は、取引先とのビジネス パートナーシップをより高度に管理することができます。 TPM ソリューションによる取引パートナーシップの BizTalk 環境でのモデルの詳細については、次を参照してください。[取引先管理ソリューションのビルド ブロック](../core/building-blocks-of-a-trading-partner-management-solution.md)です。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]電子データ交換 (edi) および AS2 データ トランスポートのネイティブ サポートが含まれます。 このサポートにより、企業は、EDI トランザクションの自動交換によって実現される生産性の向上を図りながら EDI ベースのビジネス プロセス管理ソリューションを拡張できます。 BizTalk Server は、EDI および EDIINT/AS2 を使用して、重要なサプライ チェーン ビジネス プロセスに対し、パートナー接続におけるセキュリティ保護と信頼性を高める手段を提供します。  
  
 EDI および AS2 のサポートと組み合わせると、TPM ソリューションで取引先を管理するための堅牢でスケーラブルなソリューションの提供[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 このセクションのトピックおよび以下に示すその他のトピックで、TPM の高レベルな概要と、TPM を使用した取引先管理方法について説明しています。 これらのトピックには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] による EDI および AS2 プロセスの実行方法も説明されています。  
  
## <a name="in-this-section-and-more-good-info"></a>このセクションで詳細な情報

**について、概要、およびチュートリアル**  

-   [取引先管理ソリューションのビルド ブロック](../core/building-blocks-of-a-trading-partner-management-solution.md)  
  
-   [BizTalk Server の EDI 機能](../core/biztalk-server-edi-functionality.md)  
  
-   [BizTalk Server の AS2 機能](../core/biztalk-server-as2-functionality.md)  

- [EDI および AS2 ソリューションのアーキテクチャ](../core/edi-and-as2-solution-architecture.md)

-   [環境を最適化するための構成後の手順](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md) 

- [EDI、AS2、および EDIFACT のチュートリアル](../core/tutorials-and-walkthroughs-for-edi-as2-and-edifact.md)


**EDI および AS2 ソリューションを作成するブレーンストーミング**
- [EDI および AS2 のアイテムを作成します。](../core/managing-edi-and-as2-solutions.md)

- [開発および BizTalk Server EDI ソリューションを構成します。](../core/developing-and-configuring-biztalk-server-edi-solutions.md)

- [開発と BizTalk Server AS2 ソリューションの構成](../core/developing-and-configuring-biztalk-server-as2-solutions.md)

-   [EDI および AS2 の SDK のサンプル)](../core/edi-and-as2-biztalk-server-samples-folder.md)  


 **バインド ファイルの使用**  

- [バインド ファイルを使用して、インポートまたはエクスポート - 新しい BizTalk Server 2016](../core/use-binding-files-to-import-or-export.md)  

-   [EDI AS2 ソリューションのバインドをエクスポートする方法](../core/how-to-export-bindings-for-an-edi-as2-solution.md)  
  
-   [EDI AS2 ソリューションのバインドをインポートする方法](../core/how-to-import-bindings-for-an-edi-as2-solution.md)  
  
-   [バインド ファイルのカスタマイズ](../core/customizing-binding-files.md)  


**監視し、トラブルシューティング**

- [EDI および AS2 ソリューションの監視](../core/monitoring-edi-and-as2-solutions.md)

- [EDI および AS2 ソリューションのトラブルシューティング](../core/troubleshooting-edi-and-as2-solutions.md)
  
-   UI の詳細の表示[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] 
  
-   [EDI および AS2 イベントとエラー](../core/edi-and-as2-events-and-errors.md)
 


  
