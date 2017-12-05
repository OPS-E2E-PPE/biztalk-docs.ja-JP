---
title: "BizTalk Accelerator for SWIFT ランタイム |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- runtime, architecture
- developing, components
- architecture, topology
- messages, message flow diagram
- runtime, components
- SWIFT runtime
- architecture, runtime architecture
- SWIFT network
- A4SWIFT, network
- topology
ms.assetid: c0f59760-7d7d-4b22-a7dc-54e563971d4a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 340cb27daf29e08ad63f20168680c6596650ca0d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="biztalk-accelerator-for-swift-runtime"></a>BizTalk Accelerator for SWIFT のランタイム
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] 2 つのフォームの機能を提供します。 開発材料とランタイム コンポーネント。 開発の資料には、XSD スキーマ、検証規則とポリシー、およびサンプル コードが含まれます。 ランタイム コンポーネントには、カスタム SWIFT 逆アセンブラー、カスタムの SWIFT アセンブラー、Message Repair および New Submission オーケストレーション (MrsrRepair.odx)、および FIN 対応調整オーケストレーション (FrrMain.odx) が含まれます。 Message Repair and New Submission の詳細については、次を参照してください。 [Message Repair and New Submission](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md)です。 FRR の詳細については、次を参照してください。 [FIN 対応調整](../../adapters-and-accelerators/accelerator-swift/fin-response-reconciliation.md)です。  
  
 次の図の高レベルのシステム アーキテクチャ[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]です。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-end-to-end.gif "A4SWIFTSystemArchitecture_End_to_End")  
  
 次の図は、A4SWIFT とバック エンドのアプリケーション間のメッセージのフローおよび A4SWIFT を使用する方法を示しています。 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] Message Repair and New Submission のサイトのフォーム MRSR にします。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswithbackendapplications.gif "A4SWIFTSystemArchitecture_InterfaceswithBackEndApplications")  
  
 次の図は、A4SWIFT と SWIFT ネットワークの間のメッセージのフローを示しています。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswiththeswiftnetwork.gif "A4SWIFTSystemArchitecture_InterfaceswiththeSWIFTNetwork")  
  
 A4SWIFT のすべてのコンポーネントは、BizTalk Server アプリケーション コンポーネントの垂直的市場固有の実装として定義できます。 BizTalk アクセラレータが垂直的市場固有の上に BizTalk アプリケーションの開発を迅速に開発およびランタイムの機能を提供する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 そのため、すべての A4SWIFT コンポーネント (開発または実行時) に従うし、BizTalk Server アプリケーションのアーキテクチャに適合します。 A4SWIFT にランタイム コンポーネントのインストール、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]カスタム コンポーネントとして実行します。 マテリアルのコンパイルおよび展開されると、A4SWIFT 開発後および[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ランタイムを使用してに SWIFT メッセージングとオートメーションの機能を提供します。  
  
 次の図は、BizTalk Server の高度なアプリケーションのトポロジを示します。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro1.gif "FSA_Intro1")  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーション モデルは、メッセージ ボックス データベースと、メッセージ ボックス データベースに出入りするメッセージ フローを制御するパブリッシャーとサブスクライバー パターンを使用します。 BizTalk のアーキテクチャとアプリケーションの設計に関する詳細については、BizTalk Server ヘルプを参照してください。  
  
 A4SWIFT アプリケーション モデルが継承、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーション モデルへの追加とに SWIFT に関連するソリューションを容易に SWIFT 固有のコンポーネント[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 次に、これらの A4SWIFT 固有のコンポーネントを説明します。  
  
-   **ランタイム コンポーネントです。** SWIFT 逆アセンブラー受信パイプライン、送信パイプライン、Message Repair and New Submission のオーケストレーション、および FIN 対応調整オーケストレーションに SWIFT アセンブラーです。  
  
-   **開発資料です。** SWIFT スキーマ、ルール、オーケストレーション、およびサンプル プロジェクトは、顧客のソリューションに含まれ、実行の実行時に配置します。  
  
 このセクションでは、A4SWIFT ランタイムの詳細について説明します。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [SWIFT 逆アセンブラー](../../adapters-and-accelerators/accelerator-swift/swift-disassembler.md)  
  
-   [SWIFT アセンブラー](../../adapters-and-accelerators/accelerator-swift/swift-assembler.md)  
  
-   [受信場所と InfoPath フォームを介したメッセージの送信](../../adapters-and-accelerators/accelerator-swift/submitting-messages-through-receive-locations-and-infopath-forms.md)  
  
-   [メッセージ検証エンジン](../../adapters-and-accelerators/accelerator-swift/message-validation-engine.md)