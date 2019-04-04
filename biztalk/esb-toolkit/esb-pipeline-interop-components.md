---
title: ESB パイプライン相互運用機能コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 25f9fb9d-d3d4-4df8-8e81-38b432f42ccf
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 794ce6407d10fc820444384550357f10d24f7723
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024246"
---
# <a name="esb-pipeline-interop-components"></a>ESB パイプライン相互運用機能コンポーネント
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サポート コンポーネントと、次を含むサービスを提供します。  
  
- **JMS では、コンポーネントをパイプラインします。** これらのコンポーネントを認識するには、検証、およびメタデータ、および IBM MQ Series のメッセージング システムで使用する JMS MQRFH2 形式に準拠するメッセージの内容を公開します。 この機能により、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]アプリケーションからメッセージを受信し、MQ Series JMS システムにメッセージを送信します。 コンポーネントは自動的に、ヘッダー情報を昇格し、メッセージの内容から降格します。  
  
- **Namespace パイプライン コンポーネント。** これらのコンポーネントでは、追加したり、名前空間で XML メッセージの内容を削除することができます。 これにより、アプリケーションを競合する名前空間を修復またはメッセージ ボックス データベースとアプリケーションのオーケストレーション内で名前空間の競合を防ぐために不足している名前空間を追加できます。 コンポーネントでは、BizTalk Server 外部の発行システムを変更することがなく、POX (Plain Old XML) を使用することもできます。  
  
  ESB パイプライン コンポーネントの詳細については、[パイプライン サポート コンポーネントを使用して](../esb-toolkit/using-the-pipeline-support-components.md)を参照してください。