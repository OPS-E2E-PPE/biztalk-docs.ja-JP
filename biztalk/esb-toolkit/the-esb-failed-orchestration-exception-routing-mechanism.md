---
title: Esb オーケストレーションの例外ルーティング メカニズム |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa05f44b-7fb2-48fd-886d-c6d179904e6d
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1da528a8af1b232f014a349afae292a7c0e319d5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399816"
---
# <a name="the-esb-failed-orchestration-exception-routing-mechanism"></a><span data-ttu-id="2f82c-102">Esb オーケストレーションの例外ルーティング メカニズム</span><span class="sxs-lookup"><span data-stu-id="2f82c-102">The ESB Failed Orchestration Exception Routing Mechanism</span></span>
<span data-ttu-id="2f82c-103">ESB 失敗オーケストレーションの例外ルーティング メカニズムは、次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="2f82c-103">The ESB Failed Orchestration Exception Routing mechanism provides the following features:</span></span>  
  
-   <span data-ttu-id="2f82c-104">**アンビエント プロパティをキャプチャするエラー メッセージを作成します。**</span><span class="sxs-lookup"><span data-stu-id="2f82c-104">**Creating fault messages that capture ambient properties.**</span></span> <span data-ttu-id="2f82c-105">**CreateFaultMessage**メソッドには、オーケストレーションを含むエラー メッセージが生成されますサービス名とサービス インスタンス ID、現在アクティブなオーケストレーション図形のオーケストレーションをアプリケーションの名前。オーケストレーションを処理するサーバーの名前を展開します。 例外の日付と時刻 (UTC 形式)。</span><span class="sxs-lookup"><span data-stu-id="2f82c-105">The **CreateFaultMessage** method generates a fault message that contains the orchestration service name and service instance ID, the currently activated orchestration shape, the name of the application to which the orchestration is deployed, the name of the server processing the orchestration, and the exception date and time (UTC format).</span></span> <span data-ttu-id="2f82c-106">現在も暗黙的に追加**System.Exception**現在のオーケストレーション図形の例外ハンドラーで生成されたオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2f82c-106">It also implicitly adds the current **System.Exception** object generated in the exception handler of the current orchestration shape.</span></span>  
  
-   <span data-ttu-id="2f82c-107">**エラー メッセージをオーケストレーションの既存のメッセージを追加する**します。</span><span class="sxs-lookup"><span data-stu-id="2f82c-107">**Adding existing orchestration messages to a fault message**.</span></span> <span data-ttu-id="2f82c-108">**AddMessage**メソッドには、オーケストレーションのメッセージと、エラー メッセージ内のすべてのメッセージ コンテキスト プロパティの XLANG 設定が保持されます。</span><span class="sxs-lookup"><span data-stu-id="2f82c-108">The **AddMessage** method preserves the XLANG setting of the orchestration message and all the message context properties in the fault message.</span></span>  
  
-   <span data-ttu-id="2f82c-109">**エラー メッセージに既存の例外オブジェクトを明示的に追加**します。</span><span class="sxs-lookup"><span data-stu-id="2f82c-109">**Explicitly adding an existing Exception object to a fault message**.</span></span> <span data-ttu-id="2f82c-110">**SetFaultMsgException**メソッドとしてオブジェクトをシリアル化、 **System.Exception**とエラー メッセージではこれを保存します。</span><span class="sxs-lookup"><span data-stu-id="2f82c-110">The **SetFaultMsgException** method serializes the object as a **System.Exception** and preserves it in the fault message.</span></span>  
  
-   <span data-ttu-id="2f82c-111">**サブスクライバーで受信したエラー メッセージから、列挙型のないメッセージのコレクションを取得する**します。</span><span class="sxs-lookup"><span data-stu-id="2f82c-111">**Retrieving an enumerated collection of type-less messages from a fault message received by a subscriber**.</span></span> <span data-ttu-id="2f82c-112">**GetMessages**メソッドは、XLANG メッセージとして、失敗したオーケストレーションからすべての永続化されたメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="2f82c-112">The **GetMessages** method retrieves all persisted messages from the failed orchestration as XLANG messages.</span></span> <span data-ttu-id="2f82c-113">各 XLANG メッセージに永続化された各メッセージのすべての元のコンテキスト プロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="2f82c-113">It returns all the original context properties of each persisted message in each XLANG message.</span></span>  
  
-   <span data-ttu-id="2f82c-114">**サブスクライバーで受信したエラー メッセージから、厳密に型指定の XLANG オーケストレーション メッセージを取得する**します。</span><span class="sxs-lookup"><span data-stu-id="2f82c-114">**Retrieving a strongly typed XLANG orchestration message from a fault message received by a subscriber**.</span></span> <span data-ttu-id="2f82c-115">**GetMessage**メソッドは、XLANG メッセージとしてエラー メッセージから特定の種類の永続化されたメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="2f82c-115">The **GetMessage** method retrieves a persisted message of a specific type from the fault message as an XLANG message.</span></span> <span data-ttu-id="2f82c-116">XLANG メッセージに永続化されたメッセージのすべての元のコンテキスト プロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="2f82c-116">It returns all the original context properties of the persisted message in the XLANG message.</span></span> <span data-ttu-id="2f82c-117">取得もサポートしています、 **System.Exception**オブジェクトが失敗したオーケストレーションによって生成され、取得された保存される**System.Exception**フォールト メッセージからオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2f82c-117">It also supports retrieval of the **System.Exception** object generated by the failed orchestration and retrieves a persisted **System.Exception** object from the fault message.</span></span>