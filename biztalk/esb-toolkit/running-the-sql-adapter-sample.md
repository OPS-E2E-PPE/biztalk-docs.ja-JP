---
title: SQL アダプター サンプルを実行する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 13566d08-7a59-4065-b0d7-19ae2765555e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7208878da8a2d88b89d1a9ed6a23ac6aaaa5e9a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268799"
---
# <a name="running-the-sql-adapter-sample"></a><span data-ttu-id="ce17c-102">SQL アダプター サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="ce17c-102">Running the SQL Adapter Sample</span></span>
<span data-ttu-id="ce17c-103">SQL Adapter サンプルは、行程導入サンプルで提供される Windows フォームのテスト クライアント アプリケーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="ce17c-103">The SQL Adapter sample uses a Windows Forms test client application provided with the Itinerary On-Ramp sample.</span></span>  
  
 <span data-ttu-id="ce17c-104">**SQL アダプター サンプルを実行するには**</span><span class="sxs-lookup"><span data-stu-id="ce17c-104">**To run the SQL Adapter sample**</span></span>  
  
1. <span data-ttu-id="ce17c-105">GlobalBank.ESB アプリケーションが実行されていない場合は、Microsoft の BizTalk 管理コンソールを使用して、開始します。</span><span class="sxs-lookup"><span data-stu-id="ce17c-105">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
2. <span data-ttu-id="ce17c-106">Windows エクスプ ローラーでフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。インストールした Itinerary.Test、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルをし、Esb.Itinerary.Test.exe という名前のアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="ce17c-106">In Windows Explorer, open the folder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then start the application named Esb.Itinerary.Test.exe.</span></span>  
  
3. <span data-ttu-id="ce17c-107">クリア、 **WCF サービスを使用して**クライアント側の旅行プランを使用できるようにチェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="ce17c-107">Clear the **Use WCF Service** check box so that a client-side itinerary can be used.</span></span>  
  
4. <span data-ttu-id="ce17c-108">選択、**方法の 2 つのサービス**オプション</span><span class="sxs-lookup"><span data-stu-id="ce17c-108">Select the **Two Way Service** option</span></span>  
  
5. <span data-ttu-id="ce17c-109">をクリックして、**ロード行程**ボタンをクリックし、フォルダー \Source\Samples\SqlAdapter \Itineraries 内にあるサンプルのスケジュールのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="ce17c-109">Click the **Load Itinerary** button, and then select one of the sample itineraries located in the folder \Source\Samples\SqlAdapter \Itineraries.</span></span>  
  
6. <span data-ttu-id="ce17c-110">をクリックして、 **LoadMessage**ボタンをクリックし、フォルダー \Source\Samples\SqlAdapter \Test で OrderDoc.xml サンプル メッセージを選択します。</span><span class="sxs-lookup"><span data-stu-id="ce17c-110">Click the **LoadMessage** button, and then select the OrderDoc.xml sample message in the folder \Source\Samples\SqlAdapter \Test.</span></span>  
  
7. <span data-ttu-id="ce17c-111">をクリックして、 **SubmitRequest**行程入口サービスに要求を送信するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce17c-111">Click the **SubmitRequest** button to send the request to the Itinerary On-Ramp service.</span></span>  
  
8. <span data-ttu-id="ce17c-112">GlobalBankESB データベースの Product テーブル内 1 つの行が挿入されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ce17c-112">Make sure one row is inserted in the Product table of the GlobalBankESB database.</span></span>  
  
   <span data-ttu-id="ce17c-113">SQL アダプター サンプルのしくみについては、次を参照してください。 [、SQL アダプター サンプルのしくみ](../esb-toolkit/how-the-sql-adapter-sample-works.md)します。</span><span class="sxs-lookup"><span data-stu-id="ce17c-113">For information about how the SQL Adapter sample works, see [How the SQL Adapter Sample Works](../esb-toolkit/how-the-sql-adapter-sample-works.md).</span></span>