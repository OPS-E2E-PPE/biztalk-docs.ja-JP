---
title: "カスタムの Itinerary シナリオを実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6fd69e29-e853-4b16-9966-29ab98dd5bea
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8659c5b37cba0520fb4a4c0f4c63c8d6ecff37be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="execute-a-custom-itinerary-scenario"></a><span data-ttu-id="c88d4-102">カスタムの Itinerary シナリオを実行します。</span><span class="sxs-lookup"><span data-stu-id="c88d4-102">Execute a Custom Itinerary Scenario</span></span>
<span data-ttu-id="c88d4-103">行程テスト クライアントを使用するアプリケーションでカスタムの itinerary シナリオを実行します。</span><span class="sxs-lookup"><span data-stu-id="c88d4-103">You can use the Itinerary Test Client application execute custom itinerary scenarios.</span></span>  
  
### <a name="to-execute-a-custom-itinerary-scenario-using-the-itinerary-test-client-application"></a><span data-ttu-id="c88d4-104">行程テスト用クライアント アプリケーションを使用してカスタム itinerary シナリオを実行するには</span><span class="sxs-lookup"><span data-stu-id="c88d4-104">To execute a custom itinerary scenario using the Itinerary Test Client application</span></span>  
  
1.  <span data-ttu-id="c88d4-105">Windows エクスプ ローラーでフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。インストールした Itinerary.Test\bin\Debug、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプリングし、Esb.Itinerary.Test.exe をという名前のアプリケーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="c88d4-105">In Windows Explorer, open the folder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test\bin\Debug where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples and start the application named Esb.Itinerary.Test.exe.</span></span>  
  
2.  <span data-ttu-id="c88d4-106">サービスの種類を選択、 **ServiceType**ドロップダウン リストが、要求の名前を指定し、、 **IsRequestResponse**これは、要求/応答操作の場合はチェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="c88d4-106">Select a service type in the **ServiceType** drop-down list, specify a name for the request, and then select the **IsRequestResponse** check box if this is a request/response operation.</span></span> <span data-ttu-id="c88d4-107">双方向の操作を指定し、WCF サービスのバージョンは、行程 Web; を使用します。これを行うには、チェック ボックスをオンに、 **Web サービス オプション**アプリケーション ウィンドウの上部にあるセクションです。</span><span class="sxs-lookup"><span data-stu-id="c88d4-107">You can specify a two-way operation and choose to use the WCF version of the Itinerary Web service; to do this, select the check boxes in the **Web Service Options** section at the top of the application window.</span></span>  
  
3.  <span data-ttu-id="c88d4-108">選択したサービスで使用する競合回避モジュールを指定する、 **AddResolversfortheService**ウィンドウの、競合回避モジュールは、ドロップダウン リストから、入力し、をクリックして**AddResolver**です。</span><span class="sxs-lookup"><span data-stu-id="c88d4-108">To specify the resolvers to use with the selected service in the **AddResolversfortheService** section of the window, select a resolver type from the drop-down list, and then click **AddResolver**.</span></span> <span data-ttu-id="c88d4-109">必要な場合は、複数の競合回避モジュールを追加できます。</span><span class="sxs-lookup"><span data-stu-id="c88d4-109">You can add more than one resolver if required.</span></span> <span data-ttu-id="c88d4-110">必要なすべての競合回避モジュールを追加した後にをクリックして、 **AddService**旅行計画にこのサービスの呼び出しを追加するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c88d4-110">After you add all the required resolvers, click the **AddService** button to add this service invocation to the itinerary.</span></span>  
  
4.  <span data-ttu-id="c88d4-111">旅行計画に複数のサービスの呼び出しを追加する場合は、手順 2. および 3. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c88d4-111">If you want to add more service invocations to the itinerary, repeat steps 2 and 3.</span></span> <span data-ttu-id="c88d4-112">使用することも、 **RemoveService**と**ClearServices**旅行計画内のサービスのリストを変更するボタンです。</span><span class="sxs-lookup"><span data-stu-id="c88d4-112">You can also use the **RemoveService** and **ClearServices** buttons to modify the list of services in the itinerary.</span></span>  
  
5.  <span data-ttu-id="c88d4-113">別の時に現在の旅程を繰り返す場合は、現在の完全な旅程をディスクに保存 をクリックして、 **SaveItinerary**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c88d4-113">If you want to repeat the current itinerary at another time, save the complete current itinerary to disk by clicking the **SaveItinerary** button.</span></span> <span data-ttu-id="c88d4-114">クリックして再度読み込むことができます、 **LoadItinerary**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c88d4-114">You can load it again by clicking the **LoadItinerary** button.</span></span> <span data-ttu-id="c88d4-115">これは、別のメッセージや行程 Web サービスの設定では、このシナリオを実行するたびに、旅行計画で、サービスとの競合回避モジュールを指定する必要はないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="c88d4-115">This means that you do not have to specify the services and resolvers in the itinerary every time you execute this scenario with different messages or Itinerary Web service settings.</span></span>  
  
6.  <span data-ttu-id="c88d4-116">適切なメッセージを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="c88d4-116">Load a suitable message.</span></span> <span data-ttu-id="c88d4-117">内のメッセージの名前とパスを入力するかそのためには、 **LoadMessage**テキスト ボックスまたは省略記号ボタン (...) をクリックし、必須のメッセージ ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="c88d4-117">To do this, either type the path and name of the message in the **LoadMessage** text box or click the ellipsis button (...), and then select the required message file.</span></span>  
  
7.  <span data-ttu-id="c88d4-118">クリックして、 **SubmitRequest** itinerary に指定した設定で処理するため、メッセージを送信するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c88d4-118">Click the **SubmitRequest** button to submit the message for processing with the itinerary settings you specified.</span></span> <span data-ttu-id="c88d4-119">処理には、結果が返された場合に表示されます、**結果**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="c88d4-119">If the processing returns a result, this will appear in the **Result** text box.</span></span>