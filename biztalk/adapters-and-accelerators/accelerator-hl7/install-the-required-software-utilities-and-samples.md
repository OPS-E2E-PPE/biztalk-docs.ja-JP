---
title: 必要なソフトウェア、ユーティリティ、およびサンプルのインストール |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de0cb89d-08bd-48ec-a149-8929e2608df8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 678037cd050ae8375b3c9ec465860d939d48cccc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204874"
---
# <a name="install-the-required-software-utilities-and-samples"></a>必要なソフトウェア、ユーティリティ、およびサンプルをインストールします。
このチュートリアルに必要です[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Windows Server、およびカスタム[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] MLLP テスト ツールを含むインストールします。 さらは理解しておく[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で開発[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]と[HL7 アクセラレータと使用可能な BizTalk ツールの学習](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)です。
  
 次のユーティリティとサンプルをコンピューターにインストールする必要があります。  
  
-   **MllpSend ツール**  
  
     このコマンド ライン ユーティリティは、メッセージを送信経由で、最小下位層プロトコル (MLLP) プロトコルを MLLP の受信場所。 これを使用するには、チュートリアルの結果をテストします。 詳細については、次を参照してください。 [MllpSend ツール](../../adapters-and-accelerators/accelerator-hl7/mllpsend-tool.md)です。  
  
-   **MllpPReceive ツール**  
  
     このコマンド ライン ユーティリティは、受信場所のリスナーとして機能している、MLLP のプロトコルを介してメッセージを受信します。 メッセージおよび受信した受信確認を表示する、テスト、チュートリアルの結果に使用するとします。 詳細については、次を参照してください。 [MllpReceive ツール](../../adapters-and-accelerators/accelerator-hl7/mllpreceive-tool.md)です。  
  
-   **サンプル アプリケーションに同意 ACK.txt**  
  
     このサンプル ファイルのテキストを含む、受信確認メッセージのアプリケーション承諾します。 サンプルは、受信、メッセージを表示し、サンプル ファイルで、確認を返信する MllpReceive ツールと連携します。  
  
 BTAHL7 カスタム インストール プロセスを使用して 2 つのツールとサンプル ファイルをインストールする必要があります。 通常のインストール プロセスでは、これらのツールはインストールされません。 これらのツールをインストールするに BTAHL7 のカスタム インストールを実行、**カスタム セットアップ**画面で、 **MLLP テスト ツール**から、**アダプター**フォルダー、および選択**テスト インスタンス**から、**成果物**フォルダーです。 詳細については、次を参照してください。 [BizTalk Accelerator 用 HL7 インストール](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)です。  
  
## <a name="see-also"></a>参照  
 [バッチ処理のチュートリアルを使用する準備をしています](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)