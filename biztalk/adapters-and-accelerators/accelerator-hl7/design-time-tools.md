---
title: "デザイン時ツール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Adapter Framework
- BTAHL7, tools
- Starter Project
- Pipeline Designer
- BizTalk Editor
- Visual Studio Starter Project
- BizTalk Mapper
- design-time tools
- Orchestration Designer
ms.assetid: 709bd782-d2ad-49be-ba33-e957eba2a0cc
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e22272fd04dd3bf2461e4b9fef104657cf007fbb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="design-time-tools"></a>デザイン時ツール
作業する開発者[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 一連のデザイン時のツールに組み込まれているに使用されている[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]です。 これらのツールが組み込ま[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 詳細については[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ツールを参照してください[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]ヘルプします。  
  
## <a name="biztalk-editor"></a>BizTalk エディター  
 HL7 XSD スキーマを管理するのにには、BizTalk エディターを使用します。 ソリューションの開発の (XSD ファイル) として、次のサポートされるスキーマ テンプレートを使用できます。  
  
-   HL7: 2.1 (37 イベントを含む)  
  
-   HL7: 2.2 (56 イベントを含む)  
  
-   HL7: 2.3 (182 イベントを含む)  
  
-   HL7: 2.3.1 (189 イベントを含む)  
  
-   HL7: 2.4 (288 イベントを含む)  
  
-   HL7: 2.5 (約 390 スキーマが含まれています)  
  
-   HL7: 2. XML (V2.3.1 および 2.4 は、約 450 スキーマが含まれています)  
  
## <a name="biztalk-mapper"></a>BizTalk マッパー  
 BizTalk マッパーを使用して、データ変換を定義するマップの作成やカスタマイズを行います。 BizTalk マッパーを使用して、着信および発信の変換をマップする[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージの種類。  
  
## <a name="biztalk-orchestration-designer"></a>BizTalk オーケストレーション デザイナ  
 BizTalk オーケストレーション デザイナを使用して、ビジネス プロセスの設計および実装を行います。  
  
## <a name="biztalk-pipeline-designer"></a>BizTalk パイプライン デザイナ  
 BizTalk パイプライン デザイナを使用するには、パイプラインを定義して処理手順のリンクを作成および構成します。 パイプラインは、段階的に処理を分割し、各カテゴリの作業を実行するシーケンスを決定します。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]受信ポートおよび送信パイプラインのすべてのサポートされている HL7 バージョンを提供します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]カスタム HL7 パーサーと逆アセンブラーまたはアセンブラー コンポーネントを持つパイプライン テンプレートを提供します。  
  
## <a name="biztalk-adapter-framework"></a>BizTalk アダプタ フレームワーク  
 BizTalk アダプタ フレームワークとエンドポイント アダプタを使用して、パートナーおよびアプリケーションを統合します。  
  
## <a name="visual-studio-starter-project"></a>Visual Studio のスタート プロジェクト  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]含まれています、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]スタート プロジェクトは、HL7 ソリューションの実装のクイック スタートを使用することができます。 スターター プロジェクトには、次のプロジェクトが含まれます。  
  
-   **空**[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]**プロジェクト**です。     すべてのスキーマは含まれません。  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]**V2XCommon プロジェクト**です。 ヘッダーと受信確認のスキーマが含まれます。  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]**V21Common プロジェクト**です。 HL7 バージョン 2.1 の一般的なスキーマが含まれます。  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]**V22Common プロジェクト**です。 HL7 バージョン 2.2 の一般的なスキーマが含まれます。  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]**V23Common プロジェクト**です。 HL7 バージョン 2.3 の一般的なスキーマが含まれます。  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]**V231Common プロジェクト**です。 HL7 version 2.3.1 の一般的なスキーマが含まれます。  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]**V24Common プロジェクト**です。 HL7 バージョン 2.4 についての一般的なスキーマが含まれます。  
  
-   BTAHL7**V25Common プロジェクト**です。 HL7 version 2.5 の一般的なスキーマが含まれます。  
  
## <a name="see-also"></a>参照  
 [ツールおよび機能](../../adapters-and-accelerators/accelerator-hl7/tools-and-features.md)   
 [分析ツール](../../adapters-and-accelerators/accelerator-hl7/analysis-tools2.md)