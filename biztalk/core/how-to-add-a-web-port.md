---
title: Web ポートを追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web ports, creating
- creating, Web ports
ms.assetid: da94d98e-10ca-437a-ba34-7aa6efc68f3d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42e9853755788aa29d3ca7506829dcd6bdfed53d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248010"
---
# <a name="how-to-add-a-web-port"></a><span data-ttu-id="ca007-102">Web ポートを追加する方法</span><span class="sxs-lookup"><span data-stu-id="ca007-102">How to Add a Web Port</span></span>
<span data-ttu-id="ca007-103">Web ポートの追加には、オーケストレーション デザイナのポート画面を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca007-103">You add a Web port on the port surface in Orchestration Designer.</span></span> <span data-ttu-id="ca007-104">他の構成済みのポートと異なり、Web ポートでは要求(一方向) と要求 - 応答 (双方向) 操作を混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="ca007-104">Unlike other configured ports, Web ports support a mixture of request (one-way) and request/response (two-way) operations.</span></span> <span data-ttu-id="ca007-105">Web ポート内の各操作は、1 つの Web メソッドを表します。</span><span class="sxs-lookup"><span data-stu-id="ca007-105">Each operation in the Web port represents a Web method.</span></span> <span data-ttu-id="ca007-106">Web メソッドが含まれている場合*入力*と*出力*パラメーター、BizTalk は、要求/応答操作を作成します。</span><span class="sxs-lookup"><span data-stu-id="ca007-106">If the Web method contains *input* and *output* parameters, BizTalk creates a request/response operation.</span></span> <span data-ttu-id="ca007-107">Web サービスにのみ含まれている場合、*入力*パラメーター、BizTalk はのみ一方向の操作を作成します。</span><span class="sxs-lookup"><span data-stu-id="ca007-107">If the Web service contains only an *input* parameter, BizTalk only creates a one-way operation.</span></span>  
  
### <a name="to-add-a-web-port"></a><span data-ttu-id="ca007-108">Web ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="ca007-108">To add a Web port</span></span>  
  
1.  <span data-ttu-id="ca007-109">オーケストレーション デザイナーで、オーケストレーションを開き、ポート画面を右クリックし **新しい構成済みポート**です。</span><span class="sxs-lookup"><span data-stu-id="ca007-109">In Orchestration Designer, with an orchestration open, right-click the port surface, and then select **New Configured Port**.</span></span>  
  
2.  <span data-ttu-id="ca007-110">**[ポート構成ウィザードへようこそ]** ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca007-110">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="ca007-111">**ポートのプロパティ**] ページの [、**名前**テキスト ボックス、ポートの名前を入力し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="ca007-111">On the **Port Properties** page, in the **Name** text box, type a name for the port, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="ca007-112">**ポートの種類を選択して** ページで選択**既存のポートの種類を使用して**です。</span><span class="sxs-lookup"><span data-stu-id="ca007-112">In the **Select a Port Type** page, select **Use an existing Port Type**.</span></span>  
  
5.  <span data-ttu-id="ca007-113">**使用可能なポートの種類**ボックスで、展開、 **Web ポートの種類**ノードを選択、Web ポートの種類、追加された Web サービスに対応して、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="ca007-113">In the **Available Port Types** box, expand the **Web Port Types** node and select the Web port type that corresponds to the added Web service, and then click **Next**.</span></span>  
  
     <span data-ttu-id="ca007-114">次の図に示しています、**ポートの種類を選択して** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="ca007-114">The following figure shows the **Select a Port Type** dialog box.</span></span>  
  
     ![](../core/media/ebiz-prog-ws-addwebport.gif "ebiz_prog_ws_addwebport")  
  
6.  <span data-ttu-id="ca007-115">**ポートのバインド**] ページの [、**ポートのバインド**ドロップダウン ボックスで、**今指定**です。</span><span class="sxs-lookup"><span data-stu-id="ca007-115">In the **Port Binding** page, in the **Port binding** drop down box, select **Specify now**.</span></span> <span data-ttu-id="ca007-116">BizTalk によって、URI、トランスポート、受信パイプライン、および送信パイプラインについて、参照先の Web サービスの値が自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="ca007-116">BizTalk automatically places the values from the referenced Web service in the URI, transport, and receive and send pipelines.</span></span> <span data-ttu-id="ca007-117">BizTalk プロジェクトを展開すると、BizTalk はこれらの値を使用して送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca007-117">BizTalk uses these values to create the send port when you deploy your BizTalk project.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ca007-118">送信ポートの既定の認証方法には、匿名アクセスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ca007-118">The default authentication method for the send port is anonymous access.</span></span> <span data-ttu-id="ca007-119">Web サービスが別の認証方法や暗号化方法を要求する場合は、構成を変更し、Web サービスの実行に適切なユーザー資格情報や Secure Sockets Layer (SSL) を適用します。</span><span class="sxs-lookup"><span data-stu-id="ca007-119">If the Web service requires a different authentication or encryption method, you must change the configuration to supply the appropriate user credentials or Secure Sockets Layer (SSL) to run Web services.</span></span> <span data-ttu-id="ca007-120">詳細については、次を参照してください。 [SOAP 送信アダプタ](../core/soap-send-adapter.md)と[サンプル TMA: HTTP アダプタと SOAP アダプタ](../core/sample-tma-http-and-soap-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="ca007-120">For more information, see [SOAP Send Adapter](../core/soap-send-adapter.md) and [Sample TMA: HTTP and SOAP Adapters](../core/sample-tma-http-and-soap-adapters.md).</span></span>  
  
7.  <span data-ttu-id="ca007-121">をクリックして **[次へ]**、し**完了**ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="ca007-121">Click **Next**, and then **Finish** to complete the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca007-122">参照</span><span class="sxs-lookup"><span data-stu-id="ca007-122">See Also</span></span>  
 <span data-ttu-id="ca007-123">[ポート構成ウィザードを実行する方法](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="ca007-123">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="ca007-124">Web ポートの作成</span><span class="sxs-lookup"><span data-stu-id="ca007-124">Creating Web Ports</span></span>](../core/creating-web-ports.md)