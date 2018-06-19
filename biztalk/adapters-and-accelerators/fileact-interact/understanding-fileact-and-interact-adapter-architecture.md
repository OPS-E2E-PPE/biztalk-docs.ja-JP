---
title: FileAct を理解し、アダプターのアーキテクチャの対話 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f97a7fe-20df-4509-bb6e-53743c3a57df
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c04d0ba8b1c2bbd99a71e3d76c8d7ad60c251147
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223410"
---
# <a name="understanding-fileact-and-interact-adapter-architecture"></a>FileAct を理解し、アダプターのアーキテクチャの対話
SWIFT アダプターは、BizTalk アダプター フレームワークに基づいています。 BizTalk Server 内のアダプターの分類を使用して、SWIFT アダプター, FileAct および InterAct、意味は次の。  
  
-   カスタム アダプター。 これは、カスタム アダプター FileAct および Interact と呼ばれる独自の標準を使用する SWIFT ネットワークと対話するための専用です。  
  
-   トランスポート アダプターです。 このアダプターは、SWIFT ネットワークは、メッセージを送受信するビジネス ソフトウェア アプリケーションを許可します。  
  
-   非トランザクションです。 アダプターは加えません SWIFT ネットワークと対話する任意のトランザクション オブジェクトを使用します。  
  
-   分離。 受信アダプターが別のプロセスで実行し、プロセスで正規の送信アダプターを実行します。  
  
 BizTalk アダプター フレームワークの詳細については、次を参照してください、は、アダプター フレームワーク?"。 BizTalk Server ヘルプのトピックです。  
  
 次の図は、FileAct および InterAct アーキテクチャの概要を示します。  
  
 ![](../../adapters-and-accelerators/fileact-interact/media/035ebb05-ce11-447c-b56b-ba8b41e07e50.gif "035ebb05-ce11-447c-b56b-ba8b41e07e50")  
  
> [!NOTE]
>  Microsoft[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]厳格モードの SWIFTNet リンク (SNL) API のみをサポートします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SWIFTNet クライアントとサーバー](../../adapters-and-accelerators/fileact-interact/swiftnet-client-and-server.md)  
  
-   [SWIFT 送信アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md)  
  
-   [SWIFT 受信アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)  
  
-   [FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)  
  
-   [アダプターのアーキテクチャを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)