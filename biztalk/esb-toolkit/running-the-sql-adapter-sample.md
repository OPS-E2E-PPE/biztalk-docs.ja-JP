---
title: SQL アダプタのサンプルを実行している |Microsoft ドキュメント
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
ms.openlocfilehash: bf04c06a1ef96974912ce3affe278d5a98936325
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294794"
---
# <a name="running-the-sql-adapter-sample"></a><span data-ttu-id="b6539-102">SQL アダプタのサンプルを実行しています。</span><span class="sxs-lookup"><span data-stu-id="b6539-102">Running the SQL Adapter Sample</span></span>
<span data-ttu-id="b6539-103">SQL アダプタ サンプルでは、行程入り口サンプルに用意されている、テスト クライアントの Windows フォーム アプリケーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="b6539-103">The SQL Adapter sample uses a Windows Forms test client application provided with the Itinerary On-Ramp sample.</span></span>  
  
 <span data-ttu-id="b6539-104">**SQL アダプタ サンプルを実行するには**</span><span class="sxs-lookup"><span data-stu-id="b6539-104">**To run the SQL Adapter sample**</span></span>  
  
1.  <span data-ttu-id="b6539-105">GlobalBank.ESB アプリケーションが既に実行されていない場合は、Microsoft BizTalk 管理コンソールを使用して、開始します。</span><span class="sxs-lookup"><span data-stu-id="b6539-105">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="b6539-106">Windows エクスプ ローラーでフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。インストールした Itinerary.Test、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプル、および Esb.Itinerary.Test.exe をという名前のアプリケーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="b6539-106">In Windows Explorer, open the folder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then start the application named Esb.Itinerary.Test.exe.</span></span>  
  
3.  <span data-ttu-id="b6539-107">クリア、**を使用して WCF サービス**クライアント側の日程を使用できるようにするチェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="b6539-107">Clear the **Use WCF Service** check box so that a client-side itinerary can be used.</span></span>  
  
4.  <span data-ttu-id="b6539-108">選択、 **2 つの方法サービス**オプション</span><span class="sxs-lookup"><span data-stu-id="b6539-108">Select the **Two Way Service** option</span></span>  
  
5.  <span data-ttu-id="b6539-109">クリックして、**ロード行程**ボタンをクリックし、フォルダー \Source\Samples\SqlAdapter \Itineraries にあるサンプルの日程のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="b6539-109">Click the **Load Itinerary** button, and then select one of the sample itineraries located in the folder \Source\Samples\SqlAdapter \Itineraries.</span></span>  
  
6.  <span data-ttu-id="b6539-110">クリックして、 **LoadMessage**ボタンをクリックし、フォルダー \Source\Samples\SqlAdapter \Test で OrderDoc.xml サンプル メッセージを選択します。</span><span class="sxs-lookup"><span data-stu-id="b6539-110">Click the **LoadMessage** button, and then select the OrderDoc.xml sample message in the folder \Source\Samples\SqlAdapter \Test.</span></span>  
  
7.  <span data-ttu-id="b6539-111">クリックして、 **SubmitRequest**行程入り口サービスに要求を送信するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6539-111">Click the **SubmitRequest** button to send the request to the Itinerary On-Ramp service.</span></span>  
  
8.  <span data-ttu-id="b6539-112">1 つの行は GlobalBankESB データベースの Product テーブルに挿入することを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6539-112">Make sure one row is inserted in the Product table of the GlobalBankESB database.</span></span>  
  
 <span data-ttu-id="b6539-113">SQL Adapter サンプルのしくみについては、次を参照してください。 [「SQL アダプタ サンプルの動作](../esb-toolkit/how-the-sql-adapter-sample-works.md)です。</span><span class="sxs-lookup"><span data-stu-id="b6539-113">For information about how the SQL Adapter sample works, see [How the SQL Adapter Sample Works](../esb-toolkit/how-the-sql-adapter-sample-works.md).</span></span>