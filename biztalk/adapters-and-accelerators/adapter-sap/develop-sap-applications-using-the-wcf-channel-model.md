---
title: WCF チャネル モデルを使用して SAP アプリケーションを開発 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, developing applications by using
ms.assetid: 1ce70c8b-5eeb-4585-97af-b0a7b4398dac
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13015cb042d26c946abfa3c99a4f67034b8d9708
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="develop-sap-applications-using-the-wcf-channel-model"></a>WCF チャネル モデルを使用して SAP アプリケーションを開発します。
使用することができます、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]チャネル モデルを使用する、 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] SAP バインドで作成されたチャネル インスタンス経由で直接 XML メッセージを送信することによってです。  
  
 厳密に型指定されたクラスと、WCF サービス モデルを公開するメソッドを使用する場合より、WCF チャネル モデルを使用する利点の 1 つは、チャネル モデルが SAP システムで実行する操作をより詳細に制御を提供することです。 なぜでしょうか。 WCF チャネル モデルでは、チャネル経由で送信するメッセージの内容を直接制御します。  
  
 WCF チャネル モデルを WCF サービス モデルを提供する主なメリットは、データのストリーミングをサポートする包括的なです。 WCF チャネル モデルを使用して行うことができます。  
  
-   メッセージのストリーミング、コードとアダプター間で交換されるすべてのメッセージにノードです。  
  
-   ノード値のストリーミング、SendIdoc および ReceiveIdoc 操作をメッセージにします。  
  
 これは、WCF チャネル モデルでを直接制御できるため、アダプターに送信するメッセージのメッセージの本文を提供する方法と、アダプターから受信したメッセージのメッセージ本文を使用する方法です。  
  
 これに対し、アダプターはサポートされません、WCF サービス モデルでは、ストリーミングします。 モデルでは、WCF サービス、WCF ランタイムおよび逆シリアル化、XML とマネージ コード オブジェクト表現の間でメッセージをアダプターに交換する各メッセージの完全なインメモリ コピーが行われます。  
  
 このトピックのセクションでは、操作を実行する方法を説明する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF チャネル モデルを使用します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SAP アダプターを使用して WCF チャネル モデルの概要](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-channel-model-with-the-sap-adapter.md)  
  
-   [SAP を使用して、チャネルを作成します。](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md)  
  
-   [WCF チャネル モデルを使用して SAP システムの操作を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)  
  
-   [WCF チャネル モデルを使用して SAP システムから受信操作の受信](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md) 
  
-   [WCF チャネル モデルを使用して SAP でのフラット ファイル Idoc のストリーミング](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)