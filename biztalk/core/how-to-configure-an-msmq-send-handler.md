---
title: "MSMQ 送信ハンドラーを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, send handlers
- configuring [MSMQ adapters], send handlers
- send handlers, MSMQ adapters
ms.assetid: 21917596-f27a-473b-859e-186ab5f4cd94
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: feacaec9d2794cf8806fa5156fe64b7290699faa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-an-msmq-send-handler"></a><span data-ttu-id="634b3-102">MSMQ 送信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="634b3-102">How to Configure an MSMQ Send Handler</span></span>
<span data-ttu-id="634b3-103">次の手順を実行して、MSMQ 送信ハンドラーのグローバル変数を変更します。</span><span class="sxs-lookup"><span data-stu-id="634b3-103">Use the following procedure to change the global variables for an MSMQ send handler.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="634b3-104">各ホストに関連付けられる送信ハンドラーは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="634b3-104">Each host can have only one send handler associated with it.</span></span>  
  
### <a name="to-change-global-variables-for-an-msmq-send-handler-by-using-the-biztalk-server-administration-console"></a><span data-ttu-id="634b3-105">BizTalk Server 管理コンソールを使用して MSMQ 送信ハンドラーのグローバル変数を変更するには</span><span class="sxs-lookup"><span data-stu-id="634b3-105">To change global variables for an MSMQ send handler by using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="634b3-106">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**を順に展開**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="634b3-106">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="634b3-107">展開したアダプターの一覧でクリックして**MSMQ**、右側のペインで、構成する送信ハンドラを右クリックしをクリック**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="634b3-107">In the expanded adapter list, click **MSMQ**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="634b3-108">**アダプター ハンドラーのプロパティ** ダイアログ ボックスで、**全般** タブの 、**ホスト名**一覧で、使用する送信ハンドラー、関連付けられているとする をクリックし、ホストを選択**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="634b3-108">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the send handler will be associated, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="634b3-109">**MSMQ トランスポートのプロパティ** ダイアログ ボックスで、値を入力**バッチ サイズ**です。</span><span class="sxs-lookup"><span data-stu-id="634b3-109">In the **MSMQ Transport Properties** dialog box, enter a value for **Batch Size**.</span></span>  
  
     <span data-ttu-id="634b3-110">MSMQ 送信ハンドラーが指定して、送信先キューにメッセージを送信する**バッチ サイズ**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="634b3-110">The MSMQ send handler will send messages to destination queues using the specified **Batch Size** parameter.</span></span> <span data-ttu-id="634b3-111">既定値**バッチ サイズ**値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="634b3-111">The default **Batch Size** value is 5.</span></span>  
  
5.  <span data-ttu-id="634b3-112">をクリックして**OK**  をクリック**ok**を閉じます、**アダプター ハンドラーのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="634b3-112">Click **OK** and click **OK** again to close the **Adapter Handler Properties** dialog box.</span></span>