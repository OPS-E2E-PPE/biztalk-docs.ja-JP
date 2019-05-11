---
title: カスタム コンポーネントの開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 12b7d99d-ac3c-427d-b6b6-286233fde541
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 576b5bb869e10d90fa44083456b0a2650fbc3ebd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389806"
---
# <a name="developing-custom-components"></a><span data-ttu-id="84acb-102">カスタム コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="84acb-102">Developing Custom Components</span></span>
<span data-ttu-id="84acb-103">BizTalk Server でのカスタム コンポーネントの開発し、変更または BizTalk Server の特定のインフラストラクチャ要素を拡張するために使用します。</span><span class="sxs-lookup"><span data-stu-id="84acb-103">Custom components in BizTalk Server are developed and used to modify or extend certain infrastructure elements of BizTalk Server.</span></span>  <span data-ttu-id="84acb-104">主などが含まれます: 送信または受信アダプター コンポーネントは、アダプター フレームワークに基づいており、特定のトランスポート プロトコルを処理するために使用します。送信のいずれかで使用されるコンポーネントをパイプラインまたは受信パイプラインのステージ。functoid のマップで使用します。</span><span class="sxs-lookup"><span data-stu-id="84acb-104">Primarily, this includes such things as:  send or receive adapter components which are based on the Adapter Framework and used to handle specific transport protocols; pipeline components used in any of the send or receive pipeline stages; and functoids used in maps.</span></span>  <span data-ttu-id="84acb-105">拡張する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]いくつかの方法でカスタム コードを使用します。</span><span class="sxs-lookup"><span data-stu-id="84acb-105">You can extend [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with custom code in several ways.</span></span> <span data-ttu-id="84acb-106">次のトピックでは、これを行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="84acb-106">The following topics describe how to do this.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="84acb-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="84acb-107">In This Section</span></span>  
  
-   [<span data-ttu-id="84acb-108">カスタム アダプターの開発</span><span class="sxs-lookup"><span data-stu-id="84acb-108">Developing Custom Adapters</span></span>](../core/developing-custom-adapters.md)  
  
-   [<span data-ttu-id="84acb-109">カスタム パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="84acb-109">Developing Custom Pipeline Components</span></span>](../core/developing-custom-pipeline-components.md)  
  
-   [<span data-ttu-id="84acb-110">カスタム Functoid の開発</span><span class="sxs-lookup"><span data-stu-id="84acb-110">Developing Custom Functoids</span></span>](../core/developing-custom-functoids.md)