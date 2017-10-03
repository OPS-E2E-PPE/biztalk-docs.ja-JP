---
title: "ESB には、オーケストレーションの例外のルーティング メカニズムが失敗しました |。Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa05f44b-7fb2-48fd-886d-c6d179904e6d
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afda61ea19587b327f0fe773b150eeb8f88a4f7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-esb-failed-orchestration-exception-routing-mechanism"></a><span data-ttu-id="87459-102">ESB オーケストレーション例外ルーティング機構に失敗しました</span><span class="sxs-lookup"><span data-stu-id="87459-102">The ESB Failed Orchestration Exception Routing Mechanism</span></span>
<span data-ttu-id="87459-103">ESB 失敗オーケストレーション例外ルーティング メカニズムは、次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="87459-103">The ESB Failed Orchestration Exception Routing mechanism provides the following features:</span></span>  
  
-   <span data-ttu-id="87459-104">**アンビエント プロパティをキャプチャするエラー メッセージを作成します。**</span><span class="sxs-lookup"><span data-stu-id="87459-104">**Creating fault messages that capture ambient properties.**</span></span> <span data-ttu-id="87459-105">**CreateFaultMessage**メソッドには、オーケストレーションを含むエラー メッセージが生成されますサービス名とサービス インスタンス ID に、現在アクティブ化されたオーケストレーションの図形では、オーケストレーションが、アプリケーションの名前。展開されると、オーケストレーションを処理するサーバーの名前と例外の日付と時刻 (UTC 形式)。</span><span class="sxs-lookup"><span data-stu-id="87459-105">The **CreateFaultMessage** method generates a fault message that contains the orchestration service name and service instance ID, the currently activated orchestration shape, the name of the application to which the orchestration is deployed, the name of the server processing the orchestration, and the exception date and time (UTC format).</span></span> <span data-ttu-id="87459-106">現在も暗黙的に追加**System.Exception**現在のオーケストレーション図形の例外ハンドラーで生成されたオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="87459-106">It also implicitly adds the current **System.Exception** object generated in the exception handler of the current orchestration shape.</span></span>  
  
-   <span data-ttu-id="87459-107">**エラー メッセージをオーケストレーションの既存のメッセージを追加する**です。</span><span class="sxs-lookup"><span data-stu-id="87459-107">**Adding existing orchestration messages to a fault message**.</span></span> <span data-ttu-id="87459-108">**AddMessage**メソッドには、オーケストレーション メッセージと、エラー メッセージ内のすべてのメッセージ コンテキスト プロパティの XLANG 設定が保持されます。</span><span class="sxs-lookup"><span data-stu-id="87459-108">The **AddMessage** method preserves the XLANG setting of the orchestration message and all the message context properties in the fault message.</span></span>  
  
-   <span data-ttu-id="87459-109">**エラー メッセージに既存の例外オブジェクトを明示的に追加**です。</span><span class="sxs-lookup"><span data-stu-id="87459-109">**Explicitly adding an existing Exception object to a fault message**.</span></span> <span data-ttu-id="87459-110">**SetFaultMsgException**メソッドとしてオブジェクトをシリアル化、 **System.Exception**し、エラー メッセージで保持します。</span><span class="sxs-lookup"><span data-stu-id="87459-110">The **SetFaultMsgException** method serializes the object as a **System.Exception** and preserves it in the fault message.</span></span>  
  
-   <span data-ttu-id="87459-111">**サブスクライバーで受信したエラー メッセージから、列挙型のないメッセージのコレクションを取得する**です。</span><span class="sxs-lookup"><span data-stu-id="87459-111">**Retrieving an enumerated collection of type-less messages from a fault message received by a subscriber**.</span></span> <span data-ttu-id="87459-112">**GetMessages**メソッドは、XLANG メッセージとして、失敗したオーケストレーションからすべての永続化されたメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="87459-112">The **GetMessages** method retrieves all persisted messages from the failed orchestration as XLANG messages.</span></span> <span data-ttu-id="87459-113">各 XLANG メッセージに永続化された各メッセージのすべての元のコンテキスト プロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="87459-113">It returns all the original context properties of each persisted message in each XLANG message.</span></span>  
  
-   <span data-ttu-id="87459-114">**サブスクライバーで受信したエラー メッセージから、厳密に型指定の XLANG オーケストレーション メッセージを取得する**です。</span><span class="sxs-lookup"><span data-stu-id="87459-114">**Retrieving a strongly typed XLANG orchestration message from a fault message received by a subscriber**.</span></span> <span data-ttu-id="87459-115">**GetMessage**メソッドは、エラー メッセージを XLANG メッセージとしてから、特定の種類の永続化されたメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="87459-115">The **GetMessage** method retrieves a persisted message of a specific type from the fault message as an XLANG message.</span></span> <span data-ttu-id="87459-116">XLANG メッセージに永続化されたメッセージのすべての元のコンテキスト プロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="87459-116">It returns all the original context properties of the persisted message in the XLANG message.</span></span> <span data-ttu-id="87459-117">検索もサポートしています、 **System.Exception**オブジェクトが失敗したオーケストレーションによって生成され、取得、永続化された**System.Exception**フォールト メッセージからのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="87459-117">It also supports retrieval of the **System.Exception** object generated by the failed orchestration and retrieves a persisted **System.Exception** object from the fault message.</span></span>