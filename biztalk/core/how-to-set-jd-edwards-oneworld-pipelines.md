---
title: "JD Edwards OneWorld パイプラインを設定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive pipelines
- send pipelines
- setting pipelines
- pipelines, setting
ms.assetid: 821d4081-a2d4-4957-abc0-d6370e719ba8
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e45ec6f6eb3be74e150e77de9ef6dbbe461a361a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-jd-edwards-oneworld-pipelines"></a><span data-ttu-id="ee2f1-102">JD Edwards OneWorld パイプラインの設定方法</span><span class="sxs-lookup"><span data-stu-id="ee2f1-102">How to Set JD Edwards OneWorld Pipelines</span></span>
<span data-ttu-id="ee2f1-103">Microsoft BizTalk Adapter for JD Edwards OneWorld では、送信パイプラインと受信パイプラインについてそれぞれ、XMLTransmit および XMLReceive を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-103">Microsoft BizTalk Adapter for JD Edwards OneWorld requires that you select XMLTransmit and XMLReceive for the send and receive pipelines respectively.</span></span>  
  
### <a name="to-set-pipelines"></a><span data-ttu-id="ee2f1-104">パイプラインを設定するには</span><span class="sxs-lookup"><span data-stu-id="ee2f1-104">To set pipelines</span></span>  
  
1.  <span data-ttu-id="ee2f1-105">**開始** メニューのをポイント**Program Files**、 をポイント**Microsoft BizTalk Server** 、順にクリック**BizTalk Server 管理コンソール**BizTalk Server 管理コンソールを開始します。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-105">On the **Start** menu, point to **Program Files**, point to **Microsoft BizTalk Server** , and then click **BizTalk Server Administration** to start the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="ee2f1-106">BizTalk Server 管理コンソールを展開し、 **BizTalk グループ**、展開**アプリケーション**、し、目的のアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-106">Expand BizTalk Server Administration, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
3.  <span data-ttu-id="ee2f1-107">選択**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-107">Select **Send Ports**.</span></span> <span data-ttu-id="ee2f1-108">詳細ペインで選択した送信ポートを右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-108">In the details pane, right-click the selected send port and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="ee2f1-109">**送信ポート プロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-109">In the **Send Ports Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="ee2f1-110">送信パイプラインを選択して、**送信パイプライン**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-110">Select the send pipeline from the **Send Pipeline** drop-down list.</span></span>  
  
    2.  <span data-ttu-id="ee2f1-111">受信パイプラインを選択、**受信パイプライン**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-111">Select the Receive pipeline from the **Receive Pipeline** drop-down list.</span></span>  
  
5.  <span data-ttu-id="ee2f1-112">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-112">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee2f1-113">参照</span><span class="sxs-lookup"><span data-stu-id="ee2f1-113">See Also</span></span>  
 [<span data-ttu-id="ee2f1-114">JD Edwards OneWorld 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="ee2f1-114">Creating JD Edwards OneWorld Send Handlers</span></span>](../core/creating-jd-edwards-oneworld-send-handlers.md)