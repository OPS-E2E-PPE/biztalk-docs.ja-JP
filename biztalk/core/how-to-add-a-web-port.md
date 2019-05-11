---
title: Web ポートを追加する方法 |Microsoft Docs
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
ms.openlocfilehash: a67cfd33aeace3b6cfde9f1e0a7e87831d7972ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387337"
---
# <a name="how-to-add-a-web-port"></a><span data-ttu-id="f7168-102">Web ポートを追加する方法</span><span class="sxs-lookup"><span data-stu-id="f7168-102">How to Add a Web Port</span></span>
<span data-ttu-id="f7168-103">オーケストレーション デザイナのポート画面には、Web ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="f7168-103">You add a Web port on the port surface in Orchestration Designer.</span></span> <span data-ttu-id="f7168-104">他の構成済みのポートとは異なりは、Web ポートは、(一方向) の要求と要求/応答 (双方向) 操作の組み合わせをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f7168-104">Unlike other configured ports, Web ports support a mixture of request (one-way) and request/response (two-way) operations.</span></span> <span data-ttu-id="f7168-105">Web ポート内の各操作では、Web メソッドを表します。</span><span class="sxs-lookup"><span data-stu-id="f7168-105">Each operation in the Web port represents a Web method.</span></span> <span data-ttu-id="f7168-106">Web メソッドが含まれている場合*入力*と*出力*パラメーターでは、BizTalk は要求/応答操作を作成します。</span><span class="sxs-lookup"><span data-stu-id="f7168-106">If the Web method contains *input* and *output* parameters, BizTalk creates a request/response operation.</span></span> <span data-ttu-id="f7168-107">Web サービスにのみ含まれている場合、*入力*パラメーターでは、BizTalk はのみ一方向の操作を作成します。</span><span class="sxs-lookup"><span data-stu-id="f7168-107">If the Web service contains only an *input* parameter, BizTalk only creates a one-way operation.</span></span>  
  
### <a name="to-add-a-web-port"></a><span data-ttu-id="f7168-108">Web ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="f7168-108">To add a Web port</span></span>  
  
1.  <span data-ttu-id="f7168-109">オーケストレーション デザイナのオーケストレーションを開き、ポート画面を右クリックし **新しい構成済みポート**します。</span><span class="sxs-lookup"><span data-stu-id="f7168-109">In Orchestration Designer, with an orchestration open, right-click the port surface, and then select **New Configured Port**.</span></span>  
  
2.  <span data-ttu-id="f7168-110">**[ポート構成ウィザードへようこそ]** ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7168-110">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="f7168-111">**ポートのプロパティ**] ページの [、**名前**テキスト ボックスに、ポートの名前を入力し、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="f7168-111">On the **Port Properties** page, in the **Name** text box, type a name for the port, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="f7168-112">**ポートの種類を選択します。** ] ページで [**既存のポートの種類を使用して、**。</span><span class="sxs-lookup"><span data-stu-id="f7168-112">In the **Select a Port Type** page, select **Use an existing Port Type**.</span></span>  
  
5.  <span data-ttu-id="f7168-113">**使用可能なポートの種類**ボックスで、展開、 **Web ポートの種類**ノードと選択、Web ポートの追加の Web サービスに対応する種類をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="f7168-113">In the **Available Port Types** box, expand the **Web Port Types** node and select the Web port type that corresponds to the added Web service, and then click **Next**.</span></span>  
  
     <span data-ttu-id="f7168-114">次に示します、**ポートの種類を選択します。**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="f7168-114">The following figure shows the **Select a Port Type** dialog box.</span></span>  
  
     <span data-ttu-id="f7168-115">![](../core/media/ebiz-prog-ws-addwebport.gif "ebiz_prog_ws_addwebport")</span><span class="sxs-lookup"><span data-stu-id="f7168-115">![](../core/media/ebiz-prog-ws-addwebport.gif "ebiz_prog_ws_addwebport")</span></span>  
  
6.  <span data-ttu-id="f7168-116">**ポートのバインド**ページで、**ポートのバインド**ドロップダウン ボックスで、**今指定する**します。</span><span class="sxs-lookup"><span data-stu-id="f7168-116">In the **Port Binding** page, in the **Port binding** drop down box, select **Specify now**.</span></span> <span data-ttu-id="f7168-117">BizTalk が自動的に、URI、トランスポートに参照する Web サービスから値を格納し、受信および送信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="f7168-117">BizTalk automatically places the values from the referenced Web service in the URI, transport, and receive and send pipelines.</span></span> <span data-ttu-id="f7168-118">BizTalk では、これらの値を使用して、BizTalk プロジェクトを展開するときに、送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7168-118">BizTalk uses these values to create the send port when you deploy your BizTalk project.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="f7168-119">送信ポートの既定の認証方法は、匿名アクセスです。</span><span class="sxs-lookup"><span data-stu-id="f7168-119">The default authentication method for the send port is anonymous access.</span></span> <span data-ttu-id="f7168-120">Web サービスには、さまざまな認証または暗号化の方法が必要とする場合は、適切なユーザーの資格情報または Secure Sockets Layer (SSL) Web サービスの実行に提供する構成を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7168-120">If the Web service requires a different authentication or encryption method, you must change the configuration to supply the appropriate user credentials or Secure Sockets Layer (SSL) to run Web services.</span></span> <span data-ttu-id="f7168-121">詳細については、次を参照してください[SOAP 送信アダプタ](../core/soap-send-adapter.md)と[サンプル TMA:。HTTP アダプターと SOAP アダプター](../core/sample-tma-http-and-soap-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="f7168-121">For more information, see [SOAP Send Adapter](../core/soap-send-adapter.md) and [Sample TMA: HTTP and SOAP Adapters](../core/sample-tma-http-and-soap-adapters.md).</span></span>  
  
7.  <span data-ttu-id="f7168-122">をクリックして **[次へ]**、し**完了**ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="f7168-122">Click **Next**, and then **Finish** to complete the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7168-123">参照</span><span class="sxs-lookup"><span data-stu-id="f7168-123">See Also</span></span>  
 <span data-ttu-id="f7168-124">[ポート構成ウィザードを実行する方法](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="f7168-124">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="f7168-125">Web ポートの作成</span><span class="sxs-lookup"><span data-stu-id="f7168-125">Creating Web Ports</span></span>](../core/creating-web-ports.md)