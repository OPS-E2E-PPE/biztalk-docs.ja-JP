---
title: MQSeries アダプターのコンポーネント |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, BizTalk component
- MQSeries adapters, components
- MQSeries components, MQSeries adapters
- BizTalk components
- MQSeries adapters, MQSeries component
ms.assetid: 923974cb-371d-47dc-99a7-2f7b93f60ada
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58726b6528af55da6554ff740208b3e03bdc806e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232514"
---
# <a name="components-of-the-mqseries-adapter"></a>MQSeries アダプターのコンポーネント
MQSeries アダプターでは、2 つのコンポーネントを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と MQSeries Server for Windows の間のドキュメント転送を容易にしています。  
  
-   **BizTalk コンポーネントです。** Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と同じコンピューターにこのコンポーネントをインストールします。 このコンポーネントによって BizTalk Server との通信が行われます。  
  
-   **MQSeries コンポーネントです。** MQSeries Server for Windows にこのコンポーネントをインストールします。 MQSeries Server for Windows は、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] または [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 上で動作します。 このコンポーネント (MQSAgent と呼ばれます) によって IBM MQSeries Server との通信が行われます。  
  
    > [!NOTE]
    >  MQSeries アダプターの MQSAgent コンポーネントは、Windows 上の MQSeries Server 5.3、CSD10 以降、および WebSphere MQSeries Server 6.0 に対して実行できます。  
  
 次の図に、MQSeries アダプターの一般的な使用方法を示します。  
  
 ![MQSeries Server と BizTalk 間のフローを文書化](../core/media/bts-dev-mqadapterflow.gif "BTS_Dev_MQAdapterFlow")  
  
 MQSeries アダプターは、メッセージング標準として MQSeries を選択している企業で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用できるようにする接続ソリューションです。 このソリューションを開発した背景として、以下のような課題がありました。  
  
-   簡単なインストールと構成、および MQSeries 接続ソリューションに対する顧客の要望に応えること  
  
-   最大 100 MB のメッセージ サイズをサポートすること  
  
-   MQSeries のサポートを提供すること  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信される MQSeries メッセージに対するプラグ アンド プレイの接続ソリューションを提供すること  
  
 MQSeries アダプターは、さまざまな通信プロトコル標準用のリスナー セットを提供する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 受信サービスの重要な追加機能です。 これらのリスナーによって、HTTP、FTP、MQSeries などのプロトコルがエンタープライズ アプリケーション統合 (EAI)、企業間統合、またはアプリケーション統合の取引関係に追加されます。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターのアーキテクチャ](../core/mqseries-adapter-architecture.md)   
 [MQSeries アダプターとは何ですか。](../core/what-is-the-mqseries-adapter.md)