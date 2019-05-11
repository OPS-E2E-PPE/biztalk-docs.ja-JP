---
title: メッセージングを選択して、オーケストレーション スケジュール サービス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 694f929a-c830-4906-8e97-4fbd50e70133
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 856542d5cb44a352f91cea5f64c56febb0059670
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302276"
---
# <a name="choosing-between-messaging-and-orchestration-itinerary-services"></a>メッセージングを選択して、オーケストレーション スケジュール サービス
メッセージング サブシステムまたは BizTalk Server のオーケストレーションのサブシステムで発生する、スケジュール サービスを構成できます。 これら ESB スケジュール メッセージング サービスは、メッセージの処理に設定されており、(入り口または傾斜オフ) に、BizTalk Server パイプラインで実行される可能性があります。 このオプションは、開発者は正確に場所、パイプラインで、サービスが実行を定義できます。 当然ながら、オーケストレーションのサブシステムでのプロセスに構成されているサービスは、BizTalk オーケストレーションで実行されます。  
  
## <a name="esb-itinerary-messaging-services"></a>ESB スケジュール メッセージング サービス  
 BizTalk Server パイプラインでメッセージが処理されるときに、ESB スケジュール メッセージング サービスを使用すると、メッセージの待機時間が減少します。 バックツー バック サービスを実装すると 1 つのパイプラインで、複数回のメッセージを変換し、メッセージ ボックス データベースに永続化はのみ 1 つでそのエンドポイントにメッセージをルーティングすることができます。 さらに、メッセージング ベースの処理は、オーケストレーション処理の追加リソースのコストを排除します。 一般に、メッセージング ベースの処理は、リソースの処理を要するし、処理のオーケストレーションに基づくより高速に処理を提供します。 パイプラインで、ESB ディスパッチャーと ESB ディスパッチャー逆アセンブル パイプライン コンポーネントによって提供される[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]メッセージ インターセプターとして動作させ、スケジュール サービスとしてメッセージング ベース、ルーティングは、変換、またはカスタムのサービスを実行します。 これらのコンポーネントを構成する方法の詳細については、次を参照してください。 [ESB ディスパッチャー コンポーネント](../esb-toolkit/the-esb-dispatcher-component.md)と[、ESB ディスパッチャー逆アセンブル コンポーネント](../esb-toolkit/the-esb-dispatcher-disassemble-component.md)します。  
  
## <a name="esb-itinerary-orchestration-services"></a>ESB スケジュール オンランプ オーケストレーション サービス  
 間またはオーケストレーション プロセスの後、動的ルーティングが発生する必要がある場合、は、スケジュール サービスをオーケストレーションに基づいた処理を使用します。 既定では、オーケストレーション ベースのサービスには、XML ドキュメントとして、メッセージが表示されます。 ルーティング オーケストレーションは、競合回避モジュール マネージャーを使用して、itinerary で識別されたエンドポイントを解決しようとしています。 アダプター マネージャー Resolver Manager からの応答を使用して、エンドポイントの詳細をメッセージ コンテキストに昇格させると、メッセージは、直接バインドされた論理ポートを使用してメッセージ ボックス データベースに公開されます。 この時点では、通常 BizTalk ルーティングが発生し、メッセージの昇格させたプロパティを使用して、動的送信ポートを構成します。  
  
 含まれるスケジュール サービス オーケストレーションでは、オーケストレーション ベースのカスタム スケジュール サービスを作成するための出発点として適してを提供します。 カスタム スケジュール サービスを作成する方法の詳細については、次を参照してください。[を変更すると、BizTalk ESB Toolkit の拡張](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)します。