---
title: カスタム コンポーネントの開発 |Microsoft ドキュメント
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
ms.openlocfilehash: 7b61144b2acaf787d56468c23c04835b5ad79324
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239266"
---
# <a name="developing-custom-components"></a><span data-ttu-id="a21b1-102">カスタム コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="a21b1-102">Developing Custom Components</span></span>
<span data-ttu-id="a21b1-103">BizTalk Server のカスタム コンポーネントは、BizTalk Server の特定のインフラストラクチャ要素を変更または拡張するために開発および使用されます。</span><span class="sxs-lookup"><span data-stu-id="a21b1-103">Custom components in BizTalk Server are developed and used to modify or extend certain infrastructure elements of BizTalk Server.</span></span>  <span data-ttu-id="a21b1-104">主などが含まれます: 送信または受信アダプターはアダプター フレームワークに基づいており、特定のトランスポート プロトコルを処理するために使用します。送信のいずれかで使用されるコンポーネントをパイプラインまたは受信パイプラインのステージです。および functoid のマップで使用します。</span><span class="sxs-lookup"><span data-stu-id="a21b1-104">Primarily, this includes such things as:  send or receive adapter components which are based on the Adapter Framework and used to handle specific transport protocols; pipeline components used in any of the send or receive pipeline stages; and functoids used in maps.</span></span>  <span data-ttu-id="a21b1-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をカスタム コードで拡張するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="a21b1-105">You can extend [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with custom code in several ways.</span></span> <span data-ttu-id="a21b1-106">この方法については、以下のトピックで説明します。</span><span class="sxs-lookup"><span data-stu-id="a21b1-106">The following topics describe how to do this.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a21b1-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a21b1-107">In This Section</span></span>  
  
-   [<span data-ttu-id="a21b1-108">カスタム アダプターの開発</span><span class="sxs-lookup"><span data-stu-id="a21b1-108">Developing Custom Adapters</span></span>](../core/developing-custom-adapters.md)  
  
-   [<span data-ttu-id="a21b1-109">カスタム パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="a21b1-109">Developing Custom Pipeline Components</span></span>](../core/developing-custom-pipeline-components.md)  
  
-   [<span data-ttu-id="a21b1-110">カスタム Functoid の開発</span><span class="sxs-lookup"><span data-stu-id="a21b1-110">Developing Custom Functoids</span></span>](../core/developing-custom-functoids.md)