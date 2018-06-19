---
title: MSMQ 受信ハンドラーを構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 6f34e1b3f399c93bd92aa9c4e07f6e0082d25204
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247874"
---
# <a name="how-to-configure-an-msmq-receive-handler"></a><span data-ttu-id="63946-102">MSMQ 受信ハンドラーを構成する方法 [BTS06]</span><span class="sxs-lookup"><span data-stu-id="63946-102">How to Configure an MSMQ Receive Handler</span></span>
<span data-ttu-id="63946-103">次の手順を実行して、MSMQ 受信ハンドラーが関連付けられているホストを変更します。</span><span class="sxs-lookup"><span data-stu-id="63946-103">Use the following procedure to change the host with which the MSMQ receive handler is associated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63946-104">各ホストに関連付けられる受信ハンドラーは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="63946-104">Each host can associate with only one receive handler.</span></span>  
  
### <a name="to-change-the-host-with-which-the-msmq-receive-handler-is-associated"></a><span data-ttu-id="63946-105">MSMQ 受信ハンドラーを関連付けるホストを変更するには</span><span class="sxs-lookup"><span data-stu-id="63946-105">To change the host with which the MSMQ receive handler is associated</span></span>  
  
1.  <span data-ttu-id="63946-106">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**を順に展開**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="63946-106">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="63946-107">展開したアダプターの一覧でクリックして**MSMQ**、右側のペインで、構成する受信ハンドラを右クリックしをクリック**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="63946-107">In the expanded adapter list, click **MSMQ**, in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="63946-108">**アダプター ハンドラーのプロパティ** ダイアログ ボックスで、**全般** タブの 、**ホスト名**一覧で、受信ハンドラーが関連付けられる、ホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="63946-108">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  
  
4.  <span data-ttu-id="63946-109">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63946-109">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63946-110">参照</span><span class="sxs-lookup"><span data-stu-id="63946-110">See Also</span></span>  
 [<span data-ttu-id="63946-111">MSMQ アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="63946-111">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)