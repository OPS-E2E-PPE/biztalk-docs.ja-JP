---
title: MQSeries アダプターのコンポーネント |Microsoft Docs
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
ms.openlocfilehash: 6c6a97bd38a68eef866549f980624a92ee2b3143
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391638"
---
# <a name="components-of-the-mqseries-adapter"></a>MQSeries アダプターのコンポーネント
MQSeries アダプターの間のドキュメント転送を容易に 2 つのコンポーネントを使用して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と MQSeries Server for Windows。  
  
- **BizTalk コンポーネントです。** Microsoft と同じコンピューターにこのコンポーネントをインストール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 このコンポーネントは、BizTalk Server と通信します。  
  
- **MQSeries コンポーネントです。** Windows の MQSeries サーバーでこのコンポーネントをインストールします。 MQSeries Server for Windows 上で実行[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]します。 このコンポーネント (MQSAgent と呼ばれます) は、IBM MQSeries Server と通信します。  
  
  > [!NOTE]
  >  MQSeries アダプターの MQSAgent コンポーネントは、サポートされている実行に対して MQSeries Server 5.3、CSD10 以降および Windows 上の WebSphere MQSeries Server 6.0 です。  
  
  次の図では、アダプターの一般的な使用について説明します。  
  
  ![MQSeries Server と BizTalk 間のフローを文書化](../core/media/bts-dev-mqadapterflow.gif "BTS_Dev_MQAdapterFlow")  
  
  MQSeries アダプターが使用できるようにする接続ソリューション[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]エンタープライズで選択したメッセージング標準として MQSeries します。 このソリューションが開発されたように促されて、一部を次の問題。  
  
- 簡単なインストールと構成、および MQSeries 接続ソリューションに対する顧客の要望に対応  
  
- 最大 100 MB のサイズをメッセージのサポート  
  
- MQSeries のサポートを提供します。  
  
- 送信される MQSeries メッセージのプラグ アンド プレイの接続ソリューションを提供します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
  MQSeries アダプターは、重要な追加、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]さまざまな通信プロトコル標準用のリスナーのセットを提供する受信サービスのスイートです。 リスナーは、エンタープライズ アプリケーション統合 (EAI)、企業間取引、またはアプリケーションの統合の取引関係にプロトコル、HTTP、FTP、または MQSeries、たとえばをアタッチします。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターのアーキテクチャ](../core/mqseries-adapter-architecture.md)   
 [MQSeries アダプターとは](../core/what-is-the-mqseries-adapter.md)