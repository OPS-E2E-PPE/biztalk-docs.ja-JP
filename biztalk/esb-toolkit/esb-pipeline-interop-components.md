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
# <a name="esb-pipeline-interop-components"></a><span data-ttu-id="2b124-102">ESB パイプライン相互運用機能コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2b124-102">ESB Pipeline Interop Components</span></span>
<span data-ttu-id="2b124-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サポート コンポーネントと、次を含むサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="2b124-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides support components and services, including the following:</span></span>  
  
- <span data-ttu-id="2b124-104">**JMS では、コンポーネントをパイプラインします。**</span><span class="sxs-lookup"><span data-stu-id="2b124-104">**JMS pipeline components.**</span></span> <span data-ttu-id="2b124-105">これらのコンポーネントを認識するには、検証、およびメタデータ、および IBM MQ Series のメッセージング システムで使用する JMS MQRFH2 形式に準拠するメッセージの内容を公開します。</span><span class="sxs-lookup"><span data-stu-id="2b124-105">These components recognize, validate, and expose metadata and the content of messages that conform to the JMS MQRFH2 format used by IBM MQ Series messaging systems.</span></span> <span data-ttu-id="2b124-106">この機能により、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]アプリケーションからメッセージを受信し、MQ Series JMS システムにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="2b124-106">This functionality allows a [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] application to receive messages from and send messages to JMS systems over MQ Series.</span></span> <span data-ttu-id="2b124-107">コンポーネントは自動的に、ヘッダー情報を昇格し、メッセージの内容から降格します。</span><span class="sxs-lookup"><span data-stu-id="2b124-107">The components automatically promote header information into, and demote it from, the message content.</span></span>  
  
- <span data-ttu-id="2b124-108">**Namespace パイプライン コンポーネント。**</span><span class="sxs-lookup"><span data-stu-id="2b124-108">**Namespace pipeline components.**</span></span> <span data-ttu-id="2b124-109">これらのコンポーネントでは、追加したり、名前空間で XML メッセージの内容を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="2b124-109">These components can add or remove namespaces in the content of XML messages.</span></span> <span data-ttu-id="2b124-110">これにより、アプリケーションを競合する名前空間を修復またはメッセージ ボックス データベースとアプリケーションのオーケストレーション内で名前空間の競合を防ぐために不足している名前空間を追加できます。</span><span class="sxs-lookup"><span data-stu-id="2b124-110">This allows applications to repair conflicting namespaces or add missing namespaces to prevent namespace collisions within the Message Box database and application orchestrations.</span></span> <span data-ttu-id="2b124-111">コンポーネントでは、BizTalk Server 外部の発行システムを変更することがなく、POX (Plain Old XML) を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="2b124-111">The components also allow BizTalk Server to consume POX (Plain Old XML) without modifying external publishing systems.</span></span>  
  
  <span data-ttu-id="2b124-112">ESB パイプライン コンポーネントの詳細については、次を参照してください。[パイプライン サポート コンポーネントを使用して](../esb-toolkit/using-the-pipeline-support-components.md)します。</span><span class="sxs-lookup"><span data-stu-id="2b124-112">For more information about the ESB pipeline components, see [Using the Pipeline Support Components](../esb-toolkit/using-the-pipeline-support-components.md).</span></span>