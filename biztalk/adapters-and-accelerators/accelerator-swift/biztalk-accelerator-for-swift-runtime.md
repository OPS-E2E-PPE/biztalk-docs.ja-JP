---
title: BizTalk Accelerator for SWIFT ランタイム |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 946bd3fa788f3d133e509c905e86178a94d0c5e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378888"
---
# <a name="biztalk-accelerator-for-swift-runtime"></a>BizTalk Accelerator for SWIFT ランタイム
Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] 2 つの形式で機能を提供します。 開発資料とランタイム コンポーネントです。 開発の資料には、XSD スキーマ、検証ルールとポリシー、およびサンプル コードが含まれます。 ランタイム コンポーネントには、カスタムの SWIFT 逆アセンブラー、カスタムの SWIFT アセンブラー、Message Repair および New Submission のオーケストレーション (MrsrRepair.odx)、および FIN Response Reconciliation のオーケストレーション (FrrMain.odx) が含まれます。 Message Repair and New Submission の詳細については、次を参照してください。 [Message Repair and New Submission](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md)します。 FRR の詳細については、次を参照してください。 [FIN Response Reconciliation](../../adapters-and-accelerators/accelerator-swift/fin-response-reconciliation.md)します。  

 次の図の高レベルのシステム アーキテクチャを示しています。[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]します。  

 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-end-to-end.gif "A4SWIFTSystemArchitecture_End_to_End")  

 次の図は、A4SWIFT とバックエンド アプリケーション間のメッセージのフローし、A4SWIFT を使用する方法を示しています。 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] Message Repair and New Submission 用 MRSR でフォームのサイト。  

 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswithbackendapplications.gif "A4SWIFTSystemArchitecture_InterfaceswithBackEndApplications")  

 次の図は、A4SWIFT と SWIFT ネットワークの間のメッセージのフロー方法を示しています。  

 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswiththeswiftnetwork.gif "A4SWIFTSystemArchitecture_InterfaceswiththeSWIFTNetwork")  

 A4SWIFT のすべてのコンポーネントは、BizTalk Server アプリケーションのコンポーネントの垂直方向に固有の実装として定義できます。 垂直方向に固有の上に BizTalk アプリケーションの開発を加速する機能を開発およびランタイムを提供する BizTalk アクセラレータ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 そのため、A4SWIFT のコンポーネントをすべて (開発またはランタイム) は、規定を遵守し、BizTalk Server アプリケーションのアーキテクチャに適合します。 A4SWIFT にランタイム コンポーネントのインストール、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]カスタム コンポーネントとランタイム。 マテリアルのコンパイルおよび展開、A4SWIFT の開発後、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SWIFT メッセージングとオートメーションの機能を提供するランタイムを使用しています。  

 次の図は、BizTalk Server の高度なアプリケーション トポロジを示します。  

 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro1.gif "FSA_Intro1")  

 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーション モデルは、メッセージ ボックス データベースとに、およびメッセージ ボックス データベースからのメッセージ フローを制御するパブリッシャーとサブスクライバーのパターンを使用します。 BizTalk のアーキテクチャとアプリケーションの設計に関する詳細については、BizTalk Server のヘルプを参照してください。  

 A4SWIFT のアプリケーション モデルが継承、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーション モデルへの追加と SWIFT 固有のコンポーネントで SWIFT に関連するソリューションを容易に[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 次の一覧には、これら A4SWIFT 固有のコンポーネントについて説明します。  

- **ランタイム コンポーネントです。** 受信パイプライン、送信パイプライン、Message Repair and New Submission のオーケストレーション、および FIN Response Reconciliation のオーケストレーションで SWIFT アセンブラーで SWIFT 逆アセンブラーです。  

- **開発のマテリアルです。** SWIFT スキーマ、ルール、オーケストレーション、および顧客向けのソリューションに含まれており、展開されている実行の実行時にサンプル プロジェクト。  

  このセクションでは、A4SWIFT ランタイムの詳細について説明します。  

  このセクションには、次のトピックが含まれています。  

- [SWIFT 逆アセンブラー](../../adapters-and-accelerators/accelerator-swift/swift-disassembler.md)  

- [SWIFT アセンブラー](../../adapters-and-accelerators/accelerator-swift/swift-assembler.md)  

- [受信場所と InfoPath フォームを介したメッセージの送信](../../adapters-and-accelerators/accelerator-swift/submitting-messages-through-receive-locations-and-infopath-forms.md)  

- [メッセージ検証エンジン](../../adapters-and-accelerators/accelerator-swift/message-validation-engine.md)
