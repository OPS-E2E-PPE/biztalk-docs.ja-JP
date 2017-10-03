---
title: "BizTalk Operations サンプルを実行している |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e91d4e57-ba94-4730-8c5a-4c96902f313f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57480e6020b2ab262d7d9db522b9dd2f79aa49cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-biztalk-operations-sample"></a><span data-ttu-id="e3761-102">BizTalk Operations サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="e3761-102">Running the BizTalk Operations Sample</span></span>
<span data-ttu-id="e3761-103">Microsoft BizTalk Operations サンプルでは、Windows フォーム クライアントのテスト アプリケーションを使用して BizTalk Operations Web サービスのメソッドを実行し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="e3761-103">The Microsoft BizTalk Operations sample uses a Windows Forms test client application to execute methods of the BizTalk Operations Web service and display the results.</span></span> <span data-ttu-id="e3761-104">それを実行して、独自のサービス指向アーキテクチャ (SOA) および ESB アプリケーションで、BizTalk Operations Web サービスを使用する方法を表示するコードをチェックするテスト クライアント プロジェクトを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="e3761-104">You can open the test client project to run it and to examine the code to see how you can use the BizTalk Operations Web service in your own service-oriented architecture (SOA) and ESB applications.</span></span>  
  
 <span data-ttu-id="e3761-105">Windows エクスプ ローラーで、\Samples\BizTalkOperations\bin\Debug、名前が付いたフォルダーを開き Microsoft.Practices.ESB.BizTalkOperations.Test.Client.exe アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="e3761-105">In Windows Explorer, open the folder named \Samples\BizTalkOperations\bin\Debug, and then execute the application Microsoft.Practices.ESB.BizTalkOperations.Test.Client.exe.</span></span>  
  
 <span data-ttu-id="e3761-106">図 1 は、BizTalk Operations Web サービスに対してクライアント テスト アプリケーションを示します。</span><span class="sxs-lookup"><span data-stu-id="e3761-106">Figure 1 shows the test client application for the BizTalk Operations Web service.</span></span> <span data-ttu-id="e3761-107">このアプリケーションを使用して、BizTalk Operations Web サービスのすべての関数を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="e3761-107">You can execute all the functions of the BizTalk Operations Web service using this application.</span></span> <span data-ttu-id="e3761-108">アプリケーションは、ツリー ビューの形式で結果が表示され、サービスによって返されるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3761-108">The application displays the results in a tree-view format and shows the message returned by the service.</span></span>  
  
 <span data-ttu-id="e3761-109">![Web サービス テスト](../esb-toolkit/media/ch6-webservicetest.gif "Ch6 WebServiceTest")</span><span class="sxs-lookup"><span data-stu-id="e3761-109">![Web Service Test](../esb-toolkit/media/ch6-webservicetest.gif "Ch6-WebServiceTest")</span></span>  
  
 <span data-ttu-id="e3761-110">**図 1**</span><span class="sxs-lookup"><span data-stu-id="e3761-110">**Figure 1**</span></span>  
  
 <span data-ttu-id="e3761-111">**BizTalk Operations Web サービス テスト用クライアント**</span><span class="sxs-lookup"><span data-stu-id="e3761-111">**The BizTalk Operations Web Service Test Client**</span></span>  
  
 <span data-ttu-id="e3761-112">アプリケーション ウィンドウの左側にある適切なボタンをクリックするだけで、すべてのパラメーターが不要な BizTalk Operations Web サービスのメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e3761-112">To execute a method of the BizTalk Operations Web service that does not require any parameters, simply click the appropriate button in the left side of the application window.</span></span> <span data-ttu-id="e3761-113">メソッドの入力パラメーターが必要では、ウィンドウの上部にあるドロップダウン リストでメソッドを選択して、入力パラメーターの値を必要とし、をクリックして、**サービスの呼び出し**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3761-113">For methods that do require input parameters, select the method in the drop-down list at the top of the window, enter the parameter values you require, and then click the **Invoke Service** button.</span></span>  
  
## <a name="how-the-sample-works"></a><span data-ttu-id="e3761-114">このサンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="e3761-114">How the Sample Works</span></span>  
 <span data-ttu-id="e3761-115">サンプル アプリケーションは、ESB BizTalk Operations Web サービスをインスタンス化し、アプリケーションで選択した設定に応じて、適切なメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e3761-115">The sample application instantiates the ESB BizTalk Operations Web service and calls the appropriate method depending on the settings you select in the application.</span></span> <span data-ttu-id="e3761-116">選択したサービス メソッドにパラメーターとしてアプリケーションのコントロールに入力した値を渡すし、アプリケーション ウィンドウに表示するサービスのメソッドから出力を収集します。</span><span class="sxs-lookup"><span data-stu-id="e3761-116">It passes the value(s) you enter in the application controls as parameters to the selected service method, and it collects the output from the service method to display in the application window.</span></span>