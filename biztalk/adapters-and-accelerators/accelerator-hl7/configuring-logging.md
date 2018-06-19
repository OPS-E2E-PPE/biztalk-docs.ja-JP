---
title: ログの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, auditing
- configuring, logging
- logging, configuring
- auditing, configuring
ms.assetid: cd83acbb-337b-4448-ad43-c0b89c5c3356
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54600ec16d33524af04fb0e4a308172db82a48ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204706"
---
# <a name="configuring-logging"></a><span data-ttu-id="eeca1-102">ログ記録の構成</span><span class="sxs-lookup"><span data-stu-id="eeca1-102">Configuring Logging</span></span>
<span data-ttu-id="eeca1-103">医療アプリケーションでは、メッセージの完全なログ記録が必要です。</span><span class="sxs-lookup"><span data-stu-id="eeca1-103">Health care applications require complete logging of messages.</span></span> <span data-ttu-id="eeca1-104">これらのアプリケーションは、重要な処理するために機密情報および通貨のデータ、ログは、アプリケーションの重要な部分になります。</span><span class="sxs-lookup"><span data-stu-id="eeca1-104">Since these applications handle critical, time sensitive and monetary data, logging becomes a critical part of the application.</span></span> <span data-ttu-id="eeca1-105">システム管理者は、次を実行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="eeca1-105">System administrators need to be able to do the following:</span></span>  
  
-   <span data-ttu-id="eeca1-106">構成されている場所にメッセージを保存します。</span><span class="sxs-lookup"><span data-stu-id="eeca1-106">Store messages in a configured place</span></span>  
  
-   <span data-ttu-id="eeca1-107">実際のメッセージをログに記録されたメッセージを関連付ける</span><span class="sxs-lookup"><span data-stu-id="eeca1-107">Correlate the logged messages to the actual message</span></span>  
  
-   <span data-ttu-id="eeca1-108">パートナーごと、またはプロセスの種類ごとに、メッセージ ボックスの一覧します。</span><span class="sxs-lookup"><span data-stu-id="eeca1-108">List the message per partner or per process type</span></span>  
  
-   <span data-ttu-id="eeca1-109">これらのログに記録されたメッセージの特定の時点にレポートの実行</span><span class="sxs-lookup"><span data-stu-id="eeca1-109">Run reports at a predetermined time on these logged messages</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eeca1-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="eeca1-110">In This Section</span></span>  
  
-   [<span data-ttu-id="eeca1-111">ログ ストアを選択します。</span><span class="sxs-lookup"><span data-stu-id="eeca1-111">Selecting the Logging Store</span></span>](../../adapters-and-accelerators/accelerator-hl7/selecting-the-logging-store.md)