---
title: 必要なソフトウェア、ユーティリティ、およびサンプルのインストール |Microsoft Docs
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
ms.openlocfilehash: 45f92f4cc994b4139c1c33423cc7a94c9072e226
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965907"
---
# <a name="install-the-required-software-utilities-and-samples"></a>必要なソフトウェア、ユーティリティ、およびサンプルをインストールします。
このチュートリアルは、Microsoft Windows Server、およびカスタムの Microsoft が必要です。 [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] MLLP テスト ツールを含むインストールします。 さらに、知っておくべきで[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Microsoft での開発[!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]と[HL7 アクセラレータや使用可能な BizTalk ツールの学習](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)します。
  
 次のユーティリティとサンプルをコンピューターにインストールする必要があります。  
  
- **MllpSend ツール**  
  
   このコマンド ライン ユーティリティは、メッセージを送信経由で、最小下位レイヤー プロトコル (MLLP) プロトコルを MLLP の受信場所。 これを使用するには、チュートリアルの結果をテストします。 詳細については、[MllpSend ツール](../../adapters-and-accelerators/accelerator-hl7/mllpsend-tool.md)を参照してください。  
  
- **MllpPReceive ツール**  
  
   このコマンド ライン ユーティリティでは、受信場所のリスナーとして機能、MLLP プロトコル経由でメッセージを受信します。 これを使用して、メッセージおよび受信した受信確認を表示する、チュートリアルの結果をテストします。 詳細については、[MllpReceive ツール](../../adapters-and-accelerators/accelerator-hl7/mllpreceive-tool.md)を参照してください。  
  
- **サンプル アプリケーションに同意 ACK.txt**  
  
   このサンプル ファイルのテキストを格納する、アプリケーションの受信確認メッセージを受け入れます。 サンプルは、受信、メッセージを表示し、サンプル ファイルで、確認を返信 MllpReceive ツールと連携します。  
  
  BTAHL7 のカスタム インストール プロセスを使用して 2 つのツールとサンプル ファイルをインストールする必要があります。 一般的なインストール プロセスでは、これらのツールはインストールされません。 これらのツールをインストールするで、BTAHL7 のカスタム インストールを実行、**カスタム セットアップ**画面で、 **MLLP テスト ツール**から、**アダプター**フォルダー、および選択**テスト インスタンス**から、**成果物**フォルダー。 詳細については、[BizTalk Accelerator for HL7 のインストール](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [バッチ処理のチュートリアルを使用するための準備](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)