---
title: MSMQ 受信ハンドラーを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive handlers, MSMQ adapters
- configuring [MSMQ adapters], receive handlers
- MSMQ adapters, receive handlers
ms.assetid: d6d82098-3a73-44e2-80d5-143f77e919cc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61741921363caa96acc2cb1a1e787ad1fbd41120
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386422"
---
# <a name="how-to-configure-an-msmq-receive-handler"></a><span data-ttu-id="57bc4-102">MSMQ 受信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="57bc4-102">How to Configure an MSMQ Receive Handler</span></span>
<span data-ttu-id="57bc4-103">次の手順に従って、MSMQ 受信ハンドラーを使用するホストを変更するのには、関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="57bc4-103">Use the following procedure to change the host with which the MSMQ receive handler is associated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57bc4-104">各ホストに関連付けられる受信ハンドラーは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="57bc4-104">Each host can associate with only one receive handler.</span></span>  
  
### <a name="to-change-the-host-with-which-the-msmq-receive-handler-is-associated"></a><span data-ttu-id="57bc4-105">MSMQ 受信ハンドラーを使用するホストを変更するのには、関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="57bc4-105">To change the host with which the MSMQ receive handler is associated</span></span>  
  
1.  <span data-ttu-id="57bc4-106">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順に展開**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="57bc4-106">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="57bc4-107">展開したアダプターの一覧でクリックして**MSMQ**、右側のウィンドウで、構成する受信ハンドラーを右クリックし をクリック、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="57bc4-107">In the expanded adapter list, click **MSMQ**, in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="57bc4-108">**アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、受信ハンドラーが関連付けられているが、ホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="57bc4-108">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  
  
4.  <span data-ttu-id="57bc4-109">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57bc4-109">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57bc4-110">参照</span><span class="sxs-lookup"><span data-stu-id="57bc4-110">See Also</span></span>  
 [<span data-ttu-id="57bc4-111">MSMQ アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="57bc4-111">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)