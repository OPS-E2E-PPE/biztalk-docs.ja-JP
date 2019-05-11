---
title: カスタム スケジュール シナリオの実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6fd69e29-e853-4b16-9966-29ab98dd5bea
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1533d2fcea864c1b2effb8afc2dda35c0b36c7c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261936"
---
# <a name="execute-a-custom-itinerary-scenario"></a><span data-ttu-id="db3c6-102">カスタム スケジュール シナリオを実行します。</span><span class="sxs-lookup"><span data-stu-id="db3c6-102">Execute a Custom Itinerary Scenario</span></span>
<span data-ttu-id="db3c6-103">旅行プランのテスト クライアントを使用するアプリケーションでカスタム スケジュール シナリオを実行します。</span><span class="sxs-lookup"><span data-stu-id="db3c6-103">You can use the Itinerary Test Client application execute custom itinerary scenarios.</span></span>  

### <a name="to-execute-a-custom-itinerary-scenario-using-the-itinerary-test-client-application"></a><span data-ttu-id="db3c6-104">旅行プランのテスト用クライアント アプリケーションを使用して、カスタム スケジュール シナリオを実行するには</span><span class="sxs-lookup"><span data-stu-id="db3c6-104">To execute a custom itinerary scenario using the Itinerary Test Client application</span></span>  

1. <span data-ttu-id="db3c6-105">Windows エクスプ ローラーでフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。インストールした Itinerary.Test\bin\Debug、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]をサンプリングし、Esb.Itinerary.Test.exe という名前のアプリケーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="db3c6-105">In Windows Explorer, open the folder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test\bin\Debug where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples and start the application named Esb.Itinerary.Test.exe.</span></span>  

2. <span data-ttu-id="db3c6-106">サービスの種類を選択、 **ServiceType**ボックスの一覧は、要求の名前を指定し、、 **IsRequestResponse**場合、これは、要求/応答操作のチェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="db3c6-106">Select a service type in the **ServiceType** drop-down list, specify a name for the request, and then select the **IsRequestResponse** check box if this is a request/response operation.</span></span> <span data-ttu-id="db3c6-107">双方向の操作を指定し、旅行プランの Web サービスの WCF のバージョンを使用します。これを行うには、チェック ボックスを選択、 **Web サービス オプション**アプリケーション ウィンドウの上部にあるセクション。</span><span class="sxs-lookup"><span data-stu-id="db3c6-107">You can specify a two-way operation and choose to use the WCF version of the Itinerary Web service; to do this, select the check boxes in the **Web Service Options** section at the top of the application window.</span></span>  

3. <span data-ttu-id="db3c6-108">選択したサービスを使用する競合回避モジュールを指定する、 **AddResolversfortheService** 、ウィンドウで、競合回避モジュールがドロップダウン リストから入力し、クリックしての**AddResolver**します。</span><span class="sxs-lookup"><span data-stu-id="db3c6-108">To specify the resolvers to use with the selected service in the **AddResolversfortheService** section of the window, select a resolver type from the drop-down list, and then click **AddResolver**.</span></span> <span data-ttu-id="db3c6-109">必要な場合は、1 つ以上の競合回避モジュールを追加できます。</span><span class="sxs-lookup"><span data-stu-id="db3c6-109">You can add more than one resolver if required.</span></span> <span data-ttu-id="db3c6-110">必要なすべての競合回避モジュールを追加する をクリックして、 **AddService**旅行計画にこのサービスの呼び出しを追加するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="db3c6-110">After you add all the required resolvers, click the **AddService** button to add this service invocation to the itinerary.</span></span>  

4. <span data-ttu-id="db3c6-111">旅行計画に複数のサービス呼び出しを追加する場合は、手順 2. および 3. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="db3c6-111">If you want to add more service invocations to the itinerary, repeat steps 2 and 3.</span></span> <span data-ttu-id="db3c6-112">使用することも、 **RemoveService**と**ClearServices**旅行プラン サービスの一覧を変更するボタン。</span><span class="sxs-lookup"><span data-stu-id="db3c6-112">You can also use the **RemoveService** and **ClearServices** buttons to modify the list of services in the itinerary.</span></span>  

5. <span data-ttu-id="db3c6-113">別の時に現在のスケジュールを繰り返す場合は、完全な現在の旅程をディスクに保存 をクリックして、 **SaveItinerary**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="db3c6-113">If you want to repeat the current itinerary at another time, save the complete current itinerary to disk by clicking the **SaveItinerary** button.</span></span> <span data-ttu-id="db3c6-114">クリックして再度読み込むことができます、 **LoadItinerary**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="db3c6-114">You can load it again by clicking the **LoadItinerary** button.</span></span> <span data-ttu-id="db3c6-115">これは、サービスとの競合回避モジュールは、さまざまなメッセージまたはスケジュールの Web サービスの設定では、このシナリオを実行するたびに、旅行計画で指定する必要はないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="db3c6-115">This means that you do not have to specify the services and resolvers in the itinerary every time you execute this scenario with different messages or Itinerary Web service settings.</span></span>  

6. <span data-ttu-id="db3c6-116">適切なメッセージを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="db3c6-116">Load a suitable message.</span></span> <span data-ttu-id="db3c6-117">内のメッセージの名前とパスを入力するかこれを行う、 **LoadMessage**テキスト ボックスまたは省略記号ボタン (...) をクリックし、必要なメッセージ ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="db3c6-117">To do this, either type the path and name of the message in the **LoadMessage** text box or click the ellipsis button (...), and then select the required message file.</span></span>  

7. <span data-ttu-id="db3c6-118">をクリックして、 **SubmitRequest**に指定したスケジュールの設定を使用する処理のメッセージを送信するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="db3c6-118">Click the **SubmitRequest** button to submit the message for processing with the itinerary settings you specified.</span></span> <span data-ttu-id="db3c6-119">処理結果を返す場合に表示されます、**結果**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="db3c6-119">If the processing returns a result, this will appear in the **Result** text box.</span></span>
