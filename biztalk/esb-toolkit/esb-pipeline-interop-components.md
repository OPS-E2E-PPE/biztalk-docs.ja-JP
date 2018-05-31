---
title: ESB のパイプライン コンポーネントを相互運用機能 |Microsoft ドキュメント
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
ms.openlocfilehash: ccf4d4353e6928b998d31e8096ee642cd80bb60a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294130"
---
# <a name="esb-pipeline-interop-components"></a>ESB のパイプライン コンポーネントを相互運用機能
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サポート コンポーネントと、次を含むサービスを提供します。  
  
-   **JMS はパイプライン コンポーネントです。** これらのコンポーネントを認識するには、検証、およびメタデータと IBM Mqseries のメッセージング システムで使用される JMS MQRFH2 形式に準拠するメッセージの内容を公開します。 この機能により、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]アプリケーションからメッセージを受信し、MQ Series JMS システムにメッセージを送信します。 コンポーネントは自動的に、ヘッダー情報を昇格させるし、メッセージの内容から降格します。  
  
-   **Namespace パイプライン コンポーネントです。** これらのコンポーネントでは、追加したり、XML メッセージの内容の名前空間を削除することができます。 これにより、競合する名前空間を修復またはメッセージ ボックス データベースおよびアプリケーションのオーケストレーション内で名前空間の競合を防ぐために不足している名前空間を追加するアプリケーション。 コンポーネントには、BizTalk Server 外部の発行システムを変更することがなく POX (Plain Old XML) を使用することもできます。  
  
 ESB パイプライン コンポーネントの詳細については、次を参照してください。[サポートのパイプライン コンポーネントを使用して](../esb-toolkit/using-the-pipeline-support-components.md)です。