---
title: デザイン時ツール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d60cf2a64863a842bb974fcce2d4217f9b8105f7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997443"
---
# <a name="design-time-tools"></a>デザイン時ツール
Microsoft BizTalk Accelerator for HL7 開発者 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) BizTalk Server に組み込まれているデザイン時ツールのセットを使用します。 これらのツールが統合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。 詳細については[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ツール、MicrosoftBizTalk Server のヘルプを参照してください。  
  
## <a name="biztalk-editor"></a>BizTalk エディター  
 HL7 の XSD スキーマを管理するのにには、BizTalk エディターを使用します。 ソリューション開発用 (XSD ファイル) として、次のスキーマがサポートされているテンプレートを使用できます。  
  
-   HL7: 2.1 (37 イベントが含まれています)  
  
-   HL7: 2.2 (56 イベントが含まれています)  
  
-   HL7: 2.3 (182 イベントが含まれています)  
  
-   (189 イベントが含まれています): HL7 2.3.1  
  
-   HL7: 2.4 (288 イベントが含まれています)  
  
-   HL7: 2.5 (約 390 スキーマが含まれています)  
  
-   : HL7 2. XML (V2.3.1 および 2.4 の約 450 スキーマが含まれています)  
  
## <a name="biztalk-mapper"></a>BizTalk マッパー  
 BizTalk マッパーを使用して、データ変換を定義するマップの作成やカスタマイズを行います。 BizTalk マッパーを使用して、受信と送信の両方の変換をマップする[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージの種類。  
  
## <a name="biztalk-orchestration-designer"></a>BizTalk オーケストレーション デザイナ  
 BizTalk オーケストレーション デザイナを使用して、ビジネス プロセスの設計および実装を行います。  
  
## <a name="biztalk-pipeline-designer"></a>BizTalk パイプライン デザイナ  
 BizTalk パイプライン デザイナを使用して、パイプラインを定義して処理手順のリンクを作成して構成します。 パイプラインは処理をステージに分割し、各カテゴリの作業を実行するシーケンスを決定します。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 受信し、送信パイプラインがサポートされているすべての HL7 バージョンの両方を提供します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] カスタム HL7 パーサーと逆アセンブラーまたはアセンブラー コンポーネントを持つパイプライン テンプレートを提供します。  
  
## <a name="biztalk-adapter-framework"></a>BizTalk アダプタ フレームワーク  
 BizTalk アダプタ フレームワークとエンドポイント アダプタを使用して、パートナーおよびアプリケーションを統合します。  
  
## <a name="visual-studio-starter-project"></a>Visual Studio のスタート プロジェクト  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 含まれています、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]スタート プロジェクトは、クイック スタート、HL7 ソリューションの実装を使用することができます。 スタート プロジェクトには、次のプロジェクトが含まれます。  
  
- **空**[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]**プロジェクト**します。     すべてのスキーマは含まれません。  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] **V2XCommon プロジェクト**します。 ヘッダーと受信確認のスキーマが含まれています。  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] **V21Common プロジェクト**します。 HL7 バージョン 2.1 の一般的なスキーマが含まれています。  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] **V22Common プロジェクト**します。 HL7 2.2 の一般的なスキーマが含まれています。  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] **V23Common プロジェクト**します。 HL7 バージョン 2.3 の一般的なスキーマが含まれています。  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] **V231Common プロジェクト**します。 HL7 version 2.3.1 の一般的なスキーマが含まれています。  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] **V24Common プロジェクト**します。 HL7 バージョン 2.4 については、一般的なスキーマが含まれています。  
  
- BTAHL7**V25Common プロジェクト**します。 HL7 バージョン 2.5 の一般的なスキーマが含まれています。  
  
## <a name="see-also"></a>参照  
 [ツールと機能](../../adapters-and-accelerators/accelerator-hl7/tools-and-features.md)   
 [分析ツール](../../adapters-and-accelerators/accelerator-hl7/analysis-tools2.md)