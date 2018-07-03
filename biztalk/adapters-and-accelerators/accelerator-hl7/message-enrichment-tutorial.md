---
title: メッセージの強化のチュートリアル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial
- message enrichment tutorial, about the tutorial
- messages, tutorial
- tutorials, message enrichment tutorial
ms.assetid: 4ffb047f-457a-4a80-b7ec-4b61ae16f35f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f60a6cc6bcb98e01489e981a39370215744ab860
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004043"
---
# <a name="message-enrichment-tutorial"></a>メッセージ強化のチュートリアル
このチュートリアルは、Microsoft の使用に関する詳しい手順を示します[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]特定のビジネス問題を解決する: メッセージの強化に関する問題。 メッセージ強化のチュートリアルを追加、または強化する必要がある場合は HL7 に準拠していないことが完了していないメッセージについて説明します。 これは、患者の登録アプリケーションなど、アプリケーションで発生する可能性や、Microsoft からの XML データを含むメッセージを作成する場合に発生することができます[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]します。  
  
 このチュートリアルでは、BTAHL7 でメッセージをキャプチャし、患者記録データベースからなど、不足しているあらゆるデータを提供します。 メッセージを変換し、研究室、保険、または (最小限の下位レイヤー プロトコル) の MLLP アダプターを使用して、従来の基幹業務 (LOB) アプリケーションに送信します。  
  
 このチュートリアルで「ドアベル」登録患者トリガー イベントを SOAP アダプター経由で、ここでは XML 形式のメッセージの場合を送信する Web サービス クライアント (WSClient.exe) アプリケーションを使用する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]BTAHL7 でします。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SOAP メッセージを受信ポート、およびルートの Web サービスとして公開されたオーケストレーションにメッセージを受信します。 XML メッセージには、患者の名と社会保障番号が含まれています。 メッセージを強化し、スキーマ、マップ、および変換を使用して、HL7 形式にメッセージを変換します。 保険、研究室に MLLP アダプターを介して送信を LOB アプリケーションまたはします。  
  
 次の図は、チュートリアルのプロセス フローを示しています。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-msgenrichtutarch.gif "hl7_msgenrichtutarch")  
  
> [!NOTE]
>  このチュートリアルは、Windows Server Standard、Enterprise、Datacenter が必要です。 または、Web Edition および、MLLP を含むカスタム BTAHL7 インストールは、ツールをテストします。 さらに、知っておくべきで[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]での開発[!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]情報と[HL7 アクセラレータと BizTalk ツールの使用について説明します](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)します。  
> 
> [!NOTE]
>  アセンブリを展開解除、送信ポートを停止によってエラーを回避でき、受信前のチュートリアルで使用する場所を無効にします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: アプリケーション プール ID の構成](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-application-pool-identity.md)  
  
-   [手順 2: 新しいプロジェクトの作成](../../adapters-and-accelerators/accelerator-hl7/step-2-create-a-new-project.md)  
  
-   [手順 3: アセンブリへの厳密な名前の割り当て](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md)  
  
-   [手順 4: スキーマの作成](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md)  
  
-   [手順 5: スキーマのプロパティの昇格](../../adapters-and-accelerators/accelerator-hl7/step-5-promote-schema-properties.md)  
  
-   [手順 6: スキーマの検証](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)  
  
-   [手順 7: プロジェクトの署名とビルド](../../adapters-and-accelerators/accelerator-hl7/step-7-sign-and-build-the-projects.md)  
  
-   [手順 8: BizTalk マッパーを使用したマップの作成](../../adapters-and-accelerators/accelerator-hl7/step-8-create-a-map-with-biztalk-mapper.md)  
  
-   [手順 9: マップ プロジェクトの検証とビルド](../../adapters-and-accelerators/accelerator-hl7/step-9-validate-and-build-the-map-project.md)  
  
-   [手順 10: オーケストレーションの作成](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md)  
  
-   [手順 11: オーケストレーション変数の作成](../../adapters-and-accelerators/accelerator-hl7/step-11-create-orchestration-variables.md)  
  
-   [手順 12: オーケストレーション図形の構成](../../adapters-and-accelerators/accelerator-hl7/step-12-configure-orchestration-shapes.md)  
  
-   [手順 13: ポートの作成と構成](../../adapters-and-accelerators/accelerator-hl7/step-13-create-and-configure-ports.md)  
  
-   [手順 14: Web サービスとしてのオーケストレーションの公開](../../adapters-and-accelerators/accelerator-hl7/step-14-publish-the-orchestration-as-a-web-service.md)  
  
-   [手順 15: 送信ポートと受信ポートの構成](../../adapters-and-accelerators/accelerator-hl7/step-15-configure-the-send-and-receive-ports.md)  
  
-   [手順 16: オーケストレーションの開始](../../adapters-and-accelerators/accelerator-hl7/step-16-start-the-orchestration.md)  
  
-   [手順 17: WSClient アプリケーションの作成](../../adapters-and-accelerators/accelerator-hl7/step-17-create-the-wsclient-application.md)  
  
-   [手順 18: 新しいメッセージ強化ソリューションのテスト](../../adapters-and-accelerators/accelerator-hl7/step-18-test-your-new-message-enrichment-solution.md)