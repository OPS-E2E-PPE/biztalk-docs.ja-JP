---
title: エンド ツー エンド Tutorial1 |Microsoft ドキュメント
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
ms.openlocfilehash: 90dc31ac286f8ce1e38d9a511eb319828d8ae939
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204818"
---
# <a name="end-to-end-tutorial"></a>エンド ツー エンドのチュートリアル
このチュートリアルには、使用する方法を説明する詳しい手順が含まれています。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]がサブスクライバーとパブリッシャーのシナリオでビジネス プロセスを容易になります。  
  
> [!IMPORTANT]
>  このチュートリアルを使用するのには、BTAHL7 をインストールするときにテスト ツールをインストールする必要があります。 BTAHL7 をインストールする標準的なインストールを実行した場合必要があります、カスタム インストールを実行し、このチュートリアルでは正常に動作する順序でテスト ツールをインストールします。 **カスタム セットアップ**、BTAHL7 カスタム インストールの選択画面**MLLP テスト ツール**から、**アダプター**フォルダー、および選択**テスト インスタンス**から、**成果物**フォルダーです。 詳細については、次を参照してください。 [BizTalk Accelerator 用 HL7 インストール](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)です。  
  
## <a name="declarative-scenario"></a>宣言型のシナリオ  
 このチュートリアルでは、公開/定期受信または宣言のシナリオを使用します。 宣言型では、ビジネスのフローは次の図に示すようなです。 次の図に、番号付きリストでは、ワークフローについて説明します。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-e2e-wkflw.gif "hl7_e2e_wkflw")  
宣言型のシナリオでは、ビジネスのフローを示す図  
  
1.  ワークフローは、特定のサブスクライバーにメッセージを送信するなど、受付放電と転送システムは、パブリッシャーを開始します。 ワークフローでパブリッシャー"Tutorial_ADTSystem"であり、メッセージが呼び出された"**ADT ^ A103**"。  
  
2.  メッセージは、さらに受信、処理、検証、再フォーマットし、およびサブスクライバーにメッセージをルーティングし BTAHL7 インターフェイス エンジンにルーティングされます。  
  
3.  このシナリオでは、サブスクライバーは、医療施設の情報システム (Tutorial_HISystem) 薬局システム (Tutorial_RXSystem)。 このシナリオでは、ファイルと MLLP の両方の種類のアダプターを使用します。 パブリッシャーは、サブスクライバーに注意する必要はありませんし、BTAHL7 適切に受信確認を送信、パブリッシャーにメッセージを処理した後にします。  
  
4.  パブリッシャーは、送信、ADT ^ A03 メッセージ (Tutorial_1WayReceivePort) 一方向の MLLP アダプターを経由します。  
  
5.  このメッセージの送信先は、BTAHL7 インターフェイス エンジンでは、受信メッセージには送信元メッセージが含まれています (MSH3 Tutorial_ADTSystem を =) と送信先メッセージ (MSH5 = BTAHL7InterfaceEngine)。  
  
6.  BTAHL7 では、メッセージを適切に検証した後、受信確認 (ACK) を生成し、ファイル アダプター経由 Tutorial_ADTSystem に受信確認を送信します。  
  
7.  Tutorial_HISystem システムと Tutorial_RXSystem システムは、BTAHL7 インターフェイス エンジンによって受信された ADT メッセージをサブスクライブします。  
  
8.  使用して、各フィールドの値を指定する場合に、変換、 **MSH マップ**BTAHL7 構成エクスプ ローラー タブ。  
  
     たとえば、パーティ Tutorial_RXSystem が MSH3 = BTHL7 で指定された、 **MSH マップ**タブです。そのため、サブスクライバーによって受信されたメッセージは MSH3 フィールドの値として"BTAHL7"があります。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [インストールのテスト](../../adapters-and-accelerators/accelerator-hl7/testing-your-installation.md)  
  
-   [このチュートリアルを使用する準備をしています](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md)  
  
-   [手順 1: を作成し、ヘッダーと受信確認スキーマを展開](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-header-and-acknowledgment-schemas.md)  
  
-   [手順 2: v2.3.1 の一般的なスキーマを作成します。](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md)  
  
-   [手順 3: を作成し、トリガー イベント (メッセージ) プロジェクトの配置](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project.md)  
  
-   [手順 4: 作成、ADT を受け入れるための受信ポート ^ MLLP アダプターを使用して ADT システムから A03 メッセージ](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md)  
  
-   [手順 5: ファイル アダプタを使用して、ADT システムに受信確認を配信する送信ポートを作成します。](../../adapters-and-accelerators/accelerator-hl7/step-5-create-send-port-to-deliver-acknowledgments-to-adt-system-using-file.md)  
  
-   [手順 6: ADT を配信する送信ポートを作成する ^ A03 メッセージをファイル アダプターを使用して RX システム](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md)  
  
-   [手順 7: ADT を配信する送信ポートを作成する ^ MLLP アダプターを使用して自分に A03 メッセージ](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md)  
  
-   [手順 8: パーティ情報を構成します。](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md)  
  
-   [手順 9: BizTalk Server を再起動します。](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md)  
  
-   [手順 10: エンド ツー エンド シナリオを確認してください。](../../adapters-and-accelerators/accelerator-hl7/step-10-verify-the-end-to-end-scenario.md)

## <a name="see-also"></a>参照
[使い始める BizTalk Accelerator 用 HL7](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md)