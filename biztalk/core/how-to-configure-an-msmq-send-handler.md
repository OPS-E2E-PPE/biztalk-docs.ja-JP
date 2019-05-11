---
title: MSMQ 送信ハンドラーを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, send handlers
- configuring [MSMQ adapters], send handlers
- send handlers, MSMQ adapters
ms.assetid: 21917596-f27a-473b-859e-186ab5f4cd94
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f1ca5c7eb79f38671cc7e257b184125740ed0d8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386429"
---
# <a name="how-to-configure-an-msmq-send-handler"></a><span data-ttu-id="8e630-102">MSMQ 送信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="8e630-102">How to Configure an MSMQ Send Handler</span></span>
<span data-ttu-id="8e630-103">送信ハンドラーを MSMQ のグローバル変数を変更するのには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e630-103">Use the following procedure to change the global variables for an MSMQ send handler.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e630-104">各ホストには、1 つだけ送信ハンドラーが関連付けられていることができます。</span><span class="sxs-lookup"><span data-stu-id="8e630-104">Each host can have only one send handler associated with it.</span></span>  
  
### <a name="to-change-global-variables-for-an-msmq-send-handler-by-using-the-biztalk-server-administration-console"></a><span data-ttu-id="8e630-105">BizTalk Server 管理コンソールを使用してグローバル変数を MSMQ 送信ハンドラーを変更</span><span class="sxs-lookup"><span data-stu-id="8e630-105">To change global variables for an MSMQ send handler by using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="8e630-106">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順に展開**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="8e630-106">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="8e630-107">展開したアダプターの一覧でクリックして**MSMQ**、右側のウィンドウで、構成する送信ハンドラーを右クリックし をクリック、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="8e630-107">In the expanded adapter list, click **MSMQ**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="8e630-108">**アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**いる送信ハンドラー、関連付けられているとする をクリックし、ホストを選択します**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="8e630-108">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the send handler will be associated, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="8e630-109">**MSMQ トランスポートのプロパティ** ダイアログ ボックスで、値を入力**バッチ サイズ**します。</span><span class="sxs-lookup"><span data-stu-id="8e630-109">In the **MSMQ Transport Properties** dialog box, enter a value for **Batch Size**.</span></span>  
  
     <span data-ttu-id="8e630-110">MSMQ 送信ハンドラーは、指定されたを使用して、送信先キューにメッセージを送信**バッチ サイズ**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="8e630-110">The MSMQ send handler will send messages to destination queues using the specified **Batch Size** parameter.</span></span> <span data-ttu-id="8e630-111">既定の**バッチ サイズ**値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="8e630-111">The default **Batch Size** value is 5.</span></span>  
  
5.  <span data-ttu-id="8e630-112">をクリックして**OK**  をクリック**ok**を閉じるためにもう一度、**アダプター ハンドラーのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="8e630-112">Click **OK** and click **OK** again to close the **Adapter Handler Properties** dialog box.</span></span>