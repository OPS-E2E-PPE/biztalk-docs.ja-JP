---
title: BizTalk 操作サンプルを実行している |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e91d4e57-ba94-4730-8c5a-4c96902f313f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 681a7a2d99c7488c94d3b824fa3e7d707db435ac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292532"
---
# <a name="running-the-biztalk-operations-sample"></a><span data-ttu-id="f5da6-102">BizTalk 操作サンプルを実行しています。</span><span class="sxs-lookup"><span data-stu-id="f5da6-102">Running the BizTalk Operations Sample</span></span>
<span data-ttu-id="f5da6-103">Microsoft BizTalk 操作サンプルでは、Windows フォームのテスト クライアント アプリケーションを使用して、BizTalk 操作 Web サービスのメソッドを実行し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="f5da6-103">The Microsoft BizTalk Operations sample uses a Windows Forms test client application to execute methods of the BizTalk Operations Web service and display the results.</span></span> <span data-ttu-id="f5da6-104">それを実行して、独自のサービス指向アーキテクチャ (SOA) や ESB アプリケーション内の BizTalk 操作 Web サービスの使用方法を紹介するコードをチェックするテスト クライアント プロジェクトを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="f5da6-104">You can open the test client project to run it and to examine the code to see how you can use the BizTalk Operations Web service in your own service-oriented architecture (SOA) and ESB applications.</span></span>  
  
 <span data-ttu-id="f5da6-105">Windows エクスプ ローラーで \Samples\BizTalkOperations\bin\Debug、という名前のフォルダーを開き Microsoft.Practices.ESB.BizTalkOperations.Test.Client.exe アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="f5da6-105">In Windows Explorer, open the folder named \Samples\BizTalkOperations\bin\Debug, and then execute the application Microsoft.Practices.ESB.BizTalkOperations.Test.Client.exe.</span></span>  
  
 <span data-ttu-id="f5da6-106">図 1 は、BizTalk 操作 Web サービスのテスト用クライアント アプリケーションを示します。</span><span class="sxs-lookup"><span data-stu-id="f5da6-106">Figure 1 shows the test client application for the BizTalk Operations Web service.</span></span> <span data-ttu-id="f5da6-107">このアプリケーションを使用して BizTalk 操作 Web サービスのすべての関数を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="f5da6-107">You can execute all the functions of the BizTalk Operations Web service using this application.</span></span> <span data-ttu-id="f5da6-108">アプリケーションでは、ツリー ビューの形式で結果が表示され、サービスによって返されるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5da6-108">The application displays the results in a tree-view format and shows the message returned by the service.</span></span>  
  
 <span data-ttu-id="f5da6-109">![Web サービス テスト](../esb-toolkit/media/ch6-webservicetest.gif "Ch6 WebServiceTest")</span><span class="sxs-lookup"><span data-stu-id="f5da6-109">![Web Service Test](../esb-toolkit/media/ch6-webservicetest.gif "Ch6-WebServiceTest")</span></span>  
  
 <span data-ttu-id="f5da6-110">**図 1**</span><span class="sxs-lookup"><span data-stu-id="f5da6-110">**Figure 1**</span></span>  
  
 <span data-ttu-id="f5da6-111">**BizTalk 操作 Web サービス テスト クライアント**</span><span class="sxs-lookup"><span data-stu-id="f5da6-111">**The BizTalk Operations Web Service Test Client**</span></span>  
  
 <span data-ttu-id="f5da6-112">すべてのパラメーターを必要としない BizTalk 操作 Web サービスのメソッドを実行するには、アプリケーション ウィンドウの左側にある適切なボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5da6-112">To execute a method of the BizTalk Operations Web service that does not require any parameters, simply click the appropriate button in the left side of the application window.</span></span> <span data-ttu-id="f5da6-113">メソッドの入力パラメーターを必要とは、ウィンドウの上部にあるドロップダウン リストで、メソッドを選択の入力 をクリックし、必要な場合、パラメーター値、**サービスの呼び出し**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5da6-113">For methods that do require input parameters, select the method in the drop-down list at the top of the window, enter the parameter values you require, and then click the **Invoke Service** button.</span></span>  
  
## <a name="how-the-sample-works"></a><span data-ttu-id="f5da6-114">サンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="f5da6-114">How the Sample Works</span></span>  
 <span data-ttu-id="f5da6-115">サンプル アプリケーションでは、ESB BizTalk 操作 Web サービスのインスタンスを作成し、アプリケーションで選択した設定に応じて、適切なメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f5da6-115">The sample application instantiates the ESB BizTalk Operations Web service and calls the appropriate method depending on the settings you select in the application.</span></span> <span data-ttu-id="f5da6-116">選択したサービス メソッドにパラメーターとしてアプリケーションのコントロールに入力する値を渡すし、アプリケーション ウィンドウに表示するサービス メソッドから出力を収集します。</span><span class="sxs-lookup"><span data-stu-id="f5da6-116">It passes the value(s) you enter in the application controls as parameters to the selected service method, and it collects the output from the service method to display in the application window.</span></span>