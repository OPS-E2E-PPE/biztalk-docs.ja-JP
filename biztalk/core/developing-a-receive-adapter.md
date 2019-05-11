---
title: 開発、受信アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd2623c4-dc92-435f-83d4-1b6213f3cf59
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f093b56569f3e61196921812df905d72f368b035
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351500"
---
# <a name="developing-a-receive-adapter"></a><span data-ttu-id="859af-102">開発、受信アダプター</span><span class="sxs-lookup"><span data-stu-id="859af-102">Developing a Receive Adapter</span></span>
<span data-ttu-id="859af-103">このセクションでは、受信アダプター内で発生するオブジェクト間の対話処理について説明します。</span><span class="sxs-lookup"><span data-stu-id="859af-103">This section describes the object interactions that occur within receive adapters.</span></span> <span data-ttu-id="859af-104">この情報は、受信アダプターを構築する際にカスタム アダプター開発の指針としたり、ネイティブ アダプターの働きを知ったりする上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="859af-104">You can use this information to guide custom adapter development when creating receive adapters, or to learn about how the native adapters work.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="859af-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="859af-105">In This Section</span></span>  
  
-   [<span data-ttu-id="859af-106">受信アダプターの交換パターン</span><span class="sxs-lookup"><span data-stu-id="859af-106">Exchange Patterns for Receive Adapters</span></span>](../core/exchange-patterns-for-receive-adapters.md)  
  
-   [<span data-ttu-id="859af-107">受信アダプターのインスタンス化と初期化</span><span class="sxs-lookup"><span data-stu-id="859af-107">Instantiating and Initializing a Receive Adapter</span></span>](../core/instantiating-and-initializing-a-receive-adapter.md)  
  
-   [<span data-ttu-id="859af-108">受信アダプターの操作</span><span class="sxs-lookup"><span data-stu-id="859af-108">Receive Adapter Operations</span></span>](../core/receive-adapter-operations.md)  
  
-   [<span data-ttu-id="859af-109">受信処理用メッセージのバッチ処理</span><span class="sxs-lookup"><span data-stu-id="859af-109">Batching Messages for Receive Processing</span></span>](../core/batching-messages-for-receive-processing.md)  
  
-   [<span data-ttu-id="859af-110">受信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="859af-110">Interfaces for Receive Adapters</span></span>](../core/interfaces-for-receive-adapters.md)  
  
-   [<span data-ttu-id="859af-111">受信アダプターの SSO のサポート</span><span class="sxs-lookup"><span data-stu-id="859af-111">SSO Support for Receive Adapters</span></span>](../core/sso-support-for-receive-adapters.md)