---
title: WCF チャネル モデルを使用して SAP アプリケーションの開発 |Microsoft Docs
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
ms.openlocfilehash: e2bce6ad43b6efce111a2801ba7a5b44e73dce1a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013131"
---
# <a name="develop-sap-applications-using-the-wcf-channel-model"></a>WCF チャネル モデルを使用して SAP アプリケーションを開発します。
使用することができます、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]チャネル モデルを使用する、 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] SAP バインドで作成されたチャネル インスタンス経由で直接 XML メッセージを送信することです。  
  
 WCF チャネル モデルを使用して、厳密に型指定されたクラスと、WCF サービス モデルを公開するメソッドを使用する利点の 1 つは、チャネル モデルが SAP システムで実行する操作のきめの細かい制御を提供します。 なぜでしょうか。 WCF チャネル モデルでは、直接チャネル経由で送信するメッセージの内容を制御します。  
  
 WCF チャネル モデルを使用する WCF サービスのモデルに対するもう 1 つの主な利点より包括的なデータのストリーミング サポートです。 WCF チャネル モデルを使用して実行できます。  
  
- メッセージ ノードが、コードとアダプター間で交換されるすべてのメッセージをストリーミングします。  
  
- ノード値の SendIdoc および ReceiveIdoc 操作にストリーミングをメッセージにします。  
  
  これは、ため、WCF チャネル モデルで直接制御するアダプターに送信するメッセージをメッセージ本文が提供する方法と、アダプターから受信したメッセージのメッセージ本文を使用する方法です。  
  
  これに対し、アダプターには、WCF サービス モデルでは、ストリーミングのサポートしますありません。 WCF サービス モデルでは、WCF ランタイムはシリアル化および XML とマネージ コード オブジェクトの表現の間でメッセージを逆シリアル化ため、アダプターと交換する各メッセージの完全なメモリ内コピーが行われます。  
  
  このトピックのセクションでは、操作を実行する方法を説明します、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF チャネル モデルを使用しています。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SAP アダプターを使用した WCF チャネル モデルの概要](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-channel-model-with-the-sap-adapter.md)  
  
-   [SAP を使用してチャネルを作成します。](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md)  
  
-   [WCF チャネル モデルを使用して SAP システムの操作を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)  
  
-   [WCF チャネル モデルを使用して SAP システムから受信操作の受信](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md) 
  
-   [WCF チャネル モデルを使用して SAP でのフラット ファイル Idoc のストリーミング](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)