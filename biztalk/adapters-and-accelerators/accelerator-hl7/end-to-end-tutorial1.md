---
title: エンド ツー エンド Tutorial1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.endtoendtutorial
helpviewer_keywords:
- end-to-end tutorial, about the tutorial
- end-to-end tutorial
- tutorials, end-to-end tutorial
ms.assetid: 90625edc-70a0-42c9-a2fb-8eeb5465d766
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 264a6eee008b9b327185c931ad4e5ac60cdc995a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000739"
---
# <a name="end-to-end-tutorial"></a>エンド ツー エンドのチュートリアル
このチュートリアルには、Microsoft の使用方法を説明する詳細な手順が含まれています。[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]サブスクライバーとパブリッシャーのシナリオでビジネス プロセスを容易にします。  
  
> [!IMPORTANT]
>  このチュートリアルを使用するには、BTAHL7 をインストールするときに、テスト ツールをインストールする必要があります。 コード型の BTAHL7 をインストールする一般的なインストールを実行した場合、カスタム インストールを実行テスト ツールを正常に動作するには、このチュートリアルの順序でインストールし、する必要があります。 **カスタム セットアップ**、BTAHL7 カスタム インストールの選択画面**MLLP テスト ツール**から、**アダプター**フォルダー、および選択**テスト インスタンス**から、**成果物**フォルダー。 詳細については、[BizTalk Accelerator for HL7 のインストール](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)を参照してください。  
  
## <a name="declarative-scenario"></a>宣言型のシナリオ  
 このチュートリアルでは、パブリッシュ/サブスクライブまたは宣言型のシナリオを使用します。 宣言型のシナリオでは、ビジネスのフローは次の図に示されている似ています。 次の図は、番号付きリストでは、ワークフローについて説明します。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-e2e-wkflw.gif "hl7_e2e_wkflw")  
宣言型のシナリオでは、ビジネスのフローを示す図  
  
1.  ワークフローは、特定のサブスクライバーにメッセージを送信するなど、入学放電と転送のシステムは、パブリッシャーを開始します。 ワークフローの発行元は、"Tutorial_ADTSystem"と、メッセージが呼び出された"**ADT ^ A103**"。  
  
2.  メッセージは、さらに受信、処理、検証、書式を再設定、およびサブスクライバーにメッセージをルーティングし BTAHL7 インターフェイス エンジンにルーティングされます。  
  
3.  このシナリオでは、サブスクライバーとは、病院情報システム (Tutorial_HISystem) および薬剤システム (Tutorial_RXSystem) です。 このシナリオでは、ファイルと MLLP アダプターの種類を使用します。 パブリッシャーは、サブスクライバーを意識する必要はありませんし、BTAHL7 適切に受信確認を送信、パブリッシャーに、メッセージの処理後にします。  
  
4.  パブリッシャーは、送信、ADT ^ A03 メッセージ (Tutorial_1WayReceivePort) 一方向の MLLP アダプターを経由します。  
  
5.  このメッセージの送信先には、BTAHL7 インターフェイス エンジンがあるため、受信メッセージには送信元メッセージが含まれています (MSH3 Tutorial_ADTSystem =) と送信先のメッセージ (MSH5 BTAHL7InterfaceEngine =)。  
  
6.  BTAHL7 では、メッセージを適切に検証した後、受信確認 (ACK) を生成し、ファイル アダプター経由 Tutorial_ADTSystem に受信確認を送信します。  
  
7.  Tutorial_HISystem システムと Tutorial_RXSystem システムは、BTAHL7 インターフェイス エンジンによって受信された ADT メッセージをサブスクライブします。  
  
8.  変換は、使用して、それぞれのフィールドの値を指定するときに発生します。、 **MSH マップ**BTAHL7 構成エクスプ ローラー タブ。  
  
     パーティ Tutorial_RXSystem の MSH3 がなどで指定された BTHL7 =、 **MSH マップ**タブ。したがって、サブスクライバーで受信したメッセージでは、MSH3 フィールドの値として"BTAHL7"があります。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [インストールのテスト](../../adapters-and-accelerators/accelerator-hl7/testing-your-installation.md)  
  
-   [チュートリアルを使用する準備](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md)  
  
-   [手順 1: ヘッダーと確認スキーマの作成と展開](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-header-and-acknowledgment-schemas.md)  
  
-   [手順 2: v2.3.1 の一般的なスキーマを作成します。](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md)  
  
-   [手順 3: トリガー イベント (メッセージ) プロジェクトの作成と展開](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project.md)  
  
-   [手順 4: MLLP Adapter を使用して ADT System から ADT^A03 メッセージを受け入れるための受信ポートの作成](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md)  
  
-   [手順 5: ファイル アダプターを使用して ADT System に受診確認を配信する送信ポートの作成](../../adapters-and-accelerators/accelerator-hl7/step-5-create-send-port-to-deliver-acknowledgments-to-adt-system-using-file.md)  
  
-   [手順 6: ファイル アダプターを使用して RX System に ADT^A03 メッセージを配信する送信ポートの作成](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md)  
  
-   [手順 7: MLLP アダプターを使用して HIS に ADT^A03 メッセージを配信する送信ポートの作成](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md)  
  
-   [手順 8: パーティ情報の構成](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md)  
  
-   [手順 9: BizTalk Server の再起動](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md)  
  
-   [手順 10: エンド ツー エンド シナリオの確認](../../adapters-and-accelerators/accelerator-hl7/step-10-verify-the-end-to-end-scenario.md)

## <a name="see-also"></a>参照
[BizTalk Accelerator for HL7 の概要](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md)