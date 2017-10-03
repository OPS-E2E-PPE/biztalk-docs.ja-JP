---
title: "メッセージの強化チュートリアル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial
- message enrichment tutorial, about the tutorial
- messages, tutorial
- tutorials, message enrichment tutorial
ms.assetid: 4ffb047f-457a-4a80-b7ec-4b61ae16f35f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 532fc0e8a9aeefbc35a892277c68be8d640b5588
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-enrichment-tutorial"></a>メッセージの強化のチュートリアル
このチュートリアルを使用するための手順の説明[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]特定のビジネス問題を解決する: メッセージの強化に関する問題です。 メッセージの強化のチュートリアルでは、する必要がある追加、または強化する場合、HL7 準拠ではありませんやが完了するメッセージについて説明します。 これは、患者登録アプリケーションなど、アプリケーションで発生する可能性やから XML データを含むメッセージを作成する場合に発生することができます[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]です。  
  
 このチュートリアルでは、BTAHL7 でメッセージをキャプチャし、患者のレコードをデータベースからなど、不足しているデータを提供します。 メッセージを変換し、実験、保険、または (最小限の低いレイヤー プロトコル) MLLP アダプターを使用して、レガシ基幹業務 (LOB) アプリケーションに送信します。  
  
 このチュートリアルではイベントを送信する XML 形式のメッセージの場合は、ここでは、「ドアベル」患者の登録トリガー、SOAP アダプターから Web サービス クライアント (WSClient.exe) アプリケーションを使用する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]BTAHL7 でします。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SOAP メッセージを受信ポート、およびルートの Web サービスとして公開されたオーケストレーションにメッセージを受信します。 XML メッセージには、患者の名前と社会保障番号が含まれています。 メッセージが強化され、HL7 形式にメッセージを変換するスキーマ、マップ、および変換を使用します。 研究、保険に MLLP アダプターを介して送信し、または LOB アプリケーションです。  
  
 次の図は、チュートリアルのプロセス フローを示しています。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-msgenrichtutarch.gif "hl7_msgenrichtutarch")  
  
> [!NOTE]
>  このチュートリアルは、Windows Server Standard、Enterprise、Datacenter が必要です。 または、Web Edition、および、MLLP を含むカスタム BTAHL7 インストール ツールをテストします。 さらに、する必要があります慣れて[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で開発[!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]情報および[HL7 アクセラレータと使用可能な BizTalk ツールについて説明](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)です。  
  
> [!NOTE]
>  アセンブリを展開解除、送信ポートを停止によってエラーを回避することができ、受信前のチュートリアルで使用される場所を無効にします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: アプリケーション プール Id を構成します。](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-application-pool-identity.md)  
  
-   [手順 2: 新しいプロジェクトを作成します。](../../adapters-and-accelerators/accelerator-hl7/step-2-create-a-new-project.md)  
  
-   [手順 3: アセンブリに厳密な名前を割り当てます](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md)  
  
-   [手順 4: スキーマを作成します。](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md)  
  
-   [手順 5: スキーマのプロパティを昇格させる](../../adapters-and-accelerators/accelerator-hl7/step-5-promote-schema-properties.md)  
  
-   [手順 6: スキーマを検証します。](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)  
  
-   [手順 7: 署名し、プロジェクトのビルド](../../adapters-and-accelerators/accelerator-hl7/step-7-sign-and-build-the-projects.md)  
  
-   [手順 8: BizTalk マッパーでマップを作成します。](../../adapters-and-accelerators/accelerator-hl7/step-8-create-a-map-with-biztalk-mapper.md)  
  
-   [手順 9: 検証プロジェクトをビルド マップ](../../adapters-and-accelerators/accelerator-hl7/step-9-validate-and-build-the-map-project.md)  
  
-   [手順 10: オーケストレーションを作成します。](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md)  
  
-   [手順 11: オーケストレーション変数を作成します。](../../adapters-and-accelerators/accelerator-hl7/step-11-create-orchestration-variables.md)  
  
-   [手順 12: オーケストレーション図形を構成します。](../../adapters-and-accelerators/accelerator-hl7/step-12-configure-orchestration-shapes.md)  
  
-   [手順 13: を作成し、ポートを構成します。](../../adapters-and-accelerators/accelerator-hl7/step-13-create-and-configure-ports.md)  
  
-   [手順 14: Web サービスとしてのオーケストレーションを公開します。](../../adapters-and-accelerators/accelerator-hl7/step-14-publish-the-orchestration-as-a-web-service.md)  
  
-   [手順 15 は、送信を構成し、受信ポート](../../adapters-and-accelerators/accelerator-hl7/step-15-configure-the-send-and-receive-ports.md)  
  
-   [手順 16.、オーケストレーションを開始します。](../../adapters-and-accelerators/accelerator-hl7/step-16-start-the-orchestration.md)  
  
-   [手順 17: クライアント アプリケーションを作成します。](../../adapters-and-accelerators/accelerator-hl7/step-17-create-the-wsclient-application.md)  
  
-   [手順 18: 新しいメッセージの強化ソリューションをテストします。](../../adapters-and-accelerators/accelerator-hl7/step-18-test-your-new-message-enrichment-solution.md)